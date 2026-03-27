# 🚀 End-to-End Data Engineering Pipeline using Snowflake

## 📌 Project Overview

This project demonstrates the design and implementation of a **scalable, end-to-end data pipeline in Snowflake** using a modern **Medallion Architecture (RAW → STAGING → CORE → ANALYTICS)**.

The pipeline ingests structured data from Snowflake’s TPCH dataset, processes it incrementally using **Streams and Tasks**, applies **SCD Type 2 transformations**, and builds optimized analytical models. The project also includes **Dynamic Tables, Security Policies, and Performance Optimization techniques**.

---

## 🧠 Architecture Overview

The pipeline follows a layered approach:

**Source → RAW → STAGING → CORE → ANALYTICS → Consumption**

* **RAW Layer** → Stores ingested data (unaltered)
* **STAGING Layer** → Cleans and prepares incremental data
* **CORE Layer** → Applies business logic (SCD Type 2)
* **ANALYTICS Layer** → Star schema + aggregated models

Key components:

* **Streams** → Capture incremental changes (CDC)
* **Tasks** → Automate pipeline execution
* **Dynamic Tables** → Near real-time transformations

---

## ⚙️ Key Features

### 🔹 1. Data Ingestion

* Used **CTAS (CREATE TABLE AS SELECT)** to load TPCH data into RAW layer
* Simulated real-world ingestion using **internal stages and CSV export/import**

---

### 🔹 2. Incremental Processing (CDC)

* Implemented **Streams** on RAW tables to track changes
* Used **Tasks** to automate ingestion into STAGING
* Eliminated full reloads → improved efficiency

---

### 🔹 3. SCD Type 2 Implementation

* Built **historical tracking** in CORE layer
* Maintains:

  * Active records (`IS_ACTIVE`)
  * Start/End timestamps
* Ensures **data lineage and auditability**

---

### 🔹 4. Automated Pipeline (Stored Procedure)

* Developed a **SQL stored procedure** for:

  * Loading incremental data
  * Applying SCD2 logic
  * Logging execution metrics
* Enables **controlled and repeatable ETL execution**

---

### 🔹 5. Data Modeling (Star Schema)

* Designed **Fact and Dimension tables**
* Used **surrogate keys** for optimized joins
* Supports scalable analytics workloads

---

### 🔹 6. Dynamic Tables (Near Real-Time Processing)

* Built **auto-refreshing tables** using Dynamic Tables
* Implemented **incremental refresh optimization**
* Improved performance by replacing FLOAT with NUMBER

---

### 🔹 7. Security Implementation

* **Row-Level Security (RLS)** → restrict data by region
* **Masking Policies** → protect sensitive fields (phone numbers)
* **Secure Data Sharing** → share datasets without duplication

---

### 🔹 8. Performance Optimization

* Implemented **clustering on DATE_KEY**
* Reduced query scan and improved performance
* Designed pipeline for **cost-efficient compute usage**

---

## 🏗️ Tech Stack

* **Cloud Data Warehouse** → Snowflake
* **Language** → SQL
* **Concepts** → CDC, SCD Type 2, Star Schema
* **Orchestration** → Snowflake Tasks
* **Real-time Processing** → Dynamic Tables

---

## 📊 Key Engineering Concepts Demonstrated

* Incremental Data Processing (CDC)
* Data Warehouse Layering (Medallion Architecture)
* Slowly Changing Dimensions (SCD Type 2)
* Pipeline Automation & Scheduling
* Data Security & Governance
* Query Performance Optimization

---

## ⚠️ Challenges & Learnings

* Handling **schema mismatch and surrogate key joins**
* Managing **stream consumption and incremental logic**
* Understanding **FLOAT vs NUMBER impact on dynamic tables**
* Designing **efficient joins for large-scale fact tables**

---

## 🚀 Future Improvements

* Integrate **external stages (AWS S3 / Azure Blob)**
* Implement **error handling and retry mechanisms**
* Add **workflow orchestration (Airflow / dbt)**
* Introduce **real-time streaming ingestion**

---

## 🎯 Conclusion

This project demonstrates a **production-ready Snowflake data pipeline** with:

* Scalable architecture
* Automated incremental processing
* Strong data governance
* Optimized performance

It reflects real-world data engineering practices used in modern cloud data platforms.

---
