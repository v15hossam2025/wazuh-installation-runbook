# Wazuh SIEM Installation & Agent Enrollment Runbook

A practical security engineering runbook for deploying Wazuh SIEM and onboarding infrastructure assets into centralized security monitoring.

## 🌐 Live Interactive Runbook

> The interactive HTML version of this project can be published through GitHub Pages.

## Overview

This project provides a reusable reference for implementing a Wazuh-based security monitoring environment.

The runbook focuses on practical deployment, agent onboarding, telemetry collection, and validation activities that can be adapted for SOC environments.

## Covered Areas

- Wazuh Manager deployment
- Wazuh Indexer deployment
- Wazuh Dashboard deployment
- Linux agent enrollment
- Windows agent enrollment
- Sysmon integration
- Windows security telemetry
- Agentless Syslog collection
- Web Application Firewall log forwarding
- VPN gateway log forwarding
- Firewall and network connectivity requirements
- Post-installation validation

## Architecture

```text
                         +----------------------+
                         |      Wazuh SIEM      |
                         |                      |
                         |  Manager / Indexer   |
                         |  Dashboard           |
                         +----------+-----------+
                                    |
              +---------------------+---------------------+
              |                     |                     |
              v                     v                     v
       +-------------+       +-------------+       +-------------+
       |   Linux     |       |   Windows   |       |  Security   |
       |   Servers   |       |   Servers   |       | Infrastructure|
       +-------------+       +------+------+       +-------------+
                                    |
                                  Sysmon
                                    |
                                    v
                             Windows Telemetry

       Security Infrastructure
                |
                +---- Syslog ----> Wazuh
