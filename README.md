# Fraud Detection Using Synthetic Transaction Data

## Approach Overview
This project implements an end-to-end fraud detection system using synthetically generated transaction data.  
Since real-world fraud data is sensitive and often unavailable, a realistic synthetic dataset was created to simulate user transactions on a digital payments platform. The overall approach involved:

1. Generating time-ordered transaction data with realistic entities such as users, merchants, devices, locations, and payment methods.  
2. Injecting non-random fraud patterns to simulate real-world fraud scenarios.  
3. Performing feature engineering to capture user behavior and transactional deviations.  
4. Training a machine learning model to classify transactions as fraudulent or legitimate.  
5. Evaluating the model using metrics suitable for imbalanced data.  
6. Applying explainability techniques to interpret model predictions.  
7. Designing a lightweight system architecture for real-world deployment (design only, no deployment).

This pipeline demonstrates the complete lifecycle of building a practical machine learning solution for fraud detection.

---

## Fraud Patterns Used
Fraudulent transactions were injected with structured, realistic patterns rather than random labels. The following patterns were introduced:

- **Sudden transaction amount spikes:** Fraudulent transactions often involve unusually high amounts compared to a user's normal spending behavior.  
- **Location inconsistency:** Fraudulent activity may originate from a different city or region than the user’s typical location, simulating account takeover or stolen payment credentials.  

These patterns make the fraud detection task realistic and allow the model to learn meaningful behavioral signals.

---

## Model Choice Rationale
A **Random Forest classifier** was chosen as the primary model for this task because:

- It handles non-linear relationships and feature interactions effectively.  
- It performs well on tabular data with mixed numerical and categorical features.  
- It is robust to noise and outliers.  
- It provides feature importance, which supports model interpretability.  
- Class weighting was used to address the class imbalance where fraudulent transactions are rare.

This makes Random Forest a strong and practical baseline for fraud detection problems.

---

## Evaluation Results
Fraud detection is a highly imbalanced classification problem; therefore, model evaluation was performed using metrics beyond accuracy:

- **Precision:** Measures how many predicted frauds were actually fraud.  
- **Recall:** Measures how many actual frauds were correctly detected.  
- **F1-score:** Balances precision and recall.  
- **ROC-AUC:** Evaluates the model’s ability to rank fraudulent transactions higher than legitimate ones across thresholds.  
- **Confusion Matrix:** Provides a detailed breakdown of true positives, false positives, true negatives, and false negatives.

The evaluation results show that the model is able to capture meaningful fraud patterns from the synthetic data while maintaining a reasonable trade-off between catching fraudulent transactions and limiting false positives. Threshold tuning can further adjust this trade-off based on business requirements.
