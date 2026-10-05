# Marketing Campaign Success Prediction

University machine learning project focused on predicting the success of marketing campaigns using early campaign performance data.

The project was completed as part of the module **Maschinelles Lernen**.

## Project Overview

The project was developed around a business case for **Encore Events**, an event agency running marketing campaigns across channels such as Google, Facebook and Instagram.

The goal was to predict as early as possible whether a campaign would reach its target, allowing the company to intervene before the campaign ends.

A campaign was classified as successful if its final impressions reached at least **90% of the defined target**.

## Machine Learning Problem

The task was formulated as a **binary classification problem**:

- **1 = Successful campaign**
- **0 = Unsuccessful campaign**

The prediction was based only on information available up to the **third campaign measurement**.

A regression approach was also explored, but classification was selected as the final modelling approach because it better matched the business decision problem.

## Data Preparation

The data preparation process was performed in **Tableau Prep**.

Three source tables were combined:

- Campaign basic information
- Campaign channels
- Campaign snapshots

The preparation process included:

- Joining the source tables
- Pivoting campaign snapshot data
- Transforming marketing channels into binary variables
- Removing technical duplicates
- Handling missing values
- Standardising inconsistent category values

## Feature Engineering

Feature engineering and modelling were performed in **Orange**.

The final feature set included:

### Numerical Features

- Target
- Budget
- Campaign duration
- Impression measurement 1
- Impression measurement 2
- Impression measurement 3

### Categorical Features

- Region
- Category

### Marketing Channels

- Facebook
- Google Display
- Google Search
- Instagram

Variables containing information about the final campaign result were intentionally excluded to avoid **target leakage**.

The feature space was also reduced because the dataset contained only around **230 campaigns**, which increased the risk of overfitting.

## Models Evaluated

Several machine learning models were compared:

- Decision Tree
- Random Forest
- Gradient Boosting
- AdaBoost
- Neural Network

The models were evaluated using **Stratified 10-Fold Cross Validation**.

## Evaluation Metrics

The project considered several performance metrics:

- AUC
- Matthews Correlation Coefficient (MCC)
- Classification Accuracy
- Confusion Matrix

MCC was particularly relevant because the classes were not perfectly balanced.

## Best Model

The best-performing model was **Gradient Boosting**.

### Performance

- **AUC:** 0.857
- **MCC:** 0.547
- **Classification Accuracy:** 0.774

Gradient Boosting showed the strongest overall separation between successful and unsuccessful campaigns.

The most important predictors included:

- Early impression values
- Campaign budget
- Campaign target

## Business Value

The purpose of the model was not only to achieve good predictive performance, but also to support earlier business decisions.

If a campaign is identified as being at risk after the third measurement, the company could respond by:

- Increasing the campaign budget
- Adding additional marketing channels
- Reallocating resources
- Reducing inefficient marketing spend

In the project scenario, this intervention was estimated to generate an additional **CHF 18,000 profit per 100 campaigns**.

## Technologies & Tools

- Machine Learning
- Tableau Prep
- Orange
- Binary Classification
- Feature Engineering
- Data Preparation
- Cross Validation
- Gradient Boosting
- Random Forest
- Decision Trees
- Neural Networks
- Model Evaluation
- AUC
- MCC

## My Contribution

This project was developed collaboratively by a four-person team. We worked together across all major stages of the machine learning process rather than assigning isolated components to individual members.

My contribution therefore included collaborative work on:

- Preparing and cleaning the campaign data in Tableau Prep
- Transforming and structuring the dataset for modelling
- Defining the target variable and selecting relevant features
- Performing feature engineering in Orange
- Comparing multiple machine learning models
- Evaluating model performance using AUC, MCC, accuracy and confusion matrices
- Interpreting the results of Gradient Boosting and other models
- Discussing overfitting, target leakage and feature selection
- Assessing the business value of the prediction model
- Preparing and reviewing the final documentation and presentation

The project was developed through continuous teamwork, shared analysis and joint decision-making.

## Repository Structure

```text
campaign-success-prediction/
│
├── data/
│   └── processed_campaign_data.csv
│
├── workflows/
│   ├── tableau_prep_flow.tfl
│   └── orange_ml_workflow.ows
│
├── documentation/
│   └── final_documentation.pdf
│
├── presentation/
│   └── project_presentation.pptx
│
└── README.md
