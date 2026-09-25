# SAM-Data-Reconciliation-Model
SAM-Data-Reconciliation-Model
# Enterprise Software Asset Management (SAM) & Data Reconciliation Model

## Overview
This repository contains a data reconciliation, asset normalization, and license compliance model designed for enterprise IT Asset Management (ITAM) and Software Asset Management (SAM) governance workflows.

The project evaluates a 100-row enterprise software deployment dataset (`SAM_Entitlement_Reconciliation_Model.xlsx`) against procurement contracts, normalizes multi-platform discovery feeds, isolates non-compliant assets, and quantifies financial risk and software harvesting opportunities.

---

## Business Impact & Analysis Highlights
* **Dataset Scope:** Reconciled 100 active deployment records across core enterprise vendors, including Oracle, Microsoft, SAP, Adobe, Splunk, Autodesk, Docker, and VMware.
* **Audit Exposure Identified:** Isolated **10 non-compliant software instances** across Finance, IT Infrastructure, Operations, HR, Security, and Data Analytics.
* **Financial Risk Quantified:** Calculated **$74,150 USD** in total non-compliant financial exposure and potential license harvesting savings (highlighted by unlicensed Oracle Database 19c, Microsoft SQL Server Enterprise, and SAP ERP Core deployments).

---

## Technical Deliverables & Methodology

### 1. Data Normalization & Asset Alignment
* Standardized raw deployment discovery attributes across multi-platform endpoints (Servers, Laptops, Desktops, Virtual Machines).
* Aligned records across 10 normalized parameters: `Asset_ID`, `Vendor`, `Software_Title`, `Department`, `Deployment_Status`, `Device_Type`, `Installed_Licenses`, `Entitled_Licenses`, `License_Cost_USD`, and `Compliance_Status`.

### 2. Automated Compliance Logic
Implemented conditional evaluations to classify asset records into explicit governance states:
* **Compliant:** Active installations backed by valid entitlement contracts ($Installed \le Entitled$).
* **Non-Compliant:** Active deployments exceeding entitlements ($Installed > Entitled$) OR active software instances flagged as `Inactive` on user endpoints without license coverage.

### 3. Executive Summaries & Metric Reporting (`Software_Compliance_Summary`)
Structured an Excel PivotTable summary sheet to deliver multi-dimensional reporting:
* **Compliance Matrix by Department:** Cross-tabulated non-compliant software titles against business units (Finance, Operations, Security, IT Infrastructure) to prioritize true-up and harvesting remediation.
* **Vendor Financial Exposure:** Aggregated total unit cost liability per vendor to guide procurement renewals and true-up negotiations.
* **License Harvesting Queue:** Isolated inactive installations for immediate account deactivation and entitlement reclamation.

---

## Technical Stack & Platforms Modeled
* **Data Processing & Analytics:** SQL (Data Querying, Table Joins & Normalization Logic), Microsoft Excel (PivotTables, Multi-Variable Filters, Conditional Formulas)
* **ITAM & Endpoint Platforms Modeled:** ServiceNow SAM Pro, ServiceNow CMDB (IRE Rules & CSDM 4.0), Microsoft Intune, Azure AD (Entra ID), Apple One, SCCM, SolarWinds Service Desk
