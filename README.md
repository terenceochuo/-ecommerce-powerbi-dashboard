# E-commerce Sales Dashboard

This is an interactive sales dashboard built in Power BI to analyze sales, profit, and quantity trends across categories, regions, and shipping types.

## Key Features
- YTD Sales, Profit, Quantity, and Profit Margin
- YoY and PY comparisons using DAX time intelligence
- Sales by Category, State, and Region
- Top & Bottom Products
- Shipping method performance
## DAX calculations used
To calculate YTD Sales :
####  YTD Sales = TOTALYTD(SUM(ecommerce_data[sales_per_order]),'Calendar'[Date])

#### YTD Profit = TOTALYTD(SUM(ecommerce_data[profit_per_order]),'Calendar'[Date])

#### YTD Quantity = TOTALYTD(SUM(ecommerce_data[order_quantity]),'Calendar'[Date])

#### YTD Profit Margin = TOTALYTD(ecommerce_data[Profit Margin],'Calendar'[Date])

#### PYTD Sales = CALCULATE(SUM(ecommerce_data[sales_per_order]),DATESYTD(SAMEPERIODLASTYEAR('Calendar'[Date])))

#### PYTD Quantity = CALCULATE(SUM(ecommerce_data[order_quantity]),DATESYTD(SAMEPERIODLASTYEAR('Calendar'[Date])))

#### PYTD Profit Margin = CALCULATE([Profit Margin],DATESYTD(SAMEPERIODLASTYEAR('Calendar'[Date])))

#### PYTD Profit = CALCULATE(SUM(ecommerce_data[profit_per_order]),DATESYTD(SAMEPERIODLASTYEAR('Calendar'[Date]))) 

#### Profit Margin = SUM(ecommerce_data[profit_per_order])/SUM(ecommerce_data[sales_per_order])

#### YoY Sales = ([YTD Sales]-[PYTD Sales])/[PYTD Sales]

#### YoY Quantity = ([YTD Quantity]-[PYTD Quantity])/[PYTD Quantity]

#### YoY Profit = ([YTD Profit]-[PYTD Profit])/[PYTD Profit]

#### YoY Profit Margin = ([YTD Profit Margin]-[PYTD Profit Margin])/[PYTD Profit Margin]

#### Calendar = CALENDAR(MIN(ecommerce_data[order_date]),MAX(ecommerce_data[order_date]))
#### Year = YEAR('Calendar'[Date])
#### Month Number = MONTH('Calendar'[Date])
#### Month = FORMAT('Calendar'[Date],"mmmm")

## Insights
| Metric            | Value    | YoY Change | Insight                                                                         |
| ----------------- | -------- | ---------- | ------------------------------------------------------------------------------- |
| **YTD Sales**     | \$11.53M | 🔻 -0.83%  | Slight decline in sales compared to last year.                                  |
| **YTD Profit**    | \$1.34M  | 🔺 +4.50%  | Profit has increased — suggests better cost control or pricing strategy.        |
| **YTD Quantity**  | 107K     | 🔻 -7.29%  | Sales volume has dropped significantly — demand may be falling.                 |
| **Profit Margin** | 11.58%   | 🔺 +5.37%  | Higher profitability despite lower quantity and sales — operational efficiency? |

| Category            | YTD Sales | YoY Change | Insight                                                         |
| ------------------- | --------- | ---------- | --------------------------------------------------------------- |
| **Furniture**       | \$2.52M   | 🔺 +0.73%  | Modest growth — potential stable category.                      |
| **Office Supplies** | \$6.92M   | 🔻 -1.22%  | Largest contributor to sales, but declining.                    |
| **Technology**      | \$2.10M   | 🔻 -1.37%  | Declining despite being a high-value sector — revisit strategy. |

| Region      | Contribution | Insight                                           |
| ----------- | ------------ | ------------------------------------------------- |
| **West**    | 32.22%       | Leading region — strong customer base here.       |
| **East**    | 28.42%       | Also a key market — maintain efforts.             |
| **Central** | 23.19%       | Moderate performance — room for growth.           |
| **South**   | 16.17%       | Lowest contribution — potential improvement zone. |

| Shipping Type      | % of Sales | Insight                                               |
| ------------------ | ---------- | ----------------------------------------------------- |
| **Standard Class** | 60.51%     | Dominant method — efficient but worth evaluating SLA. |
| **Second Class**   | 19.71%     | Consider if this adds value or cost unnecessarily.    |
| **First Class**    | 15.1%      | Likely used for high-value/urgent shipments.          |

🎯 Strategic Recommendations
Investigate Quantity Decline: Sales units are down ~7.3% — identify if it's due to pricing, market competition, or reduced promotions.

Capitalize on Improved Margins: With profit margins up, maintain cost efficiencies while boosting sales volume.

Boost Underperforming Regions: Target the South and Central regions with geo-targeted marketing.

Reevaluate Product Mix: Shift focus to top-selling items while discontinuing or improving low sellers.

Category Strategy: Office Supplies are key — prevent further decline through bundling or pricing adjustments.


## Tools Used
- Power BI Desktop
- DAX
- Time Intelligence Functions
- Data Modeling & Visual Design

## Screenshot
![Dashboard Preview](https://github.com/terenceochuo/-ecommerce-powerbi-dashboard/blob/59eede1586143eee9e5639b26310c1c63dba3a96/dashboard-screenshot.png.PNG)

