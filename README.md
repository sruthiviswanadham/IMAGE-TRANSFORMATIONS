# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1: Initialize Environment:

Import necessary libraries: cv2, numpy, and matplotlib.pyplot.
Load the Image:

Use cv2.imread() to read the image file (e.g., "HappyFish.jpg").
Convert the image from BGR to RGB format using cv2.cvtColor() for accurate color representation in Matplotlib.
Perform Transformations:
<br>

### Step2: Translation:

Retrieve the image dimensions (rows and columns).
Create a translation matrix M_translate to shift the image by a specified number of pixels (e.g., 50 pixels right and 100 pixels down).
Apply the translation using cv2.warpAffine().
<br>
### Step3: Scaling:

Use cv2.resize() to scale the image by specified factors (e.g., 1.5 times its original size in both dimensions).
<br>
### Step4: Shearing:

Define a shearing transformation matrix M_shear with specified shear factors.
Apply shearing using cv2.warpAffine().
<br>
### Step5: Reflection (Flipping):

Use cv2.flip() to create a horizontal reflection (flip along the y-axis) of the image.
<br>
### Step6: Rotation:

Calculate the rotation matrix using cv2.getRotationMatrix2D(), specifying the center of rotation, angle (e.g., 45 degrees), and scale (1).
Apply rotation using cv2.warpAffine().
<br>
### Step7: Display the Results:

Use Matplotlib to create subplots for the original and transformed images.
Set titles for each subplot and disable axes for better visual presentation.
Adjust layout for clear viewing and show the plots.
<br>
### Step8: Optional Cropping:

(If needed) Crop a specified region of the original image using array slicing.
<br>
## Program:
```python
Developed By: Viswanadham Venkata Sai Sruthi
Register Number: 212223100061
i)Image Translation
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('HappyFish.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib
plt.subplot(2, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')

# 1. Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))

plt.figure(figsize=(12, 8))


plt.subplot(2, 3, 2)
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')

```

```python
ii) Image Scaling
# 2. Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x

plt.subplot(2, 3, 3)
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```

```python
iii)Image shearing
# 3. Shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))

plt.subplot(2, 3, 4)
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```


```python
iv)Image Reflection
# 4. Reflection (Flip)
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)

plt.subplot(2, 3, 5)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```


```python
v)Image Rotation
# 5. Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))

plt.subplot(2, 3, 6)
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')

plt.tight_layout()
plt.show()
```


```python
vi)Image Cropping
# 6. Cropping
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image

# Plot cropped image separately as its aspect ratio may be different
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```

## Output:
### Original Image:
![image](https://github.com/user-attachments/assets/240ea3a4-766b-4ab5-a596-2f1d61357bc6)

### i)Image Translation
![image](https://github.com/user-attachments/assets/8fce931d-c571-417c-bbab-df2b529fbf61)


<br>
<br>
<br>
<br>

### ii) Image Scaling
![image](https://github.com/user-attachments/assets/f72afe8a-3154-4fd5-b929-b75d0885c810)



<br>
<br>
<br>
<br>


### iii)Image shearing
![image](https://github.com/user-attachments/assets/b4e21ed8-99b2-411e-b18d-9821a797db44)


<br>
<br>
<br>
<br>


### iv)Image Reflection
![image](https://github.com/user-attachments/assets/ae64b980-8e0b-47cb-9131-4e785d2e2039)




<br>
<br>
<br>
<br>



### v)Image Rotation
![image](https://github.com/user-attachments/assets/f4cb28ee-c009-42f7-88bd-9c6bc58b3636)

<br>
<br>
<br>
<br>



### vi)Image Cropping
![image](https://github.com/user-attachments/assets/4d462b47-ffc8-44ed-8e2e-b7fb3aa7df5d)

<br>
<br>
<br>
<br>




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
