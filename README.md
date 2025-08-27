# Classification of Brain Tumors in MRI Images using Deep Learning

## Purpose
This project implements a **deep learning pipeline** to detect and classify brain tumors from MRI scans into three categories: **Meningioma, Glioma, and Pituitary tumors**. It combines **U-Net for tumor segmentation** and a **CNN for classification**, providing both region-of-interest detection and tumor type identification.

## Features
- Segment brain and tumor regions using **U-Net** for precise focus on tumor areas.
- Classify MRI scans into **Meningioma, Glioma, or Pituitary tumors** using a **CNN** trained on **augmented and cleaned segmented data**.
- Preprocess images with **OpenCV, NumPy, and skimage** (resizing, normalization, augmentation).
- Data augmentation using image flipping to enhance training.
- Model evaluation using **Dice coefficient, IoU, ROC AUC, precision, recall, specificity, F1-score, and accuracy**.
- Visualize segmentation masks, classification results, and training metrics using **Matplotlib**.

## Dataset
The dataset consists of MRI scans in `.mat` format and can be found on **Kaggle**: (https://figshare.com/articles/dataset/brain_tumor_dataset/1512427/5).

## Tech Stack
- **Programming Language:** Python  
- **Libraries:** TensorFlow/Keras, OpenCV, NumPy, scikit-learn, Matplotlib, skimage, h5py  
- **Development Environment:** Kaggle GPU T4 x2
- **Dataset Management:** Kaggle

## Pipeline Overview
1. Load and preprocess MRI images and ground truth masks from `.mat` files.
2. Resize images and masks to **128x128** pixels and normalize pixel values.
3. Split data into training, validation, and test sets.
4. Augment training data with horizontal flipping.
5. Train **U-Net** for tumor segmentation using **BCE + Dice loss** and IoU metric.
6. Generate predicted masks and filter out blank predictions.
7. Train **CNN classifier** on segmented tumor regions to classify tumor type.
8. Evaluate models on test set with detailed metrics and visualization of predicted masks.

## Result
### Classification Performance by Tumor Type

| Tumor Type      | Precision | Recall | F1-score | Number of Samples|
|-----------------|-----------|--------|----------|------------------|
| Meningioma      | 0.72      | 0.66   | 0.69     | 71               |
| Glioma          | 0.86      | 0.84   | 0.85     | 143              |
| Pituitary Tumor | 0.87      | 0.97   | 0.92     | 93               |

<img width="1598" height="971" alt="image" src="https://github.com/user-attachments/assets/af61c80b-aa05-47c2-af0a-109baa04a37c" />

