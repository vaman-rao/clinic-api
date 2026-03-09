# Cloud-Native Monitoring and Alerting Bootcamp
## Prometheus + Grafana for Kubernetes & Microservices

---

| Field | Details |
|---|---|
| **Client** | Oracle |
| **Vendor** | The Skill Enhancers |
| **Trainer** | Vaman Rao Deshmukh |
| **Mode** | VILT (Virtual Instructor-Led Training) |
| **Dates** | 09th March 2026 – 13th March 2026 |
| **Duration** | 5 Days · 9 AM – 5 PM IST |
| **Audience** | Freshers |
| **Approach** | Hands-on, industry-standard, enterprise-focused |

---

## About This Bootcamp

This repository contains the complete learner's guide for the five-day **Cloud-Native Monitoring and Alerting Bootcamp**. Every concept is paired with hands-on labs built around a realistic reference application — the **ClinicCare Microservices Platform** — a multi-service Spring Boot system that manages patients, appointments, doctors, billing, and notifications.

By working with a single, coherent application across all five days, you will see how monitoring decisions made on Day 1 pay dividends when you are building production dashboards on Day 4 and designing alerting strategies on Day 5.

---

## Repository Structure

```
.
├── 00-README.md          ← This file — overview, prerequisites, lab setup
├── 01-day1.md            ← Observability & Prometheus Fundamentals
├── 02-day2.md            ← Advanced PromQL & Microservice Instrumentation
├── 03-day3.md            ← Alerting & Alertmanager
├── 04-day4.md            ← Grafana & Kubernetes Monitoring
├── 05-day5.md            ← Production Architecture & Capstone Project
```

---

## The ClinicCare Reference Application

ClinicCare is a fictional clinic management platform composed of five Spring Boot microservices:

| Service | Responsibility |
|---|---|
| `patient-service` | Patient registration, profile management, records |
| `appointment-service` | Scheduling, rescheduling, cancellation |
| `doctor-service` | Doctor profiles, availability, specialisations |
| `billing-service` | Invoice generation, payment tracking |
| `notification-service` | Email / SMS dispatch for appointments and bills |

Each service exposes:
- A REST API on a dedicated port
- Spring Boot Actuator at `/actuator/prometheus`
- Custom business metrics via Micrometer

### Port Allocation (used across all labs)

| Component | Port |
|---|---|
| `patient-service` | 8081 |
| `appointment-service` | 8082 |
| `doctor-service` | 8083 |
| `billing-service` | 8084 |
| `notification-service` | 8085 |
| Prometheus | 9090 |
| Alertmanager | 9093 |
| Grafana | 3000 |

---

## Prerequisites

Participants are expected to have working knowledge of:

- **Linux command line** — processes, networking, file system basics
- **Docker** — images, containers, volumes, networking
- **Kubernetes** — pods, deployments, services, namespaces
- **YAML** configuration files
- **Basic REST API** understanding
- **Java / Spring Boot** fundamentals

---

## Lab Setup Requirements

### Minimum Hardware
- 64-bit system (Intel i5 or equivalent recommended)
- 16 GB RAM
- 100 GB free disk space

### Software
- Windows 11 / macOS
- Internet connection ≥ 50 Mbps

### Required Applications

| Tool | Version |
|---|---|
| Docker | Latest stable |
| Kubernetes | Minikube **OR** Kind |
| kubectl CLI | Matches cluster version |
| Helm | v3+ |
| Git | Latest |
| Java | 17+ |
| VS Code | Latest — with YAML & Kubernetes extensions |

> **NOTE:** Prometheus, Grafana, and Alertmanager will be installed **during labs** using Docker and Helm. Do **NOT** pre-install them manually.

### Permissions
- Access to GitHub repositories

---

## Pre-Bootcamp Validation Checklist

Before Day 1, confirm each item works on your laptop:

- [ ] `docker run hello-world` completes successfully
- [ ] `minikube start` (or `kind create cluster`) brings up a cluster
- [ ] `kubectl get nodes` shows a Ready node
- [ ] `helm repo add stable https://charts.helm.sh/stable` succeeds
- [ ] `kubectl run nginx --image=nginx` creates a Running pod

---

## Learning Objectives

By the end of this bootcamp, participants will be able to:

1. Understand observability in cloud-native systems
2. Install and configure Prometheus
3. Write advanced PromQL queries
4. Instrument Java microservices with Micrometer
5. Monitor Kubernetes clusters
6. Create production-grade dashboards in Grafana
7. Configure alerting with Alertmanager
8. Design monitoring architecture for production systems

---

## Five-Day Schedule at a Glance

| Day | Theme | Key Deliverable |
|---|---|---|
| **Day 1** | Observability & Prometheus Fundamentals | Running Prometheus scraping Node Exporter; PromQL basics |
| **Day 2** | Advanced PromQL & Microservice Instrumentation | Instrumented Spring Boot app with recording rules |
| **Day 3** | Alerting & Alertmanager | Firing alerts routed to Slack / email |
| **Day 4** | Grafana & Kubernetes Monitoring | Production dashboards on kube-prometheus-stack |
| **Day 5** | Production Architecture & Capstone | Full ClinicCare monitoring stack with failure simulation |

---

## Lab Architecture (Local Laptop Model)

```
Spring Boot Microservices (ClinicCare)
        │
        │  /actuator/prometheus (HTTP)
        ▼
    Prometheus  ──────────────► Alertmanager ──► Slack / Email
        │
        ▼
     Grafana (Dashboards)

Deployed on: Local Kubernetes cluster (Minikube / Kind) via Helm charts
```

---

## How to Use This Guide

- Each day file (`01-day1.md` through `05-day5.md`) covers theory, worked examples, lab exercises, and homework.
- Code blocks are copy-paste ready. All examples reference ClinicCare services for consistency.
- Lab exercises progress in complexity; complete them in order.
- End-of-day summaries provide a quick revision checklist.

---

*Maintained by The Skill Enhancers · Oracle Bootcamp March 2026*
