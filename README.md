# Demand-planning-project
This repository demonstrates how to build a *baseline demand forecast* for multiple products using **Excel only**. 
It uses **dummy data** and transparent formulas to showcase the logic I'd apply in a demand-planning workflow

---

## What this file does

- Provides a clean template for **baseline forecasting** across products and months
- Includes sheets for **Raw Data**, **Calculations**, **Seasonality**, **Baseline Forecast**, and **Charts**
- Show how to transform historical sales into a **repeatable, auditable baseline** that planners can align around

---

## Methods Used 

### 1) Forecasting Framework
**Final Forecast = Baseline Forecast + Uplifts**
#### 1. Baseline Forecast
- **Category level** (not SKU) to minimize forecast error:
- Forecasting at a very detailed SKU level increases variability and error rates
- Category aggregation provides a more stable demand signal, which can later be split down to SKUs if needed
- Derived from **historical sales trend**:
- Start with raw sales (often noisy and fluctuating)
- Subtract known building blocks (promotion spikes, price increases, distribution expansions, marketing campaigns)

### 2) Moving Average (MA) 
-Smooth short-term fluctuations and highlight the trend 
-Example (3-month MA): 
=AVERAGE(OFFSET[@Actuals],0,-1), OFFSET([@Actuals],0,-2), OFFSET[[@Actuals],0,-3)
-Why: Simple, robust starting point when seasonality is mild or data is noisy. 

---

## Business Value

- **Improves accuracy:** separating baseline from uplifts reduces bias and noise
- **Supporting collaboration"** baseline comes from data, uplifts from Sales/Marketing ensure alignment
- **Transparent:** category-level baseline is stable, while uplifts capture business realities
- **Foundation for advanced models:** provides a benchmark against which more complex statistical/ML models can be compared
