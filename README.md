# Enterprise Multi-Branch Network Design

A simulated enterprise network built using Cisco Packet Tracer, connecting a Head Office (HQ) with three remote branches through a Frame Relay WAN.

## Project Overview

This project demonstrates the design and configuration of a small enterprise network with centralized HQ connectivity and three branch LANs.

The network uses EIGRP for dynamic routing between routers and DHCP to assign IP addresses automatically to HQ computers. Branch computers use static IPv4 addressing.

## Network Topology

The topology consists of:

- 1 Head Office router
- 3 branch routers
- 4 LAN switches
- 9 PCs
- 1 Frame Relay switch

The HQ and branch routers connect through the Frame Relay WAN. Each router connects to its local LAN.

![Network topology](screenshots/network-topology.png)

## Technologies Used

- Cisco Packet Tracer
- IPv4 addressing and subnetting
- Ethernet switching
- Frame Relay WAN
- EIGRP dynamic routing
- DHCP
- Static IP configuration
- Cisco IOS verification and troubleshooting

## IP Addressing Plan

| Location | LAN Network | Default Gateway |
|---|---|---|
| HQ | 172.16.1.0/24 | 172.16.1.1 |
| Branch 1 | 192.168.1.0/24 | 192.168.1.1 |
| Branch 2 | 192.168.2.0/24 | 192.168.2.1 |
| Branch 3 | 192.168.3.0/24 | 192.168.3.1 |

### WAN Addressing

| Router | WAN IP Address |
|---|---|
| HQ | 10.1.1.4/24 |
| Branch 1 | 10.1.1.1/24 |
| Branch 2 | 10.1.1.2/24 |
| Branch 3 | 10.1.1.3/24 |

The addressing tables describe the intended design. See the Packet Tracer file and configuration notes for the final implementation.

## Main Configurations

### 1. Router Interfaces
Configured LAN and WAN interfaces with IPv4 addresses and enabled the interfaces.

### 2. Frame Relay
Configured Frame Relay encapsulation and virtual circuit mappings for WAN connectivity.

### 3. EIGRP
Configured EIGRP to exchange routing information between routers and learn remote LAN networks.

### 4. DHCP
Configured the HQ router as a DHCP server for the HQ LAN.

### 5. Branch PCs
Assigned static IPv4 addresses and the appropriate default gateways to branch computers.

## Verification and Testing

The following Cisco IOS commands were used or intended for verification:

```text
show ip interface brief
show running-config
show ip protocols
show ip eigrp neighbors
show ip route
show ip route eigrp
show frame-relay pvc
show frame-relay map
show ip dhcp pool
show ip dhcp binding
```

Connectivity can be tested from PC Command Prompt using `ping`.

See the `screenshots/` directory for evidence of the actual topology and verification results.

## Project Files

- `Enterprise_Multi_Branch_Network.pkt` — Packet Tracer simulation.
- `configs.txt` — router configurations and verification notes.
- `screenshots/` — topology and test screenshots.

## Learning Outcomes

- Designed a multi-branch network topology.
- Practiced IPv4 addressing and subnetting.
- Configured dynamic routing with EIGRP.
- Practiced DHCP configuration.
- Worked with Frame Relay WAN concepts and DLCI mappings.
- Used Cisco IOS commands to verify network status and troubleshoot connectivity.

## How to Open the Project

1. Download `Enterprise_Multi_Branch_Network.pkt`.
2. Open Cisco Packet Tracer.
3. Open the downloaded `.pkt` file.
4. Inspect the topology and run connectivity tests.

## Author

Networking project completed as part of my Cisco CCNA self-study and practical networking development.
