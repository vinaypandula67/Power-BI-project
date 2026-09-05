# Supply Chain Analytics Dashboard (Power BI)

A single-page Power BI report that gives a quick visual overview of a company's supply chain performance revenue, costs, shipping, and supplier metrics built on one imported data table.

## Overview

This `.pbix` file contains one report page ("Page 1", 1280×720) backed by a single data table named **`supply_chain_data`**, imported directly (no relationships or additional tables the model is a flat, single-table dataset). The report was authored in Power BI (report version 5.73, PBI Desktop-compatible schema version 1.28).

## Data Model

- **Table:** `supply_chain_data`
- **Relationships:** none (single-table model)
- **Fields referenced by the visuals in this report:**
  - Product type
  - Supplier name
  - Number of products sold
  - Revenue generated
  - Costs
  - Shipping carriers
  - Shipping costs
  - Transportation modes
  - Routes
  - Customer demographics (Gender)

This field set matches the well-known "Supply Chain Analysis" sample dataset used in many BI portfolio projects (a fictional cosmetics/consumer-goods supply chain with per-product records covering pricing, sales, shipping, manufacturing, and logistics). If your source CSV/table differs, update the field names above accordingly.

## Report Contents

The page is laid out as a single dashboard with 10 visuals:

| Visual | Type | Fields |
|---|---|---|
| Total Revenue | Card | Sum of Revenue generated |
| Total Costs | Card | Sum of Costs |
| Units Sold | Card | Sum of Number of products sold |
| Shipping Costs | Card | Shipping carriers, Sum of Shipping costs |
| Costs by Transportation Mode | Clustered bar chart | Transportation modes, Sum of Costs |
| Costs by Route | Treemap | Routes, Sum of Costs |
| Revenue by Customer Demographic | Donut chart | Customer demographics (Gender), Sum of Revenue generated |
| Revenue by Transportation Mode | Funnel | Transportation modes, Sum of Revenue generated |
| Revenue by Supplier | Clustered column chart | Supplier name, Sum of Revenue generated |
| Product Type Filter | Slicer | Product type |

The **Product type slicer** acts as the primary filter, letting users drill into revenue, cost, and shipping metrics for a specific product category across all other visuals on the page.

## Key Metrics Tracked

- Total revenue generated and total costs incurred
- Units (products) sold
- Shipping cost breakdown by carrier
- Cost distribution across transportation modes and shipping routes
- Revenue split by customer demographic (gender)
- Revenue performance by supplier

## How to Use

1. Open `powerBIproj.pbix` in Power BI Desktop.
2. Use the **Product type** slicer in the top-right to filter the dashboard to a specific product category.
3. Hover over the bar, treemap, donut, funnel, and column visuals for detailed tooltips.
4. Click any data point to cross-filter the rest of the page (e.g., click a transportation mode in the bar chart to see its effect on revenue and supplier charts).

## Requirements

- Power BI Desktop (April 2024 or later recommended for full compatibility with the report/theme schema versions used).
- The underlying `supply_chain_data` table/query, if you need to refresh or repoint the data source.

## Notes

- This report has no bookmarks, additional pages, or DAX measures beyond simple `SUM()` aggregations applied directly to columns — all calculations are implicit measures created on the fly in the visuals.
- No row-level security or custom security bindings are configured.
