# Fetal Ultrasound Biometry

This repository contains deep learning–based approaches to identify fetal head biometry landmarks from axial ultrasound images. The project focuses on detecting Biparietal Diameter (BPD) and Occipitofrontal Diameter (OFD), which are clinically used to assess gestational age and fetal neurodevelopment.

---

## 📌 Problem Statement

Fetal ultrasound is the most widely used imaging modality for prenatal screening. Accurate estimation of fetal head biometry is critical for early detection of central nervous system (CNS) anomalies.

This project addresses the task of:
- Identifying **four anatomical landmark points** on fetal axial brain ultrasound images  
  - Two points for **BPD**
  - Two points for **OFD**

Two complementary deep learning approaches are explored:
1. **Landmark Detection-Based Approach**
2. **Segmentation-Based Approach**

---

## 🧠 Approach Overview

### Part A: Landmark Detection-Based Approach
- A convolutional neural network is trained to directly predict landmark locations.
- Ground truth landmarks are represented as Gaussian heatmaps.
- The model learns to regress heatmaps corresponding to each biometry point.
- Final landmark coordinates are extracted from predicted heatmaps.

**Key aspects:**
- Heatmap regression instead of direct coordinate regression
- Data augmentation to handle ultrasound variability
- Multiple architectural hypotheses tested

---

### Part B: Segmentation-Based Approach
- A segmentation model is trained to identify the fetal cranium.
- The predicted segmentation mask is post-processed using classical computer vision techniques.
- An ellipse is fitted to the cranium to estimate:
  - BPD as the minor axis
  - OFD as the major axis

**Key aspects:**
- U-Net–based architecture
- Morphological operations for mask refinement
- Geometry-based extraction of biometry points

---

## 🗂️ Repository Structure

The repository is organized into two main parts corresponding to the task requirements:

### Part 1: Landmark Detection-Based Approach
- Predicts four anatomical landmark points directly using deep learning.
- Uses heatmap regression to localize biometry points.

**Contents:**
- Detailed report (PDF)
- Separate README explaining the approach
- Training and testing scripts
- Model weights for multiple hypotheses tested

---

### Part 2: Segmentation-Based Approach
- Segments the fetal cranium using a U-Net–based model.
- Uses classical computer vision techniques on the segmentation mask to estimate BPD and OFD.

**Contents:**
- Detailed report (PDF)
- Separate README explaining the approach
- Training and testing scripts
- Final trained segmentation model weights

---
Fetal-Ultrasound-Biometry/
│
├── Part_1_Landmark_Detection/
│   ├── report_part1.pdf
│   ├── README.md
│   ├── scripts/
│   │   ├── train.py
│   │   └── test.py
│   └── model_weights/
│       ├── hypothesis_1.pth
│       ├── hypothesis_2.pth
│       └── final_hypothesis.pth
│
├── Part_2_Segmentation/
│   ├── report_part2.pdf
│   ├── README.md
│   ├── scripts/
│   │   ├── train.py
│   │   └── test.py
│   └── model_weights/
│       └── unet_segmentation.pth
│
└── README.md

---

## ⚙️ Framework & Tools

- **Framework:** PyTorch  
- **Language:** Python  
- **Training Environment:** Google Colab (GPU)  
- **Coding Style:** PEP-8 compliant  

---

## 📄 Notes

- This repository is intended for research and educational purposes.
- Direct copying of external codebases was avoided; all implementations were written and adapted independently.

---

## 📬 Contact

For questions, clarifications, or discussions related to this project, feel free to reach out:

**Rhakia**  
LinkedIn: [https://www.linkedin.com/in/rhakia-64906a24a/]

## 👤 Author

Rhakia  
AI & ML Enthusiast
