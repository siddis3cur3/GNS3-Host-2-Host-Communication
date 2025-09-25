# GNS3-Projects
Ever wondered What it's like to mess around with networking? Here, we do exactly that.

Please understand that these are mini-projects purely for my learning experience and serves as a mind roadmap to track basics for me. These can serve as a ladder if anyone is interested in learning cloud and networking concepts with me.

# Networking Projects with GNS3

This repository documents my networking projects built with GNS3, simulating how real-world networks function.
Each project builds on the previous one, moving step by step from the basics of device communication to advanced routing, security, and cloud networking concepts.

## The goal of this repo is:

To serve as my personal networking portfolio.

To demonstrate hands-on skills in networking (useful for certifications like OCI, CCNA, etc.).

To make complex topics visual and practical through GNS3 simulations.

## Project 1 – PC-to-PC Communication


### Objective - Create a simple local area network where two PCs communicate within the same subnet.

Topology
`PC1  <------>  Switch  <------>  PC2`

### Configuration

PC1:

`ip 192.168.1.1 255.255.255.0`


PC2:

`ip 192.168.1.2 255.255.255.0`

Outcome

PC1 can ping PC2 successfully.

Demonstrates basic LAN (Layer 2) connectivity.

## Project 2 – Adding a Router Gateway

### Objective - Introduce a router to act as the gateway for the subnet, enabling routing at Layer 3.

Topology
`PC1 ---- Switch ---- Router ---- Switch ---- PC2`

### Configuration
On Router (Cisco 7200):
Copy and paste it on the terminal

`enable
configure terminal
interface fastEthernet 0/0
ip address 192.168.1.254 255.255.255.0
no shutdown
end
write memory`

On PCs:

PC1

`ip 192.168.1.1 255.255.255.0 192.168.1.254`


PC2

`ip 192.168.1.2 255.255.255.0 192.168.1.254`

Outcome

Both PCs reach the router gateway (192.168.1.254).

PC1 and PC2 communicate through the router.

Demonstrates the role of a default gateway in networking.


### Takeaways

Project 1: Proved end-to-end communication in a subnet.

Project 2: Showed how gateways enable routing and external communication.

Both projects mirror cloud networking concepts used in platforms like OCI VCNs.

###  Next Projects

Project 3: Multiple Subnets & Routing Between Them

Project 4: ACLs & Security Controls

Project 5: Simulating Internet with NAT
