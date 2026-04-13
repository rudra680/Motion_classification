 # 🚗 Motion Classification using Feature Engineering & Machine Learning

## 📌 Overview
This project focuses on classifying motion patterns from video frame sequences into four categories:
- **AHEAD**
- **HALTED**
- **SHARP-LEFT**
- **SHARP-RIGHT**

Instead of using deep learning, we rely on **hand-crafted motion features** and classical machine learning models to achieve strong performance.

---

## 🎯 Objective
To build a robust classification pipeline that:
- Extracts meaningful motion-based features from consecutive frames  
- Handles class imbalance effectively  
- Optimizes model performance using threshold tuning  
- Achieves balanced performance across all motion classes  

---

## 📂 Dataset
- Input data consists of **video sequences represented as ordered image frames**
- Each folder corresponds to a **single video**
- Labels are stored using **Excel subsheets per video**
- Temporal consistency is maintained using **consecutive frame pairs**

---

## ⚙️ Pipeline Overview

### 1. Data Preparation
- Validated image paths and labels  
- Maintained temporal order of frames  
- Structured dataset using per-video organization  

---

### 2. Exploratory Data Analysis (EDA)
- Analyzed motion distributions using frame differences  
- Identified **class imbalance**:
  - AHEAD: 4735  
  - HALTED: 1160  
  - SHARP-LEFT: 138  
  - SHARP-RIGHT: 166  

---

### 3. Feature Engineering
Extracted motion-based features including:

#### 🔹 Motion Features
- Frame difference (motion intensity)  
- Left-right and top-bottom motion differences  

#### 🔹 Optical Flow Features
- Mean flow (x and y directions)  
- Flow magnitude  
- Spatial asymmetry (left/right/top/bottom)  

#### 🔹 Motion Dynamics
- Flow curl (rotation)  
- Gradient direction ratios  

#### 🔹 Statistical Features
- Variance  
- Entropy  

#### 🔹 Gradient Features
- Sobel gradients (x and y directions)

---

### 4. Feature Standardization
- Applied **StandardScaler**
- Ensured all features contribute equally to model learning  

---

### 5. Handling Class Imbalance
- Applied **undersampling** for majority class  
- Used **SMOTE (Synthetic Minority Oversampling Technique)**  
- Achieved balanced class distribution  

---

### 6. Model Training
Models used:
- Logistic Regression  
- Support Vector Machine (SVM)  
- Random Forest  
- Gradient Boosting  
- Shallow Neural Network  

---

### 7. Threshold Optimization
- Performed **grid search on class-wise thresholds**  
- Used **Stratified 3-Fold Cross Validation**  
- Optimized for **Macro F1-score**  
- Applied to:
  - Random Forest  
  - Gradient Boosting  

---

## 📊 Results

### 🏆 Best Model: Gradient Boosting (Tuned)

- **Accuracy:** 0.944  
- **Macro F1-score:** 0.794  
- **Weighted F1-score:** 0.940  

### 📌 Key Observations
- Strong performance on **AHEAD and HALTED**  
- Improved detection of **SHARP-LEFT and SHARP-RIGHT**  
- Threshold tuning significantly improved minority class performance  

---

## 🚀 Key Highlights
- Motion-based feature engineering (no deep learning)  
- Optical flow-based representation  
- Effective handling of class imbalance using SMOTE  
- Threshold optimization using grid search  
- Strong generalization on test data  

---
