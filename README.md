# Rice Leaf Disease Detection Project

## 🌿 Project Overview
### Visit Blog : https://medium.com/@vinodbavage08/detecting-rice-leaf-diseases-with-ai-how-i-built-a-92-accurate-classification-system-2771ceb83dfb
### Visit dataset : https://d3ilbtxij3aepc.cloudfront.net/projects/CDS-Capstone-Projects/PRCP-1001-RiceLeaf.zip
### Visit the project website https://riceleafdetection.lovable.app/

This project is an endeavor into **Precision Agriculture**, focusing on the early and accurate detection of diseases in rice leaves using **Machine Learning** and **Deep Learning** techniques. The primary goal is to provide a robust system to help farmers quickly identify common rice leaf diseases, enabling timely intervention to protect crop yield and ensure food security.

## ⭐ Key Objectives

*   **Classification:** Accurately classify rice leaf images into specific disease categories or as healthy.
*   **Model Development:** Build and optimize a high-performance classification model, leveraging deep learning architectures.
*   **Robustness:** Implement advanced techniques like Cross-Validation and Data Augmentation to ensure the model generalizes well to unseen data.

---

## 🔬 Dataset Analysis (Task 1: EDA Summary)

The dataset consists of RGB images of rice leaves, labeled with their respective disease or health status.

| Metric | Details |
| :--- | :--- |
| **Source** | Rice leaf image dataset |
| **Total Images** | 119 |
| **Number of Classes** | 3 |
| **Classes Detected** | `Bacterial leaf blight`, `Brown spot`, `Leaf smut` |

### Class Distribution

| Class | Count |
| :--- | :--- |
| **Bacterial leaf blight** | 40 |
| **Brown spot** | 40 |
| **Leaf smut** | 39 |

***Insights from EDA:***
*   The initial dataset is small (119 images), necessitating the use of **Data Augmentation** and **Transfer Learning**.
*   The class distribution is relatively balanced, but rigorous evaluation (like Stratified K-Fold) is crucial.
*   Images vary in resolution, requiring consistent resizing and normalization during preprocessing.

---

## 🛠️ Methodology and Project Steps

The project follows a comprehensive Machine Learning pipeline:

1.  **Data Loading & Visualization:** Inspecting image quality, labels, and class distribution (EDA).
2.  **Image Preprocessing:** Resizing, normalization, and applying aggressive **Data Augmentation** (rotation, shift, zoom, flip) to increase dataset diversity.
3.  **Train-Test Split:** Splitting data for training and evaluation, utilizing **Stratified K-Fold Cross-Validation** for robust evaluation.
4.  **Model Building:** Developing a **Convolutional Neural Network (CNN)**-based classifier, specifically using **Transfer Learning**.
5.  **Model Training & Evaluation:** Training the model and assessing performance using standard metrics: Accuracy, Precision, Recall, and F1-score.
6.  **Hyperparameter Fine-tuning:** Applying regularization and learning rate scheduling to improve results.

---

## 🧠 Model Building & Performance (Task 2 Summary)

A deep learning classifier was built using **Transfer Learning**, specifically leveraging **EfficientNet**, a powerful and parameter-efficient architecture, to classify the three major rice leaf diseases.

### 📊 K-Fold Cross-Validation Summary

To ensure the model's performance is stable and reliable across different data splits, **K-Fold Cross-Validation** was employed.

| Metric | Accuracy |
| :--- | :--- |
| **Average Training Accuracy** | **97.83%** ($\pm$ 2.29%) |
| **Average Validation Accuracy** | **84.06%** ($\pm$ 8.86%) |

***Outcome:*** A trained **EfficientNet** model capable of classifying rice leaf images into the three disease categories with strong validation accuracy, demonstrating the effectiveness of transfer learning on limited agricultural datasets.

---

## 🚀 Advanced Techniques for Improvement (Task 3 Report)

A strong focus was placed on advanced strategies to overcome common challenges in agricultural image classification (small datasets, potential overfitting).

| Technique | Rationale / Implementation | Best Strategy |
| :--- | :--- | :--- |
| **Data Augmentation** | Artificially increases dataset size and diversity (Rotation, Shift, Zoom, Brightness Jitter). **Prevents overfitting.** | **Aggressive Augmentation** |
| **Transfer Learning** | Using pretrained models (e.g., **EfficientNet**, MobileNetV2) on ImageNet. **Speeds up training & captures low-level features.** | **EfficientNet/MobileNetV2** |
| **Regularization** | **Dropout** (prevents co-adaptation) and **Batch Normalization** (stabilizes training). | **Dropout + BatchNorm** |
| **Learning Rate Scheduling** | `ReduceLROnPlateau` or `Cosine Annealing` for faster, more stable convergence. | **ReduceLROnPlateau** |
| **Early Stopping** | Monitors validation loss to stop training when improvement plateaus. **Prevents overfitting.** | **EarlyStopping** |
| **Cross-Validation** | **Stratified K-Fold** for stable evaluation across splits. | **K-Fold Cross-Validation** |
| **Future Trends** | Investigating **Advanced Augmentation** (Mixup, CutMix), **Self-Supervised Learning**, and **Explainable AI (XAI)** (heatmaps) for better interpretability. | **XAI for Interpretability** |

---

## 💻 Requirements

To run this project, you will need a Python 3.x environment and the following libraries:

*   `numpy`
*   `pandas`
*   `matplotlib` / `seaborn`
*   `scikit-learn`
*   `tensorflow` or `PyTorch` (for deep learning model building)
*   Jupyter Notebook (for analysis and training pipeline)

## 📌 Conclusion

The PRCP-1001 project successfully implemented a complete machine learning pipeline for rice leaf disease detection. The project highlights that a combination of **Exploratory Data Analysis (EDA)**, **Transfer Learning (EfficientNet)**, and robust techniques like **Data Augmentation** and **K-Fold Cross-Validation** is essential for building a reliable and accurate classification system, even with a limited initial dataset. This work lays the foundation for developing real-time, edge-deployable solutions for agricultural field applications.
