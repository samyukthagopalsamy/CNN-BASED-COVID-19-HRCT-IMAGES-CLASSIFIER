# CNN BASED COVID-19 HRCT IMAGES CLASSIFIER

The CNN based COVID-19 High-Resolution Computed Tomography (HRCT) Images Classifier can detect COVID-19 infection from the given CT scan images of COVID and non-COVID patients and determine the severity of lung infection from those images. 

This is done mainly using the four steps:

**1. Preprocessing the data:** Refers to all the transformations on the acquired data before it 
is fed to the deep learning algorithm. This step involves anonymizing patient details, 
verifying data distribution, and sampling the required images for each patient. <br>
* Sampled 64 image slices from over 700 slices for each of 210 patients to avoid model overfitting

**2. Segmentation:** The preprocessed lung images will undergo segmentation to partition the 
lung scan into different segments. This is done to simplify the representation of an image to 
something more meaningful and easier to analyze. <br>
* Segmented lungs from thoracic tissue by applying a mask from a pre-trained 3D U-net (R-231) model

**3. Classification:** The segmented images are taken for the process of classification to 
categorize all the pixels in a digital image into one of two classes. <br>
* Trained Convolutional neural network model to predict the probability of COVID-19 infection from high resolution computed tomography (HRCT) lung scans <br>
* Built the model using Keras with input tensor of dimension 1*64*128*128 and used Binary Cross-Entropy loss function

**4. Scoring:** The images classified as COVID positive are assigned a severity score based 
on the amount of lung infected. <br>
* Achieved an accuracy of 82.11%, F1-score of 82.25%, and AUC of 0.857

The **data set** for this project is provided by **PSG Institute of Medical Sciences & Research**, 
Coimbatore. This data set contains a combination of Computed Tomography (CT) scan 
images of patients who are affected by COVID-19 and patients who are not affected by 
COVID-19. 

A total of 210 patients CT scan images were given in which 125 patients are affected by 
COVID-19, and 85 patients are not affected by COVID-19. 
Each of these 210 patients’ CT scans contained nearly 400 to 800 slices of information. 

This research project is completed under the guidance of  **Dr. Karpagam G R** (Associate Head and Programme 
Coordinator, CSE, PSG College of Technology) and **Dr. Maheshwaran V** (Associate Professor, Department of 
Radiology, PSG Institute of Medical Sciences & Research) and was supported by the **Centre for Artificial Intelligence and Research Laboratory**, PSG
College of Technology. 
