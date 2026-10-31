# 📈 Qlik Sense & Qlik Cloud Projects Portfolio

> Advanced Qlik Sense dashboards built for Poulta Inc — a large poultry enterprise. Covers HR management, workforce operations, breeder/broiler farm tracking, hiring pipelines, and deployment monitoring. Built with advanced Set Analysis, REST API integration, and multi-source data pipelines.

---

## 🏢 About the Context

All dashboards below were built for **Poulta Inc** — an integrated poultry company with operations spanning farms, hatcheries, feedmills, and corporate HR. Data was pulled from multiple sources (PostgreSQL, MongoDB, REST APIs) and unified into Qlik's data model for cross-functional analytics.

---

## 🎯 Projects Overview

### 1. Teamwork Management System & Task Tracker Dashboard
- Real-time task assignment, status tracking, and team workload visualization
- Drill-down from department → team → individual task level
- Set Analysis for filtering completed vs pending vs overdue tasks
- KPI cards showing on-time delivery rate, avg task duration, bottlenecks

---

### 2. HRMS Dashboard (HR Management System)
- Centralized HR dashboard covering employee lifecycle: onboarding → active → exit
- Headcount trends, attrition rate, department-wise distribution
- Advanced Set Analysis for tenure bands, salary ranges, and role hierarchies
- Connected to live HR database via REST API integration

---

### 3. Hiring Dashboard
- End-to-end recruitment funnel: Applications → Screening → Interview → Offer → Joined
- Conversion rate analysis at each stage
- Time-to-hire metrics by department and role
- Source-of-hire breakdown (LinkedIn, referrals, job portals)

---

### 4. Deployment Dashboard
- Tracks employee deployment across farms, hatcheries, feedmills, and offices
- Geographic distribution visualization
- Capacity vs actual headcount per location
- Automated alerts for understaffed departments

---

### 5. Breeder Farm HR Dashboard
- Workforce management specific to breeder farm operations
- Shift scheduling, attendance tracking, and overtime analysis
- Productivity metrics linked to farm performance KPIs
- Cross-referenced with production data for correlation analysis

---

### 6. Broiler Farm HR Dashboard
- Similar to breeder dashboard — tailored for broiler farm operational metrics
- Flock cycle tracking linked to labor requirements
- Cost-per-bird labor analysis
- Integration with farm IoT data for operational context

---

## 🛠️ Tech Stack

| Tool | Usage |
|---|---|
| Qlik Sense | Main dashboard development platform |
| Qlik Cloud | Cloud deployment and sharing |
| Set Analysis | Advanced filtering and conditional aggregations |
| QlikView Script | Data load scripts, transformation logic |
| REST API Connector | Live data from PostgreSQL, MongoDB, internal APIs |
| Data Pipelines | Multi-source data ingestion and modeling |
| Section Access | Row-level security per user role |

---

## ⚡ Advanced Techniques Used

**Set Analysis:**
```
// Year-over-year comparison
Sum({<Year={$(=Year(Today())-1)}>} Sales)

// Exclude nulls, filter active employees only
Count({<Status={'Active'}, EmpID={'>0'}>} EmpID)

// Intersection of multiple conditions
Sum({<Dept={'HR'}, Month={$(=Month(Today()))}>} Headcount)
```

**Data Modeling:**
- Star schema design with HR, farm, and production fact tables
- Bridge tables for many-to-many relationships
- Incremental data loads for large operational datasets
- Cross-app data sharing via Qlik Cloud

**REST API Integration:**
- Live data pulls from internal FastAPI endpoints
- Scheduled reloads for dashboard freshness
- JSON parsing and normalization in load script

---

## 📁 Repository Structure

```
qlik-sense-projects/
├── hrms-dashboard/
│   ├── screenshots/          — Dashboard screenshots
│   ├── load-script/          — Anonymized data load scripts
│   └── README.md
├── hiring-dashboard/
│   ├── screenshots/
│   └── README.md
├── deployment-dashboard/
│   ├── screenshots/
│   └── README.md
├── breeder-hr-dashboard/
│   ├── screenshots/
│   └── README.md
├── broiler-hr-dashboard/
│   ├── screenshots/
│   └── README.md
├── task-tracker-dashboard/
│   ├── screenshots/
│   └── README.md
├── set-analysis-snippets/
│   └── advanced-expressions.md  — Reusable Set Analysis formulas
└── README.md
```

---

## 🔒 Note

All dashboards were built on **live production data** at Poulta Inc. This repository contains **screenshots, anonymized load scripts, and architecture documentation**. Raw data and credentials are excluded.

---

*Built by [Syed Fahad Fazal](https://linkedin.com/in/syed-fahad-fazal) — Data Scientist → AI Engineer @ Poulta Inc*
