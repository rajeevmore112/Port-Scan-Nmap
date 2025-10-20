# Port-Scan-Nmap
Author: Rajeev More
Date: 2025-10-20  
Task: Local network port scan using Nmap (TCP SYN scan)

## Summary 
Performed an Nmap TCP SYN scan on my local network (192.168.29.0/24) to discover exposed services and assess basic security risks. 
Found the gateway exposing HTTP/HTTPS/UPnP and several hosts with SMB/RTSP services.

## Command Used
```bash
nmap -sS 192.168.xx.0/XX
nmap -sS 192.168.xx.0/XX -oN scan_results.txt
```

## Key Findings 
 192.168.xx.x (gateway): 80/tcp (http), 443/tcp (https), 1900/tcp (upnp), 8080/tcp, 8443/tcp — gateway web/management services exposed.
 192.168.xx.xx: 554/tcp (rtsp) — likely a camera/media device.
 192.168.xx.xx & 192.168.xx.xxx: 135/tcp, 139/tcp, 445/tcp, 5357/tcp — SMB/NetBIOS services (high risk if unpatched or using default creds).
 192.168.xx.xxx: No open ports found in the scanned set.

## Repo Contents
├── README.md
├── scan_results.txt        # CMD Nmap output (from -oN) (REDACTED MACs AND IP ADDRESSES AS THEY WERE PERSONAL)
├── TCP SYN Scan.jpg        # terminal screenshot (REDACTED MACs AND IP ADDRESSES AS THEY WERE PERSONAL)

##Wireshark Analysis
I attempted to capture and analyze packets using Wireshark during the Nmap TCP SYN scan.
While I successfully captured network traffic, I wasn’t able to interpret or filter the packets effectively this time.
I plan to revisit Wireshark with proper filters.
