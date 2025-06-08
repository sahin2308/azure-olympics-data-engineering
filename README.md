# Tokyo Olympics Data AnalysisProject 🚀

An end-to-end Azure Data Engineering project that demonstrates real-world ETL orchestration using Azure Data Factory, Azure Databricks, Delta Lake, Unity Catalog, and CI/CD with Azure DevOps. This project ingests and transforms 2024 Olympics data and makes it ready for Power BI analytics.

---

## 🔧 Tech Stack

- **Azure Data Factory (ADF)**
- **Azure DevOps (CI/CD)**
- **Azure Data Lake Storage Gen2**
- **Azure Databricks + Unity Catalog**
- **PySpark**
- **Delta Live Tables (DLT)**
- **Power BI** (for reporting layer)

---

## 📊 Project Architecture

![Architecture Diagram](./architecture/project-architecture.png)

---

## 📁 Data Sources

- **Public GitHub CSVs** (2024 Olympics)
- **Local Flat Files** (manually uploaded for demo)

---

## 🚀 Key Features

- CI/CD pipeline using Azure DevOps with Git Integration
- Parameterized data ingestion via Azure Data Factory
- Issue resolution using ADF’s fault tolerance features for schema mismatch
- Dynamic PySpark notebooks with `dbutils.jobs.taskValues`
- Bronze → Silver → Gold architecture using Delta Lake
- Delta Live Tables for curated data
- 20% improvement in pipeline performance using optimized transformations

---

## 📌 Modules Breakdown

### 1. Data Ingestion (ADF)
- Ingested from GitHub and local into **Bronze** container.
- Used ADF pipelines with Git flow: feature branch → PR → merge.

### 2. Data Transformation (Databricks)
- Connected Databricks to ADLS via Access Connector.
- Created Unity Catalog, external locations, bronze/silver/gold schemas.
- Used parameterized notebooks for scalable ingestion.

### 3. Advanced Transformations
- Performed business logic using PySpark.
- Stored transformed data in **Silver** layer.

### 4. Gold Layer (Delta Live Tables)
- Created curated views for reporting.
- Delta Live Tables used for pipeline performance and data quality.

---

## ⚙️ CI/CD (Azure DevOps)

- Feature branches used for pipeline development.
- Pull request flow with peer review.
- ARM templates exported for deployment consistency.

---

## 🐞 Real Issues Faced & Solutions

- **Schema mismatch in CSV files**: Solved via ADF Copy Activity fault tolerance → skipped incompatible rows.
- **Performance tuning**: Delta tables, Unity Catalog + DLT reduced runtime by ~20%.

---

## 📈 Power BI Reporting (Optional)
- Power BI connected to **Gold** Delta Tables.
- Reports for events, coaches, medal stats, etc.

---

## 📦 Folder Description

| Folder | Description |
|--------|-------------|
| `notebooks/` | All Databricks notebooks used for ingestion and transformation |
| `adf/` | JSON pipelines and ARM templates for ADF |
| `devops/` | CI/CD flow screenshots, PR examples |
| `delta-live-tables/` | DLT pipeline definitions |
| `architecture/` | Project diagram or flowcharts |
| `data_samples/` | Sample CSV files (sanitized) |

---

## 📜 License

MIT – feel free to use and modify.

---

## 🙋‍♂️ Author

**Sahin Saikh**  
[LinkedIn](https://www.linkedin.com/in/sahin-saikh/) | [Instagram](https://www.instagram.com/thatdataguy.in) | [Portfolio](https://overjoyed-leaf-03a.notion.site/thatdataguy-in-1da84b1a70fe8040b465fcf789b8fc3b)

---

## 🌟 If you liked this project, feel free to give it a star ⭐
