# Time-To-Recovery Modeling for Photovoltaic Cells

> This project was completed as part of my practicum for the **Master of Science in Computational Analytics** program at **Georgia Tech**, in collaboration with **Sandia National Laboratories**.

This project presents a modeling framework to estimate the **time-to-recovery** of utility-scale photovoltaic (PV) systems following adverse weather events. While much of the existing literature addresses degradation and fault detection in PV systems, the **recovery phase**—how long it takes for system performance to return to normal—remains underexplored. This work addresses that gap using a combination of **survival analysis** and **machine learning**.

## Dataset

The analysis is based on a large-scale dataset covering **over 800 PV plants across the U.S.**. The primary outcome is the **duration (in days)** required for a system’s **performance ratio (PR)** to return to baseline after experiencing a disruption.

## Methodology

The analytical pipeline includes:
- **Clustering** and **time labeling** of raw performance data.
- Identification of **recovery episodes** following weather-induced performance drops.
- **Feature engineering** to capture system, temporal, and event-based characteristics.

Several modeling approaches were tested to predict recovery duration:

### Survival Models
- **XGBoost Cox** *(best-performing: C-index = 0.8426)*
- **DeepSurv**
- **Random Forest Survival**
- **Logistic Hazard**
- **DeepHit**

### Baseline Models
- Linear Regression  
- Logistic Regression  
- Multi-Layer Perceptron (MLP)

The models were evaluated using the **concordance index (C-index)**, a standard metric in survival analysis to assess the ability to correctly rank predicted recovery times.

## Findings

- The **XGBoost Cox** model achieved the highest performance and best ability to rank recovery durations.
- Tree-based survival models offered a strong balance between **performance and interpretability**.
- Deep learning models like DeepSurv and DeepHit showed potential but required more tuning and data regularization to generalize well.
- Baseline models were substantially less accurate, validating the importance of using time-to-event modeling in this context.

## Conclusion

This study demonstrates that survival-based approaches are well-suited for modeling recovery timelines in solar PV systems. The findings are applicable to **resilience planning**, **operational forecasting**, and **maintenance scheduling** in renewable energy operations.

