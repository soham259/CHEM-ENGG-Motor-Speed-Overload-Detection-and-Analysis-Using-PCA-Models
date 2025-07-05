# Motor Speed Overload Detection and Analysis Using PCA (SIMCA)

## Overview

This project presents a **data-driven approach** for early detection and analysis of overload conditions in a series of industrial equipment using **Principal Component Analysis (PCA)**. All multivariate modeling and visualizations were performed using **SIMCA** software, ensuring robust and interpretable results for process monitoring and predictive maintenance.

## Problem Statement

- **Equipment Train:** The process consists of five units (E1–E5) in series, each with motor current sensors (FLAs).
- **Operational Challenge:** Overloads can cause system shutdowns, resulting in downtime and production loss.
- **Goal:** Develop a model to detect and predict overloads using historical sensor data, enabling proactive maintenance.

## Key Features

- **Data Preprocessing:** Cleans and prepares raw data for analysis, including filtering, imputation, and scaling.
- **PCA Modeling (SIMCA):** Utilizes SIMCA’s PCA-X models for dimensionality reduction and pattern recognition.
- **Overload Indicator:** Binary variable (0/1) indicating overload state, used for classification and monitoring.
- **Visualization:** All plots (score, loading, DModX, Hotelling’s T²) are generated in SIMCA for clear interpretation.
- **Outlier & Instability Detection:** Identifies abnormal samples and process instability through multivariate statistics.

## Data Description

- **Variables:**
  - `Date`: Timestamp of measurement
  - `E1 FLAs` – `E5 FLAs`: Full Load Amps for each equipment
  - `E1 Speed`: Speed of E1 motor
  - `Overload indicator`: Target variable (0 = normal, 1 = overload)
- **Preprocessing Steps:**
  - Remove non-informative columns (e.g., time, all-zeros columns)
  - Filter out downtime rows (`E1 FLAs` < 20)
  - Impute missing values using KNN (if needed before SIMCA import)
  - Standardize variables (mean = 0, std = 1)

## PCA Modeling in SIMCA

- **Model Building:** Data imported into SIMCA, PCA-X model built with optimal components determined by cross-validation.
- **Variance Explained:** First two principal components typically explain ~77% of variance (PC1: 59%, PC2: 18%).
- **Visualization:** 
  - **Score Plots:** Show clustering and separation of overload vs. normal samples.
  - **Loading Plots:** Reveal which variables drive each principal component.
  - **DModX & Hotelling’s T²:** Identify outliers and monitor process stability.
- **Interpretation:** Overload conditions correlate strongly with higher FLAs and E1 Speed; E4/E5 FLAs are closely related, E2 FLAs behaves differently.

## Usage

1. **Prepare Data:** Clean and preprocess as described.
2. **Import to SIMCA:** Load data into SIMCA for PCA modeling.
3. **Analyze:** Use SIMCA’s graphical tools to interpret results, monitor for overloads, and detect abnormal conditions.
4. **Take Action:** Use insights for predictive maintenance and process optimization.

## Dependencies

- **Software:** SIMCA (for all PCA modeling and visualization)
- **Optional (for preprocessing):** Python (pandas, numpy, scikit-learn), Excel

## Authors

- Saumya Vaidya
- Soham Raut
- Srajan Kewat
- Sohel Bhongade

- **All PCA models and plots in this project were created using SIMCA.**
- For code-based preprocessing, Python (with pandas and scikit-learn) was used prior to SIMCA import[1][2].

*For further details, refer to the project documentation and SIMCA project files.*
