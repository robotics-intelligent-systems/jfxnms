# jfxnms — OpenTwin AI Network Management System

> Open, modular and standards-oriented reference architecture for AI-assisted network operations, digital twins, SDN/NFV, observability, simulation, infrastructure management, V2X/network-of-systems research and automated network engineering.

## Table of Contents

- Description and Context
- Vision
- Objectives
- Reference Architecture
- OpenTwin Network Digital Twin
- AI-Assisted Network Operations
- Network Management and SDN
- Wireless, V2X and Network Simulation
- Infrastructure and Data Center Management
- Security and Network Observability
- MBSE CAD CAM CAS
- Open-Source Technology Compendium
- User Guide
- Installation Guide
- Dependencies
- Recommended Repository Structure
- MVP
- Development Roadmap
- How to Contribute
- Code of Conduct
- Authors and Maintainers
- Additional Information
- Intellectual Property and Open Design
- Disclaimer
- License

---

## Description and Context

**jfxnms / OpenTwin AI Network Management System** consolidates the source repository into a structured architecture for network management, network digital twins, AI-assisted operations, SDN, wireless and V2X simulation, infrastructure orchestration, data-center asset management, security monitoring and end-to-end network experimentation.

The source repository is titled **Artificial Intelligence for Network Management System** and references Kubernetes, Apex/SAPIENT middleware, atemsys, OpenAirTwin, Harvester, machine learning with OMNeT++, Artery, AVENS, space_veins, NoSSim, MAVSIMNET, CrowNet, ANSA, JetKVM, Ralph, SONiC, OpenWISP, NMS PRIME, ONOS, OpenWrt, OcNOS, Zeek, Open Network Linux, Mininet, Ryu, Floodlight, Apache MINA, Apache Storm and Redfish.

The source also defines the engineering lifecycle:

```text
MBSE -> CAD -> CAM -> CAS
```

with Arcadia/Capella as a systems-engineering reference.

This consolidated README uses the BID repository template only as a **documentation-structure reference**. It does not imply BID/IDB sponsorship, funding, endorsement, catalog membership or institutional affiliation.

## Vision

```text
USERS / OPERATORS / AUTOMATION
             |
             v
OpenTwin AI Network Management
             |
Intent | Inventory | Topology | Telemetry | AI/AIOps
             |
             v
NETWORK DIGITAL TWIN
Assets | Links | State | Events | Configuration | Models
       |                 |                 |
       v                 v                 v
 REAL NETWORK       SIMULATION       INFRASTRUCTURE
OpenWrt/SONiC      Mininet/OMNeT++   K8s/Harvester
SDN/OpenWISP       V2X/Aerial/Sat    Servers/Redfish
       |                 |                 |
       +-----------------+-----------------+
                         |
                         v
              VERIFY / OPTIMIZE / OPERATE
```

## Objectives

- Build an open, modular Network Management System architecture.
- Represent physical and virtual network assets through OpenTwin digital twins.
- Maintain topology, configuration, state, telemetry, alarms and historical events.
- Support AI-assisted anomaly detection, forecasting and operations decision support.
- Integrate SDN controllers and open/disaggregated network operating systems.
- Support simulation-before-deployment workflows.
- Enable wireless, V2X, aerial and satellite-network experimentation.
- Integrate data-center infrastructure and hardware-management interfaces.
- Provide security analytics and network observability.
- Preserve traceability between requirements, architecture, simulation and operational evidence.
- Minimize proprietary lock-in through documented adapters and replaceable implementations.

## Reference Architecture

```text
+----------------------------------------------------------------+
| EXPERIENCE / OPERATIONS                                        |
| Web UI | Dashboards | Alerts | Network Maps | Automation      |
+----------------------------+-----------------------------------+
                             |
+----------------------------v-----------------------------------+
| SERVICE LAYER                                                  |
| Inventory | Topology | Config | Telemetry | Events | Policy   |
+----------------------------+-----------------------------------+
                             |
+----------------------------v-----------------------------------+
| OPENTWIN NETWORK CORE                                          |
| Twin Registry | Graph | State | History | Models | Provenance |
+--------------+------------------------+-------------------------+
               |                        |
               v                        v
+----------------------------+   +-------------------------------+
| AI / AIOps                 |   | SIMULATION / VERIFICATION     |
| Anomaly Detection          |   | Mininet / OMNeT++             |
| Forecasting                |   | V2X / Aerial / Satellite      |
| Root-Cause Assistance      |   | Network-of-Systems            |
+--------------+-------------+   +---------------+---------------+
               |                                 |
               +----------------+----------------+
                                |
+-------------------------------v--------------------------------+
| ADAPTER / CONTROL LAYER                                        |
| OpenWISP | ONOS | Ryu | Floodlight | OpenWrt | SONiC | Redfish|
+-------------------------------+--------------------------------+
                                |
+-------------------------------v--------------------------------+
| PHYSICAL / VIRTUAL INFRASTRUCTURE                              |
| Switches | Routers | APs | Edge | K8s | HCI | Servers | V2X |
+----------------------------------------------------------------+
```

Cross-cutting concerns: **Cybersecurity · Identity · Auditability · Configuration Management · Data Provenance · Interoperability · Resilience · Observability · Human Oversight**.

## OpenTwin Network Digital Twin

Candidate twin types include Network Twin, Site Twin, Router Twin, Switch Twin, Access Point Twin, Server Twin, Kubernetes Cluster Twin, Hyperconverged Infrastructure Twin, Link Twin, Wireless Cell Twin, V2X Node Twin, Vehicle Network Twin, Satellite Link Twin, Data Center Twin, Security Sensor Twin and Simulation Scenario Twin.

```yaml
twin:
  id: switch-core-01
  type: network-switch
  configuration:
    platform: generic
    management_adapter: open
  state:
    availability: unknown
    interfaces: []
  topology:
    neighbors: []
  telemetry_refs: []
  alarm_refs: []
  model_refs: []
  provenance:
    source: discovery
    timestamp: null
```

Lifecycle:

```text
DISCOVER -> REGISTER -> MODEL -> OBSERVE -> SIMULATE -> COMPARE -> OPTIMIZE -> CHANGE -> VERIFY
```

## AI-Assisted Network Operations

Potential applications include anomaly detection, time-series forecasting, capacity prediction, congestion detection, fault correlation, probable root-cause ranking, configuration-drift analysis, predictive hardware maintenance, path optimization, wireless-performance analysis and incident summarization.

AI-generated recommendations should retain model version, input data, confidence/uncertainty where available and decision provenance.

## Network Management and SDN

Potential adapters and references include:

- OpenWISP for deployment, monitoring and management.
- NMS PRIME as a provisioning/NMS reference.
- ONOS for SDN control.
- Ryu and Floodlight for SDN experimentation.
- OpenWrt for embedded network devices.
- SONiC for open network operating-system environments.
- Open Network Linux as a white-box networking reference.
- OcNOS as a disaggregated network OS reference subject to licensing/interoperability review.

No single controller or network operating system is assumed to be mandatory.

## Wireless V2X and Network Simulation

The source repository includes research references for V2X, aerial vehicle networks, vehicle-to-satellite links, network-of-systems simulation and wireless digital twins, including OMNeT++, Artery, AVENS, space_veins, NoSSim, MAVSIMNET, CrowNet, ANSA and OpenAirTwin.

```text
Network Requirements
        |
Scenario Model
        |
General Network -------- Wireless / Mobility
Mininet                  OMNeT++ / Artery
NoSSim                   AVENS / MAVSIMNET
CrowNet                  space_veins
        |                     |
        +----------+----------+
                   |
             OpenTwin Twin
                   |
            KPI / Event Compare
```

## Infrastructure and Data Center Management

Candidate functions include server/chassis inventory, hardware health, remote management, Kubernetes state, HCI state, asset lifecycle and configuration history.

Relevant source references include Kubernetes, Harvester, Redfish, Ralph and JetKVM.

## Security and Network Observability

Security capabilities may include traffic analysis, anomaly detection, configuration-drift detection, topology-aware incident correlation, authentication, RBAC, audit trails, secure APIs and controlled configuration changes.

**Zeek** may be integrated as an optional network-analysis/observability component.

## MBSE CAD CAM CAS

The source repository explicitly defines:

```text
MBSE -> CAD -> CAM -> CAS
```

**MBSE:** Arcadia/Capella for stakeholder needs, operational analysis, system requirements, logical architecture, physical architecture and verification traceability.

**CAD:** physical network/datacenter layouts, racks, edge appliances, antennas or hardware prototypes where applicable.

**CAM:** manufacturing/assembly only when independently developed hardware is included.

**CAS:** topology emulation, wireless simulation, SDN experiments, V2X/aerial/satellite scenarios and end-to-end performance analysis.

## Open-Source Technology Compendium

| Domain | Technology / Reference | Proposed Role |
|---|---|---|
| Container Orchestration | Kubernetes | Workload / cluster orchestration |
| Middleware | Apex / SAPIENT | Integration research reference |
| Kernel / I/O | atemsys | Low-level system integration reference |
| Wireless Digital Twin | OpenAirTwin | Wireless digital-twin research |
| HCI | Harvester | Virtualization / HCI |
| Network Simulation | OMNeT++ ML | Simulation and ML experiments |
| V2X | Artery | V2X simulation |
| Aerial Networks | AVENS | Aerial network simulation |
| Satellite/V2X | space_veins | Vehicle-to-satellite simulation |
| Network-of-Systems | NoSSim | Network-of-systems simulation |
| MAV Networks | MAVSIMNET | Mobile/aerial network simulation |
| Simulation | CrowNet | Mobile/network simulation |
| Simulation Automation | ANSA | Automated simulation/analysis |
| Remote Hardware | JetKVM | KVM-over-IP reference |
| CMDB / Assets | Ralph | Asset/data-center management |
| Network OS | SONiC | Open network OS |
| NMS | OpenWISP | Deployment/monitoring/management |
| NMS / Provisioning | NMS PRIME | Provisioning/NMS reference |
| SDN | ONOS | SDN controller |
| Embedded Network OS | OpenWrt | Router/edge platform |
| Network OS Reference | OcNOS | Disaggregated NOS reference |
| Network Security | Zeek | Network analysis/observability |
| White-box Networking | Open Network Linux | NOS development reference |
| Network Emulation | Mininet | SDN/network emulation |
| SDN | Ryu | SDN framework |
| SDN | Floodlight | SDN/OpenFlow research |
| Network Framework | Apache MINA | Network application framework |
| Stream Processing | Apache Storm | Real-time distributed processing |
| Hardware Management | Redfish | Data-center hardware API |
| MBSE | Arcadia / Capella | Systems engineering |

Inclusion does not imply that every technology is a required dependency, currently maintained, mutually license-compatible or production-ready. Each integration requires independent technical, security and licensing review.

## User Guide

1. Define network scope and operational objectives.
2. Register sites, devices, links and infrastructure assets.
3. Import or discover topology.
4. Map assets into OpenTwin digital twins.
5. Connect telemetry/event sources.
6. Establish configuration baselines.
7. Define KPIs and alarms.
8. Reproduce the target topology in simulation where appropriate.
9. Compare simulated and observed behavior.
10. Execute AI-assisted analysis.
11. Review recommendations.
12. Apply approved changes through an adapter/controller.
13. Verify outcomes and record evidence.
14. Preserve configuration and event provenance.

## Installation Guide

```bash
git clone https://github.com/robotics-intelligent-systems/jfxnms.git
cd jfxnms
```

The source repository should currently be treated primarily as a **technology compendium and architecture reference**. Do not assume every referenced project forms one executable stack.

Suggested MVP:

```text
Web/API
  |
OpenTwin Network Core
  |
Inventory + Topology + Telemetry
  |
Mininet Adapter
  |
OpenWISP / Ryu / Controller Adapter
```

## Dependencies

### Required Dependencies

Only components necessary for the selected runnable profile.

### Optional Integrations

Kubernetes, Harvester, OpenWISP, ONOS, Ryu, Floodlight, OpenWrt, SONiC, Zeek, Redfish, Ralph and Apache Storm may be treated as optional integrations when appropriate.

### Research References

OpenAirTwin, OMNeT++ ML experiments, Artery, AVENS, space_veins, NoSSim, MAVSIMNET, CrowNet, ANSA and other experimental simulators/frameworks belong in a research-reference category unless selected for an implementation profile.

## Recommended Repository Structure

```text
jfxnms/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── docs/
├── MBSE/
│   ├── Arcadia/
│   ├── CAD/
│   ├── CAM/
│   └── CAS/
├── opentwin/
│   ├── registry/
│   ├── topology/
│   ├── state/
│   ├── history/
│   └── provenance/
├── inventory/
├── topology/
├── telemetry/
├── events/
├── aiops/
├── simulation/
│   ├── mininet/
│   ├── omnet/
│   ├── v2x/
│   ├── aerial/
│   └── satellite/
├── adapters/
│   ├── openwisp/
│   ├── onos/
│   ├── ryu/
│   ├── floodlight/
│   ├── sonic/
│   ├── openwrt/
│   ├── redfish/
│   └── zeek/
├── infrastructure/
├── security/
├── api/
├── ui/
├── deployment/
├── tests/
└── examples/
```

## MVP

MVP features:

- network asset registry;
- topology graph;
- configuration baseline;
- telemetry ingestion;
- alarms/events;
- Network Twin representation;
- Mininet topology emulation;
- one SDN/NMS adapter;
- simple anomaly detection;
- REST API;
- dashboard;
- event/configuration provenance.

Success criteria:

- devices and links are represented as identifiable twins;
- topology can be reconstructed reproducibly;
- telemetry maps to the correct asset;
- simulation topology can be compared with target topology;
- configuration changes are recorded;
- alarms preserve time/source;
- basic anomaly detection can be evaluated against recorded data;
- no proprietary cloud/controller is mandatory.

## Development Roadmap

### Phase 1 — Documentation and MBSE
- [x] Consolidated source technology compendium.
- [x] BID-inspired documentation organization.
- [x] OpenTwin NMS reference architecture.
- [ ] Requirements baseline.
- [ ] Arcadia/Capella model.

### Phase 2 — Network Twin Core
- [ ] Asset registry.
- [ ] Topology graph.
- [ ] State/history.
- [ ] Configuration baselines.
- [ ] Event provenance.
- [ ] API.

### Phase 3 — Simulation
- [ ] Mininet adapter.
- [ ] Scenario model.
- [ ] Simulation results.
- [ ] KPI/topology comparison.

### Phase 4 — Network Management / SDN
- [ ] OpenWISP adapter.
- [ ] Ryu or ONOS adapter.
- [ ] OpenWrt integration.
- [ ] SONiC integration.

### Phase 5 — Infrastructure
- [ ] Kubernetes cluster twin.
- [ ] Harvester integration.
- [ ] Redfish adapter.
- [ ] Ralph/CMDB mapping.

### Phase 6 — Security and Observability
- [ ] Zeek ingestion.
- [ ] Drift detection.
- [ ] Audit logging.
- [ ] Role-based access.

### Phase 7 — AI / AIOps
- [ ] Anomaly detection.
- [ ] Capacity forecasting.
- [ ] Fault correlation.
- [ ] Predictive maintenance.
- [ ] Recommendation provenance.

### Phase 8 — Wireless / V2X
- [ ] OMNeT++ integration.
- [ ] Artery scenarios.
- [ ] Wireless twin model.
- [ ] V2X telemetry comparison.

### Phase 9 — Aerial / Satellite / Network-of-Systems
- [ ] AVENS/MAVSIMNET research integration.
- [ ] space_veins scenarios.
- [ ] Network-of-Systems models.

### Phase 10 — Production Hardening
- [ ] CI/CD.
- [ ] Secure secrets handling.
- [ ] Resilience and performance testing.
- [ ] Backup/recovery.
- [ ] Release governance.

## How to Contribute

Contributions are welcome in network management, SDN, network digital twins, observability, network security, Kubernetes/network infrastructure, network simulation, wireless/V2X, aerial/satellite networking, AI/AIOps, MBSE and documentation.

Pull requests should document scope, architecture impact, supported versions, network privileges, dependencies/licenses, security implications, tests, simulation/verification evidence and rollback considerations.

Do not commit production credentials, device secrets, private network topology, customer configuration backups or restricted firmware.

## Code of Conduct

Contributors should maintain a respectful, inclusive, professional and technically constructive environment. A dedicated `CODE_OF_CONDUCT.md` is recommended.

## Authors and Maintainers

Maintained by the **Robotics Intelligent Systems** open-source initiative.

Repository: `robotics-intelligent-systems/jfxnms`

Third-party software, trademarks, protocols, datasets, models and documentation remain the property of their respective owners.

## Additional Information

jfxnms can serve as a Network Management System architecture reference, network digital-twin research platform, AIOps experimentation framework, SDN integration testbed, network simulation catalog, wireless/V2X research platform, data-center infrastructure management reference and MBSE-to-network-verification framework.

The OpenTwin organization introduced here is an architectural consolidation of technologies already referenced by the source repository; it is not a claim that all proposed modules are already implemented.

## Intellectual Property and Open Design

Preferred principle:

> **Open, modular architecture designed to minimize proprietary lock-in and enable independent implementations.**

The project should favor open standards, documented interfaces, modular adapters, replaceable implementations, portable data models, explicit provenance and reproducible simulations.

Open source does not itself guarantee freedom from third-party patent, copyright, trademark or other intellectual-property rights. Licensing and jurisdiction-specific review remain necessary.

## Disclaimer

**jfxnms / OpenTwin AI Network Management System is a research, educational and engineering project.**

It is not, by itself, a production-certified telecommunications, safety-critical, emergency-communications or cybersecurity system. AI recommendations, simulated results, topology models and digital-twin state can be incomplete or inaccurate and require engineering validation before operational changes are applied.

The BID repository template is used solely as a **documentation-structure reference**. This project does not claim BID/IDB funding, sponsorship, endorsement, catalog membership or institutional affiliation.

## License

Preserve the actual license selected by the `jfxnms` repository and place its complete text in the repository root.

Third-party dependencies and referenced projects retain their own licenses and terms. Inclusion in the technology compendium does not automatically make them license-compatible.

Do not copy BID/IDB institutional copyright, funding, liability or catalog statements into this project unless they are independently applicable and authorized.

---

## OpenTwin NMS Principles

**Open Architecture · Network Digital Twins · Simulation First · AI-Assisted Operations · SDN Interoperability · Observability · Security · Provenance · Reproducibility · Human Oversight**

> Discover the network. Model it as a digital twin. Simulate before change. Observe real behavior. Use AI to assist diagnosis and optimization. Apply controlled changes through open interfaces. Verify the result and preserve the evidence.
