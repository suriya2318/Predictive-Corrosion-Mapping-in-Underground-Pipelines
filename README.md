# Predictive Corrosion Mapping in Underground Pipelines
## Project Objective
The aim of this project is to detect early-stage underground pipeline corrosion using sensor data (GPR, Soil pH, Temperature, and Moisture) and predict corrosion hotspots through a machine learning pipeline entirely built in Microsoft Excel. This helps pipeline maintenance teams to proactively intervene, prevent leakage, reduce repair costs, and improve infrastructure lifespan.

## Problem Statement 
Underground pipelines transporting water and gas are vulnerable to hidden corrosion beneath insulation layers. Studies reveal:

• Corrosion accounts for 12% of pipeline leaks.

• It causes $50 billion in repair costs annually.

• Traditional manual inspections fail to detect 70% of early corrosion.

• 70% of U.S. pipelines are over 50 years old, increasing the urgency for predictive tools.

## Solution 
The project aims to predict corrosion hotspots using ground-penetrating radar (GPR), soil sensors, and machine learning models. The solution involves: 

• Collecting and organizing data from GPR, soil pH, and leak history. 

• Cleaning and preprocessing the data. 

• Engineering features like corrosion rate and humidity index. 

• Predicting corrosion using multiple linear regression. 

• Performing risk analysis and mapping corrosion severity using heatmaps. 

• Scheduling preventive maintenance using Monte Carlo simulations. 

• Generating a visual dashboard for performance reporting.

## Dataset Used
- <a href="https://github.com/suriya2318/Predictive-Corrosion-Mapping-in-Underground-Pipelines/blob/main/Corrosion_Prediction.xlsx"> Corrosion Prediction Dataset</a>

## Working Process of Underground Pipeline Corrosion Prediction
### Step 1: Data Collection
• Setup: Open Corrosion_Prediction.xlsx and create sheets for GPR Data, Soil pH, Leak History, and Weights (with variables and weights).

• Goal: Structure raw data for easy access.

• Output: Organized data across separate sheets, ready for processing.

### Step 2: Data Cleaning
• Setup: Use Remove Duplicates; apply =IFERROR(A2, AVERAGE(A:A)) for missing values; optional outlier handling via Z-Score/IQR.

• Goal: Improve data quality.

• Output: Clean, accurate datasets ready for analysis.

![image](https://github.com/user-attachments/assets/95c33056-23a2-463c-b886-7e7233707f67)

### Step 3: Feature Engineering
• Setup: In GPR Data sheet, add:

F: Corrosion Risk Factor

G: Normalized GPR Signal

H: Severity Score

• Formulas:

• Corrosion Risk:
=IF(AND(B3<6.5, C3>30, D3>35, E3<0.3), "High Risk", IF(AND(B3<7, C3>25, D3>30, E3<0.5), "Moderate Risk", "Low Risk"))

• Normalized GPR:
=(E2-MIN(E:E))/(MAX(E:E)-MIN(E:E))

• Severity Score:
=C2*D2*E2

• Goal: Derive insights on corrosion conditions and quantify severity.

![image](https://github.com/user-attachments/assets/f3dc1de1-e3fc-4f63-8ac7-070080b1ab9e)

### Step 4: Corrosion Prediction (Multiple Linear Regression)
• Setup:

• In Weights Sheet, assign:

Soil pH: 0.3, Moisture: 0.4, Temperature: 0.2, GPR: 0.1

• In Prediction Sheet:
=SUMPRODUCT(B2:E2, Weights!$B$2:$B$5)

• Goal: Predict corrosion scores using weighted input variables.

### Step 5: Risk Analysis (Conditional Formatting)
• Setup:

Select Corrosion Score Column → Conditional Formatting → Rules:

0.8 = Red (High Risk)

0.5–0.8 = Yellow (Moderate Risk)

< 0.5 = Green (Low Risk)

• Goal: Quickly identify high-risk locations.

![image](https://github.com/user-attachments/assets/c2bfa4c1-35b2-4d74-bbf5-5f5f07db5ab3)

### Step 6: Corrosion Severity Mapping (Heatmap)
• Setup:

Select Corrosion Score column → Home → Conditional Formatting → Color Scales → Red-Yellow-Green.

• Goal: Visualize corrosion severity by color intensity.

![image](https://github.com/user-attachments/assets/b2e9d9ce-1c6a-4898-945a-045196174acd)

### Step 7: Preventive Maintenance Scheduling (Monte Carlo Simulation)
• Setup:

New Sheet: Monte Carlo Simulation

Copy Locations and Corrosion Scores.

Simulate: =RAND()*B2 for 1000 rows.

Failure Probability: =COUNTIF(C2:C1001, ">=0.8")/1000

• Goal: Estimate failure likelihoods and support maintenance planning.

![image](https://github.com/user-attachments/assets/70285a48-2e64-411d-bdd9-afc175dda3ca)

### Step 8: Performance Report (Dashboard)
Charts & Tables:

• Pivot Table for Corrosion Severity.

Output:

![image](https://github.com/user-attachments/assets/12eb5b9b-761b-47f8-8495-154acdcd6f2e)

• Bar Chart for high/moderate/low risk (colored).

Output:

![image](https://github.com/user-attachments/assets/ba0b84d1-f038-4690-8a18-9299ad1bdf36)

• Heatmap: Corrosion Score column with Color Scale.

Output:

![image](https://github.com/user-attachments/assets/458a600b-96b0-46e9-958b-02ec2aa52267)

• Line Chart: Monte Carlo failure probabilities.

Output:

![image](https://github.com/user-attachments/assets/b2b2db5e-f8a7-4fec-82f0-e5834b1921a0)

• Goal: Deliver a visual, data-driven summary of pipeline risk and health.

## Final Outcomes and Workflow 
### Final Outputs 
#### Outcome 1: Identified high-risk corrosion hotspots using predictive modeling. 
o A list of locations classified as High, Moderate, or Low Risk 

#### Outcome 2: Generated a heatmap for visualizing corrosion severity across pipeline locations. 
o A color-coded map showing corrosion severity across all locations. 

#### Outcome 3: Developed a preventive maintenance schedule using Monte Carlo simulations. 
o A schedule with failure probabilities for each location. 

#### Outcome 4: Created a visual dashboard for real-time monitoring and reporting. 
o A comprehensive dashboard for real-time monitoring and reporting. 

### Explore the project Report
- <a href="https://github.com/suriya2318/Micro-Crack-Detection-in-Underwater-Turbine-Blades/blob/main/Micro%20Crack%20Detection%20in%20Underwater%20Turbine%20Blades_Project%20Report.pdf">Project Final Report</a>

### Project Workflow
1. Data Collection → 2. Data Cleaning → 3. Feature Engineering → 4. Corrosion Prediction → 5. Risk Analysis → 6. Severity Mapping → 7. Maintenance Scheduling → 8. Performance Reporting.

## Final Conclusion 
The Predictive Corrosion Mapping in Underground Pipelines project successfully addresses the critical issue of hidden corrosion in aging pipelines, which leads to leaks, environmental hazards, and significant financial losses. By leveraging Excel-based tools, predictive modeling, and data visualization techniques, the project provides a cost-effective and scalable solution for early detection and prevention of pipeline corrosion. 

### Impact: 
• Cost Savings: Reduces annual repair costs by preventing leaks and addressing corrosion early. 

• Improved Safety: Minimizes environmental and safety risks associated with pipeline failures. 

• Extended Lifespan: Enhances the longevity of aging pipelines, 70% of which are over 50 years old in the U.S. 

• Resource Optimization: Allocates maintenance resources efficiently, focusing on high-risk areas.
