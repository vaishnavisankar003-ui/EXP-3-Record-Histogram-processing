# EXP-3-Record-Histogram-processing
# Histogram-of-an-images

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:** VAISHNAVI S

**Register Number:** 212225230289

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('vaishu.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('vaishu.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image

<img width="372" height="605" alt="Screenshot 2026-10-26 125349" src="https://github.com/user-attachments/assets/dae940f0-5626-47c6-aed2-adedd92dad57" />

### Input Grayscale Image Range

<img width="818" height="596" alt="Screenshot 2026-10-26 125402" src="https://github.com/user-attachments/assets/eec11989-6eb5-491b-a21c-47b9ae84dfb4" />


### Input Grayscale Image Equalized Histogram

<img width="777" height="593" alt="Screenshot 2026-10-26 125415" src="https://github.com/user-attachments/assets/913eb508-367c-48d8-afad-17e4ce601b2d" />


### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="420" height="592" alt="Screenshot 2026-10-26 125423" src="https://github.com/user-attachments/assets/43d2716b-8593-44e5-9f55-b4561f62a5d3" />

### Equalized Image

<img width="412" height="586" alt="Screenshot 2026-10-26 125432" src="https://github.com/user-attachments/assets/f42e8ea8-262b-46d9-be9b-032005ae1bf6" />

### Equalized Histogram

<img width="786" height="582" alt="Screenshot 2026-10-26 125446" src="https://github.com/user-attachments/assets/ad1148cb-8a33-4a65-b15c-2fc6d913b116" />


### Final Output of Original Image and Equalized 

<img width="1535" height="547" alt="Screenshot 2026-10-26 125533" src="https://github.com/user-attachments/assets/13ab5043-a20e-40b1-991b-0a9fc881159c" />


### Final Output of Original Image and its Histogram Equalized
<img width="1585" height="450" alt="Screenshot 2026-10-26 125546" src="https://github.com/user-attachments/assets/7805cd71-a30e-4671-ac1b-dd8cd2473310" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
