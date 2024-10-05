# Oily Giant Oil Drilling

## Table of Contents

- [Project Objective](#project-objective)
- [Project Structure and Steps](#project-structure-and-steps)
  - [1. Data Preparation](#1-data-preparation)
  - [2. Model Training and Validation](#2-model-training-and-validation)
  - [3. Profit Calculation Preparation](#3-profit-calculation-preparation)
  - [4. Calculating Profit for Selected Wells](#4-calculating-profit-for-selected-wells)
  - [5. Risk and Profit Analysis](#5-risk-and-profit-analysis)
- [Tools and Techniques Utilized](#tools-and-techniques-utilized)
- [Specific Results and Outcomes](#specific-results-and-outcomes)
  - [Data Preparation and Feature Engineering](#data-preparation-and-feature-engineering)
  - [Model Performance by Region](#model-performance-by-region)
  - [Profit Calculation Analysis](#profit-calculation-analysis)
  - [Selection of Top Wells](#selection-of-top-wells)
  - [Profit and Risk Estimation Using Bootstrapping](#profit-and-risk-estimation-using-bootstrapping)
- [Final Recommendations](#final-recommendations)
- [Key Observations](#key-observations)
- [What I Have Learned from This Project](#what-i-have-learned-from-this-project)

## Project Objective

The goal of this project is to find the best locations for developing new oil wells for the company OilyGiant. By analyzing geological data from three regions, we aim to build a model to predict the volume of reserves in new wells, select the most profitable wells, and identify the region with the highest overall profit potential for well development.

[back to top](#oily-giant-oil-drilling)

## Project Structure and Steps
**1. Data Preparation:**
- Load and examine the datasets containing parameters collected from oil wells in three different regions.
- Clean and prepare the data for model training, ensuring all relevant variables are in the appropriate format for analysis.

**2. Model Training and Validation:**
- For each of the three regions, the data was split into training (75%) and validation (25%) sets.
- A linear regression model was trained on the training set to predict the volume of reserves in new wells.
- Predictions were made on the validation set, and the mean volume of reserves and RMSE (Root Mean Squared Error) were calculated to evaluate the model's performance.
- A function was created to automate the process of model training and evaluation for all three regions.

**3. Profit Calculation Preparation:**
- Calculate the minimum volume required per well to avoid losses, based on a $100 million budget for the development of 200 wells.
- Assess the mean volume per well for each region to determine profitability potential.

**4. Calculating Profit for Selected Wells:**
- Create a function to calculate the profit from selected wells based on model predictions.
- Select the top 200 wells with the highest predicted reserves for each region.
- Calculate the total profit for the 200 wells and provide recommendations on which region to develop based on profitability.

**5. Risk and Profit Analysis:**
- Use bootstrapping with 1,000 samples to analyze profit distributions.
- Calculate the average profit, 95% confidence intervals, and the risk of losses (defined as a negative profit) for each region.
- Provide final recommendations on which region is most suitable for oil well development based on both profit potential and risk  assessment.

[back to top](#oily-giant-oil-drilling)

## Tools and Techniques Utilized

- Data Processing: pandas, numpy
- Modeling: Scikit-learn for linear regression modeling
- Profit Analysis and Optimization: Bootstrapping technique for risk and profit evaluation
- Visualization: Matplotlib, Seaborn for plotting distributions and model performance
- Statistical Metrics: RMSE for model evaluation, 95% confidence intervals, and risk probability calculations

[back to top](#oily-giant-oil-drilling)

## Specific Results and Outcomes

**Data Preparation and Feature Engineering:**
- Three datasets (geo_data_0.csv, geo_data_1.csv, and geo_data_2.csv) were explored, each representing different regions with oil well data.
- Features included in each dataset: f0, f1, f2 (geological parameters), and product (volume of reserves in thousands of barrels).
- No significant data quality issues were identified, allowing for smooth progression to model training.

**Model Performance by Region:**
- **Region 0**: The linear regression model achieved a predicted average volume of 92.5 thousand barrels with an RMSE of 37.6 thousand barrels.
- **Region 1:** The model performed better with a predicted average volume of 68.8 thousand barrels and an RMSE of 0.89 thousand barrels, indicating low prediction error.
- **Region 2:** Predictions resulted in an average volume of 94.9 thousand barrels with an RMSE of 40.0 thousand barrels.

**Profit Calculation Analysis:**
- The budget for developing 200 wells per region was set at $100 million. Each well needed to generate a minimum of 111.1 thousand barrels to avoid losses.
- Region 0 had an average well production slightly below the threshold, indicating potential profitability issues.
- Region 1 had a lower average volume but the highest profit margin per well due to more consistent production.
- Region 2 had a high average volume but also higher variability, leading to a mixed profit potential.

**Selection of Top Wells:**
- The top 200 wells were selected based on the highest predicted reserves for each region.
- Region 1 emerged as the region with the most consistent profit due to low variance and stable well output.

**Profit and Risk Estimation Using Bootstrapping:**
- Bootstrapping with 1,000 samples was used to calculate profit distributions and assess risks for each region.
- Region 0:
  - Average profit: $32 million
  - 95% confidence interval: $-3.1 million to $56.1 million
  - Risk of loss (negative profit): 6.2%
- Region 1:
  - Average profit: $46 million
  - 95% confidence interval: $37.2 million to $53.8 million
  - Risk of loss: 0.7%
- Region 2:
  - Average profit: $28 million
  - 95% confidence interval: $-10 million to $50 million
  - Risk of loss: 7.4%

**Final Recommendations:**
- Region 1 was recommended for oil well development as it had the highest average profit and the lowest risk of losses (below the 2.5% threshold).
- The results confirmed that Region 1 was consistently profitable and carried minimal risk, aligning with business requirements for sustainable investment.

**Key Observations**
- Region 1 outperformed the other regions in terms of profit margin and consistency, despite having a lower average volume of reserves per well.
- The variability in predictions (indicated by RMSE) had a significant impact on profit potential, as regions with higher RMSE showed higher risk and lower average profit.
- The bootstrapping method provided robust insights into the potential risks and profitability of developing oil wells in each region, helping make informed business decisions.
- These outcomes led to the conclusion that focusing development efforts on Region 1 would maximize profit while minimizing risk.

[back to top](#oily-giant-oil-drilling)

## What I Have Learned from This Project
- **Data Analysis and Cleaning**: Efficiently handled data preparation and ensured proper formatting for analysis.
- **Model Training and Evaluation**: Developed strong skills in building and validating regression models to predict numerical outcomes.
- **Profit Calculation and Risk Analysis**: Gained experience in calculating potential profits and evaluating risks using statistical techniques such as bootstrapping.
- **Business-Oriented Decision Making**: Learned to integrate data science techniques with business conditions to make informed decisions on investment and development strategies.

[back to top](#oily-giant-oil-drilling)