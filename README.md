# 📊 Employee Payroll & Workforce Analytics Dashboard

An interactive **Power BI** dashboard that analyzes employee headcount, payroll costs, and compensation breakdowns across departments, designation, gender, and time — built to give HR and finance stakeholders a single source of truth for workforce and payroll insights.

<p align="left">
  <img src="https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black"/>
  <img src="https://img.shields.io/badge/DAX-217346?style=flat-square"/>
  <img src="https://img.shields.io/badge/Power_Query-004B87?style=flat-square"/>
  <img src="https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square"/>
</p>

---

## 🎯 Objective

HR and finance teams often track headcount and payroll data across disconnected spreadsheets, making it hard to spot trends, compare departments, or explain payroll fluctuations. This dashboard consolidates employee, department, and salary data into one model to answer questions like:

- How is headcount distributed across departments, designations, and gender?
- How has payroll cost trended month over month and year over year?
- Which departments drive the most compensation cost (bonus, commission, payroll)?
- How is total payroll split by location and department?

---

## 🗂️ Data Model

The dashboard is built on a **star schema** with one fact table and three dimension tables, connected through a shared date dimension for time intelligence.

![Data Model](./screenshots/Conceptual_Model.png)

| Table | Type | Key Fields |
|---|---|---|
| `fact_salary_dataset` | Fact | BasicSalary, Allowances, Bonus, Commission, Deductions, HRA, NetSalary, SalaryDate, EmployeeID, DeptID |
| `employee_dataset` | Dimension | EmpID, EmpName, Designation, Gender, DateOfJoining |
| `dept_dataset` | Dimension | DeptID, DeptName, Location |
| `Dim Calendar` | Date Dimension | Date, Month, Year |

**Relationships:** `employee_dataset` and `dept_dataset` connect to `fact_salary_dataset` on a one-to-many basis, with `Dim Calendar` enabling time-based filtering and trend analysis across all pages.

---

## 📈 Report Pages

### 1. Executive Dashboard
High-level workforce overview: total employees by designation, gender split, and headcount trend by year.

![Employee Analysis](./screenshots/Employee_Analysis.png)

### 2. Employee Payroll
Employee-level payroll table with drill-down by name, alongside month-to-date trends for payroll, commission, and bonus.

![Employee Payroll](./screenshots/Employee_Payroll.png)

### 3. Payroll Analysis
Department-level payroll breakdown: total payroll by department ID, headcount share by department, gender distribution, and monthly payroll trend.

![Executive Dashboard](./screenshots/Executive_Dashboard.png)

### 4. Employee Payroll & Workforce Analytics (Detail View)
Filterable view combining payroll trend, commission by department, bonus by department, and total payroll by department — sliceable by Year, Gender, Location, and Department.

![Payroll Analysis](./screenshots/Payroll_Analysis.png)

---

## 🔧 What I Did

- Designed a **star-schema data model** connecting employee, department, and salary fact data through a shared calendar table
- Built **DAX measures** for payroll components (basic salary, allowances, bonus, commission, deductions, HRA, net salary)
- Built **Power Query** transformations to clean and shape the raw employee and salary datasets before loading
- Designed **4 report pages** with cross-filtering slicers (Year, Gender, Location, Department, Employee Name) for interactive exploration
- Applied consistent visual design and branding across all pages for a polished, presentation-ready dashboard

---

## 💡 Key Insights

- Headcount is concentrated in Sales and Analyst/Clerk/Manager roles, with a male-to-female split of roughly 79% to 21%
- Employee count grew steadily from 2018 through a peak in 2022, before tapering in 2023–2024
- Monthly payroll cost fluctuates within a fairly tight band (~899K–948K), with no single month consistently driving cost spikes
- HR and Accounting departments account for the largest share of commission and bonus payouts, while Operations contributes the smallest share of total payroll

---

## 🚀 How to Use

1. Download `employee_dataset.pbix` from this repo
2. Open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
3. Use the slicers (Year, Gender, Location, DeptName, EmpName) on each page to explore the data interactively

---

## 🛠️ Tools Used

`Power BI Desktop` · `DAX` · `Power Query (M)` · `Data Modeling (Star Schema)`

---

## 📁 Repo Structure

```
├── employee_dataset.pbix        # Power BI report file
├── screenshots/                 # Dashboard page exports
│   ├── Conceptual_Model.png
│   ├── Executive_Dashboard.png
│   ├── Employee_Analysis.png
│   ├── Employee_Payroll.png
│   └── Payroll_Analysis.png
└── README.md
```

---

<p align="center"><i>⭐ If you found this project useful, consider starring the repo!</i></p>
