# Splunk-Home-Lab

## Overview
Built a security monitoring lab using Splunk Enterprise on Ubuntu Linux to simulate 
real-world SOC analyst workflows, including log ingestion, attack simulation, 
and automated threat detection.

## Tools & Technologies
- Splunk Enterprise
- Ubuntu Linux
- Hydra
- OpenSSH
- SPL (Splunk Processing Language)

## What I Built

### Log Ingestion
- Configured Splunk to monitor and index live Linux authentication logs (`/var/log/auth.log`)
- Set up real-time ingestion pipeline from system logs into Splunk indexer

### Attack Simulation
- Installed and configured OpenSSH server on Ubuntu
- Used Hydra to simulate SSH brute force attacks against localhost
- Generated realistic failed login events captured by Splunk in real time

### Detection Dashboard
Built a multi-panel dashboard titled **Linux Auth Monitor** with the following panels:
- **Failed Login Attempts Over Time** — timechart of failed SSH logins
- **Total Failed Logins** — aggregate count of failed attempts
- **Top Targeted Usernames** — most frequently targeted accounts
- **Failed Logins by Source IP** — tracks attacker IP addresses

### Automated Alerting
- Created a scheduled SPL alert that triggers when failed login attempts exceed a threshold
- Alert runs every 15 minutes and adds to Triggered Alerts for review

## Key SPL Queries

**Detect brute force activity:**
