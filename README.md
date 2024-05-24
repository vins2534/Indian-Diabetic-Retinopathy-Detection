# Diabetic-Retinopathy-Detection

The main emphasis of this application lies in extracting crucial segments from the retina fundus and subsequently determining whether Diabetic Retinopathy is present or not.

## Table of Contents
- [Introduction](#introduction)
- [About Dataset](#about-dataset)
- [Reading Fundus Images from Folder](#reading-fundus-images-from-folder)
- [Preprocessing](#preprocessing)
- [Segmentation](#segmentation)
- [Feature Extraction](#feature-extraction)
- [Classification Model](#classification-model)
- [Results](#results)

## Introduction
Diabetic Retinopathy (DR) is a serious complication of diabetes that affects the eyes, potentially leading to vision impairment or even blindness if left untreated. Timely detection and intervention are crucial in preventing the progression of this condition. The "Diabetic-Retinopathy-Detection" project aims to address this challenge by leveraging advanced image processing and machine learning techniques.

The primary goal of our application is to analyze retina fundus images and identify signs of Diabetic Retinopathy. By extracting crucial segments from these images and employing a robust classification model, we can provide a reliable tool for early diagnosis and intervention. Early detection allows for timely medical assistance, helping to mitigate the impact of Diabetic Retinopathy on patients' vision.

This project not only contributes to the field of medical diagnostics but also aligns with the broader objective of leveraging technology for proactive healthcare. The automated detection provided by our application has the potential to assist healthcare professionals in their diagnosis, making the process more efficient and accessible.

## About Dataset
The "Diabetic-Retinopathy-Detection" project utilizes the Indian Diabetic Retinopathy Detection dataset, a comprehensive collection of retina fundus images curated for the purpose of advancing research in the field of diabetic eye diseases. This dataset is specifically tailored for the identification and analysis of Diabetic Retinopathy in the Indian population. 

[Dataset Link](https://idrid.grand-challenge.org/Data/)

## Reading Fundus Images from Folder
To train and evaluate the Diabetic-Retinopathy-Detection model, it is essential to efficiently read and preprocess the fundus images from the dataset. 

The IDRid dataset is divided into three folders:
- Segmentation
- Disease Grading
- Localization

In this project, we have utilized the Segmentation and Disease Grading folders, which also consist of ground truths and labeled CSV files.

## Preprocessing
The input fundus images in RGB format are first resized to fit a maximum of 1500 pixels in width and 1152 pixels in height while maintaining the aspect ratio. Key preprocessing steps include:

- **Channel Extraction**: Extracting a particular channel (green or red).
- **CLAHE**: Applying Contrast Limited Adaptive Histogram Equalization (CLAHE) to enhance features.
- **Gamma Correction**: Adjusting brightness and contrast to segment microaneurysms.
- **Median Filter**: Removing salt and pepper noise.
- **Gaussian Filter**: Smoothing the image for better segmentation results.
- **Channel Segmentation**: Using the red channel to segment the optic disc and the green channel for blood vessels and microaneurysms.

## Segmentation
The segmentation of the fundus image includes:
- **Optic Disc**: Extracted from the red channel using binary thresholding and morphological operations.
- **Microaneurysm**: Segmented using thresholding, gamma adjustment, and morphological operations.
- **Blood Vessels**: Segmented from the green channel using CLAHE, filtering, and morphological operations.
- **Exudates**: Identified in grayscale images using thresholding and centroid calculations.

## Feature Extraction
Key features extracted for Diabetic Retinopathy detection include:
- Area of the optic disc
- Ratio of microaneurysms
- Length of blood vessels
- Blood vessel tortuosity
- Edge density
- Mean intensity
- Standard deviation
- Exudate density

These features are critical for accurate model training and prediction.

## Classification Model
After feature extraction, the next step is classification:
- The model used for binary classification is Random Forest, which gave the highest accuracy compared to KNN, Logistic Regression, SVM, and Gradient Boosting.
- Features used for model training include the ratio of microaneurysms, blood vessel length, blood vessel tortuosity, and mean intensity.

## Results
The results and performance metrics of the model will be discussed in this section. (Add your specific results and findings here.)

## Contributing
We invite contributors and users to explore, collaborate, and enhance the capabilities of this Diabetic Retinopathy detection system.


