# Fake Banking Android App Detection

## Problem Statement
Problem Statement 4 – Detection of Fake Banking Android Applications

## Channel
Channel 2 – Synthetic Data

---

## Overview
This project aims to detect fake or malicious banking Android applications using
machine learning. Fake banking apps often misuse sensitive permissions such as
SMS, contacts, and accessibility services to perform financial fraud.

To ensure ethical and safe experimentation, a fully synthetic dataset was
generated that simulates realistic permission abuse and behavioral patterns.

---

## Architecture Overview
Synthetic Dataset  
→ Data Preprocessing  
→ Logistic Regression Model Training  
→ Model Evaluation  
→ ONNX Model Export  
→ ONNX-based Inference  

---

## Dataset
- Dataset Type: Synthetic
- Dataset Size: ~1 GB
- Each row represents one Android banking application
- Generated programmatically using controlled randomness
- Inspired by publicly documented Android permission abuse patterns
- No real APKs or malware binaries were used

### Features
- permissions_count  
- dangerous_permissions  
- uses_sms  
- uses_contacts  
- uses_camera  
- uses_accessibility  
- api_call_count  
- app_size_mb  
- target_sdk  
- background_services  

### Label
- 0 → Legitimate App  
- 1 → Fake / Suspicious App  

---

## Model
- Algorithm: Logistic Regression
- Library: Scikit-learn

### Justification
- Simple and explainable
- Effective for tabular data
- Suitable for security-focused classification
- Easy deployment using ONNX format

---

## Training Details
- Large dataset handled using sampling strategy
- Sample size used for training: 200,000 rows
- Train/Test split: 80/20
- Evaluation Metrics:
  - Accuracy
  - Precision
  - Recall
  - Confusion Matrix

Detailed metrics are available in `logs/training_logs.txt`.

---

## How to Run Training
```bash
python code/train.py
