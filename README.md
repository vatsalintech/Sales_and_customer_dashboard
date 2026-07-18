# Sales & Customer Dashboards

Interactive Tableau workbook for exploring retail sales performance and customer behavior across the United States (non-EU Superstore-style data).

Link for Tableau Public - https://public.tableau.com/app/profile/vatsal.shah8881/viz/SalesCustomerDashboards_17748174293690/SalesDashboard

Link for GitHub repository - https://github.com/vatsalintech/Sales_and_customer_dashboard

## Dashboards

| Dashboard | Purpose |
| --- | --- |
| **Sales Dashboard** | Year-over-year KPIs, subcategory comparison, and weekly sales trends |
| **Customer Dashboard** | Customer volume, order frequency distribution, and top customers |

### Sales Dashboard

- KPI cards for **Sales**, **Profit**, **Quantity**, and **Sales per Customer**, each with current-year vs previous-year comparison
- **Subcategory Comparison** — performance by product subcategory (click to filter)
- **Weekly Trends** — sales over the selected year (click to filter)

### Customer Dashboard

- KPI cards for **Customers** and **Orders**, with year-over-year change
- **Customer Distribution** — how customers cluster by number of orders
- **Top Customers** — highest-value or most active customers

Both dashboards share a **Select Year** parameter (`2020`–`2023`) and use filter actions so chart selections update related views.

## Data

Source CSVs live under `datasets/non-eu/`. They are joined in Tableau as **Sales DataSource**:

```
Orders  ──Customer ID──►  Customers
Orders  ──Postal Code──►  Location
Orders  ──Product ID───►  Products
```

| File | Rows | Contents |
| --- | ---: | --- |
| `Orders.csv` | ~9,994 | Order lines: dates, segment, ship mode, sales, quantity, discount, profit |
| `Customers.csv` | ~793 | Customer ID and name |
| `Products.csv` | ~1,894 | Category, sub-category, product name |
| `Location.csv` | ~632 | City, state, region, country (United States) |

**Coverage**

- Years: 2020–2023  
- Segments: Consumer, Corporate, Home Office  
- Categories: Furniture, Office Supplies, Technology  
- Regions: Central, East, South, West  

## Project structure

```
.
├── Sales & Customer Dashboards.twbx   # Packaged workbook (open this)
├── datasets/
│   └── non-eu/
│       ├── Orders.csv
│       ├── Customers.csv
│       ├── Products.csv
│       └── Location.csv
├── images/                            # Dashboard navigation / UI icons
└── README.md
```

## Getting started

**Easiest:** open the [live dashboard on Tableau Public](https://public.tableau.com/app/profile/vatsal.shah8881/viz/SalesCustomerDashboards_17748174293690/SalesDashboard).

**Locally:**

1. Clone or download this [GitHub repo](https://github.com/vatsalintech/Sales_and_customer_dashboard).
2. Install [Tableau Desktop](https://www.tableau.com/products/desktop) or [Tableau Public](https://public.tableau.com/).
3. Open `Sales & Customer Dashboards.twbx` (**File → Open**).
4. Use **Select Year** and click charts to filter related views.

### Refreshing data from CSVs

If you edit the files in `datasets/non-eu/`:

1. Open the workbook in Tableau Desktop.
2. Go to the **Sales DataSource** and reconnect or replace the text files as needed.
3. Refresh extracts, then save a new `.twbx` if you want the packaged file updated.