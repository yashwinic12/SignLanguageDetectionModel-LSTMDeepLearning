# SignLanguageDetectionModel-LSTMDeepLearning
This repository contains code for sign language detection using LSTM and deep learning in Python. The project utilizes TensorBoard, MediaPipe Holistics, and OpenCV to build an effective sign language recognition system.
## Project Structure:
### -Data Collection Folder- Mp_Data
### -Python files
## Techstack Used
The following dependencies are required to run the project:
### -Python (>=3.6)
### -TensorFlow (>=2.0)
### -OpenCV (>=4.0)
### -MediaPipe Holistics
### -NumPy
### -Matplotlib

# 1.MediaPipe Holistic
## The initial step of the program is to identify the Keypoints of the user. MP Holistic is an API created by Mediapipe which identifies the keypoints on a body by identifying the holistic key points

### mp_holistic = mp.solutions.holistic mp_drawing = mp.solutions.drawing_utils
### These two api calls, are calls the Holistic API uses to identify the keypoints holistic keypoints and draw it

## The function draw_landmarks(image, results)
### Draws landmarks of the identified keypoints on the user

## However wth a few extra lines of code draw_styled_landmarks(image,results)
### The keypoints can be color coded for the viewer to identify the different parts of the human



# 2.Collecting the Data

## After the mediapipe has been defined the keypoints must be collected and stored to be trained on later.

## def extract_keypoints(results)
### This takes in the extracted keypoints from the video and concatenated the values into a numpy array.

## The collected data is abeled as 'Hello', 'Thanks', and 'I Love You'. In order to collect the data the user poses for the three different action in for 30 sequences for 30 frames. For a total of 90 collectd sequences
### The identified keypoints are stored in the folder called MP_Data, with each sequence in its respective action folder in the .npy format



# 3.Training the Long Short Term Memory

## To train the Long Short Term Memory the model selected was a Sequential model trained on 3 layers and 2 dense layers. Since it is catagorical data the model was compiled as:

## model.compile(optimizer = 'Adam',loss='categorical_crossentropy',metrics=['categorical_accuracy'])
### The model was then Trained on 2000 epochs.



# 4.Testing in Real time

## These are the testing results in real time from the project after training the data on the LSTM Architecture using MP Holistic

## Hello
## Thanks
## I Love You


## Extras
## 1. Color Coded Probability Viewer
### This is a probability bar which shows the gesture that is being identified the most in the test. The bar rises with the gesture it recognizes most. The color for each bar is as follows:

## Blue/Hello
## Green/Thanks
## Orange/I Love You
