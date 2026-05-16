# Edge Detection Using OpenCV

## Aim
To perform edge detection using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detectors.

---

## Software Required
- Python 3.x
- OpenCV
- NumPy
- Matplotlib
- Jupyter Notebook / VS Code

---

## Algorithm

### Step 1
Import required libraries.

### Step 2
Load the input image.

### Step 3
Convert the image to grayscale.

### Step 4
Apply Sobel edge detector.

### Step 5
Apply Prewitt edge detector.

### Step 6
Apply Roberts edge detector.

### Step 7
Apply Laplacian edge detector.

### Step 8
Apply Canny edge detector.

### Step 9
Display all output images.

---

## PROGRAM :

```P
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread("image.jpg")

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

sobelx = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=3)
sobely = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=3)
sobel = cv2.magnitude(sobelx, sobely)

kernelx = np.array([[1,1,1],
                    [0,0,0],
                    [-1,-1,-1]])

kernely = np.array([[-1,0,1],
                    [-1,0,1],
                    [-1,0,1]])

prewittx = cv2.filter2D(gray, -1, kernelx)
prewitty = cv2.filter2D(gray, -1, kernely)
prewitt = prewittx + prewitty

robertsx = np.array([[1,0],
                     [0,-1]])

robertsy = np.array([[0,1],
                     [-1,0]])

robertx = cv2.filter2D(gray, -1, robertsx)
roberty = cv2.filter2D(gray, -1, robertsy)
roberts = robertx + roberty

laplacian = cv2.Laplacian(gray, cv2.CV_64F)

canny = cv2.Canny(gray, 100, 200)

plt.figure(figsize=(15,10))

plt.subplot(2,3,1)
plt.imshow(gray, cmap='gray')
plt.title("Original Image")
plt.axis("off")

plt.subplot(2,3,2)
plt.imshow(sobel, cmap='gray')
plt.title("Sobel Edge")
plt.axis("off")

plt.subplot(2,3,3)
plt.imshow(prewitt, cmap='gray')
plt.title("Prewitt Edge")
plt.axis("off")

plt.subplot(2,3,4)
plt.imshow(roberts, cmap='gray')
plt.title("Roberts Edge")
plt.axis("off")

plt.subplot(2,3,5)
plt.imshow(laplacian, cmap='gray')
plt.title("Laplacian Edge")
plt.axis("off")

plt.subplot(2,3,6)
plt.imshow(canny, cmap='gray')
plt.title("Canny Edge")
plt.axis("off")

plt.tight_layout()
plt.show()
```

## Output

### Sobel Edge Detector
- Detects horizontal and vertical edges
- Produces gradient-based edge map

### Prewitt Edge Detector
- Detects directional edges
- Uses simple kernels

### Roberts Edge Detector
- Detects diagonal edges
- Sensitive to noise

### Laplacian Edge Detector
- Uses second-order derivatives
- Detects rapid intensity changes

### Canny Edge Detector
- Produces clean and thin edges
- Multi-stage edge detection technique

---

## Result
Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques.

---

## Developed By

**Name:** Thirumalai K

**Department:** AIML