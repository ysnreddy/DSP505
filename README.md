# DSP505
DSP505 Major Project

# Project Name 
Custom Object Detection using offline models

A brief description of your machine learning project.

This Project will detect the objects with the help of the trained model and label the objects with their respective names.
When we capture an image from the Android mobile, that image will be sent to our offine model and it will infer the image and identify the objects within it and position the objects with the bounding boxes along with their names.

Here we have trained a custom model and deployed the same in our Android application.

## Table of Contents

- [Overview](#overview)
This Project will detect the objects with the help of the trained model and label the objects with their respective names. When we capture an image from the Android mobile,
that image will be sent to our offine model and it will infer the image and identify the objects within it and position the objects with the bounding boxes along with their names.

- [Installation](#installation)
A recent version of Android Studio (v4.2+)
Android Studio Emulator or a physical Android device
TFLite Model Maker
TFLite Task Library

- [Usage](#usage)
used for detecting the objects at a place without using the internet.

- [Data](#data)

Initial Efficient Model was training on COCO dataset. Open Images Dataset V4 is a publicly available Salads dataset, which was used for custom training of the model. 
Each image in the dataset contains objects labeled as one of the following classes:

Baked Good
Cheese
Salad
Seafood
Tomato

The Salads dataset is available at: gs://cloud-ml-data/img/openimage/csv/salads_ml_use.csv.

It contains 175 images for training, 25 images for validation, and 25 images for testing. The dataset has five classes: Salad, Seafood, Tomato, Baked goods, Cheese.

The dataset is provided in CSV format:

TRAINING,gs://cloud-ml-data/img/openimage/3/2520/3916261642_0a504acd60_o.jpg,Salad,0.0,0.0954,,,0.977,0.957,,
VALIDATION,gs://cloud-ml-data/img/openimage/3/2520/3916261642_0a504acd60_o.jpg,Seafood,0.0154,0.1538,,,1.0,0.802,,
TEST,gs://cloud-ml-data/img/openimage/3/2520/3916261642_0a504acd60_o.jpg,Tomato,0.0,0.655,,,0.231,0.839,,

Each row corresponds to an object localized inside a larger image, with each object specifically designated as test, train, or validation data. You'll learn more about what that means in a later stage in this notebook.
The three lines included here indicate three distinct objects located inside the same image available at gs://cloud-ml-data/img/openimage/3/2520/3916261642_0a504acd60_o.jpg.
Each row has a different label: Salad, Seafood, Tomato, etc.
Bounding boxes are specified for each image using the top left and bottom right vertices.	


- [Training]
# Using TensorFlow Lite:
TensorFlow Lite is a cross-platform machine learning library that is optimized for running machine learning models on edge devices, including Android and iOS mobile devices. It has two major components which are used in 
this project
  1. Model Maker is a Python library - For Transfer Learning
  2. Task Library for converting model into .TFLite.

The EfficientDet-Lite0 model uses epochs = 50 by default, which means it will go through the training dataset 50 times. You can look at the validation accuracy during training and stop early to avoid overfitting.
Set batch_size = 8 here so you will see that it takes 21 steps to go through the 175 images in the training dataset.
Set train_whole_model=True to fine-tune the whole model instead of just training the head layer to improve accuracy. The trade-off is that it may take longer to train the model.

- [Evaluation](#evaluation)

Evalution metrics used are standard metrics used for object detection.
	
- [Results](#results)

Results are obtained in our Android app in the form of bounding boxes with the object names and confidence level

- [Contributing](#contributing)

  CNN Model Training: Yarrabothula SN Reddy
  Android Mobile App Development: Sivananda



- [License](#license)
https://www.apache.org/licenses/LICENSE-2.0

