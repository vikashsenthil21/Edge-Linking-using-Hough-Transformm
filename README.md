# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image.

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:

### Developed by : Vikash s
### Register no : 212222240115
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('captan.png') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```
## Output

![image](https://github.com/user-attachments/assets/718cb501-4f38-432d-a414-9f87067ddc02)

## Grayscale Image:
```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
plt.subplot(2, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
## Output

![image](https://github.com/user-attachments/assets/2786b059-060c-4ada-968b-f8c0bbb519b3)

## Canny Edge Detector:
```
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
plt.subplot(2, 2, 3)
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
```
## Output

![image](https://github.com/user-attachments/assets/80e1560e-7f11-40b0-bb40-ac8d2ea8c526)

## Detect lines using the probabilistic Hough transform
```
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
        plt.subplot(2, 2, 4)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
```
## Output

![image](https://github.com/user-attachments/assets/3238ff31-1b48-40c6-bdb7-93bb8ae71992)

# Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
