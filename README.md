# Hand-Guesture-Recognition
Conducting examination in a smoothly manner is a crucial task for an invigilator. Students require help during exams for various things. Students can inform the invigilator by voicing out, but it might disturb other classmates who are writing the paper. In a large classroom it might be tedious task for a student to interact with the invigilator instantly. To solve the problem, students can use hand signals to inform the invigilator for any help. The invigilator needs to be attentive and carefully look for signs from students to help them. In such cases where the classroom is big or to run the examination by minimal disturbance for the students, we can use the hand gesture recognition task by a surveillance camera which can capture the hand gesture from the students and inform the same via an app to the cell phone of the invigilator.

# Steps to Develop Hand Gesture Recognition
The steps are divided into the following three parts:
1) Creating a dataset
2) Training a CNN on the captured dataset
3) Predicting the data

# Dataset Creation
Used live feed from the video camera to create the dataset.
Created a region of interest where the frames will be detected and saved in a directory having 4 folders for 4 different hand gestures.
Did background differentiation by calculating the accumulated weighted average of the background and subtract this from the frames that contain some object Infront of the background that can be distinguished as a foreground.

# Calculate Threshold Value
Calculated threshold value for every frame.
Then determined the contour and returned the max contours using the function segment.
When contours are detected, we start to save the image of the ROI for the different folders for the different signs it is detected for.
Then created a total of 1000 images for each set of different hand gestures.

# Resize Images
Image are to be resized before training the model.
Images are resized in a particular ratio.
Base width was fixed to 100 pixels and height is then defined by the ratio of 100 divided by original base width value of the image.

# Training the CNN
Trained the CNN on the created dataset.
Designed CNN based on some trial and error method with hyper tuning the model.
Built network containing 7 hidden convolution layers with Relu as the activation function and 1 Fully connected layer.
The network is trained across 50 iterations with a batch size of 64.
The ratio of training set to validation set is kept at 1000: 100.
After compiling the model, we fit the model using 8 epochs and save the model for it to be used in the last module.

# Predict the Gesture
Created a bounding box for detecting the ROI and calculate the accumulated average. This is done for identifying any foreground object.
Now find the max contour and if contour is detected that means a hand, threshold of the ROI is treated as a test image.
With the use of previously saved model, the threshold image is given as an input to the model for prediction.

Thank you for reading out till the end.
