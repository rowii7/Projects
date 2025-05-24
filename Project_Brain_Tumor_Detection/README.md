# 🧠 Brain Tumor Detection from MRI Scans

This project presents a deep learning-based system for binary classification of brain MRI images into **tumor** and **no tumor** categories. Leveraging **transfer learning** with **ResNet50**, the project aims to assist radiologists by automating the detection process, improving diagnostic accuracy and efficiency.

---

## 📝 Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Preprocessing](#preprocessing)
- [Model Architecture](#model-architecture)
- [Training and Evaluation](#training-and-evaluation)
- [Results](#results)
- [Installation](#installation)
- [Usage](#usage)
- [References](#references)

---

## 📌 Project Overview

Brain tumor diagnosis is critical and often challenging. Manual MRI analysis is prone to human error and can be time-consuming. This project uses **convolutional neural networks (CNNs)**, specifically **ResNet50**, for the **binary classification** of brain MRI images:

- **Yes Tumor (1)**
- **No Tumor (0)**

Key techniques include:
- Dataset merging and balancing
- Data augmentation
- Transfer learning with ResNet50
- Performance evaluation using standard metrics

---

## 📁 Dataset

Two public Kaggle datasets were used:

1. **Brain MRI Images for Brain Tumor Detection**  
2. **Brain Tumor MRI Dataset** (merged Glioma, Meningioma, Pituitary into one "tumor" class)

After merging, the dataset was:
- Cleaned (duplicate & corrupted images removed)
- Resized to **224x224**
- Balanced: 3,500 images per class (7,000 total)

Split:
- **70% Training**
- **15% Validation**
- **15% Testing**

---

## ⚙️ Preprocessing

- Image resizing and normalization
- Label encoding: `'yes' → 1`, `'no' → 0`
- Augmentation: rotation, zoom, shifting (for minority class)
- Undersampling: controlled downsampling of the majority class

---

## 🧠 Model Architecture

Built using **ResNet50** (pretrained on ImageNet), with modifications:

- Base model frozen (initially)
- Global average pooling
- Dense layer: 128 units, ReLU
- Output layer: 1 neuron, sigmoid activation

**Loss Function:** Binary Crossentropy  
**Optimizer:** Adam  
**Epochs:** 10  

---

## 📊 Training and Evaluation

Training and validation metrics show:

- **Training Accuracy:** 99.49%
- **Validation Accuracy:** 99.52%
- **Test Accuracy:** 98.48%

**Classification Report:**

| Class         | Precision | Recall | F1-score |
|---------------|-----------|--------|----------|
| No Tumor (0)  | 0.97      | 1.00   | 0.98     |
| Tumor (1)     | 1.00      | 0.97   | 0.98     |

**Confusion Matrix:**
- Correct Predictions: 1,034/1,050
- Misclassifications: 16

---


