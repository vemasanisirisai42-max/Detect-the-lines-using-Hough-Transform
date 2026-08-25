#  Exp no : 7 Detect-the-lines-using-Hough-Transform

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.


##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---
### Developed by:
## Name : Siri sai
## Reg no: 212225240181
##  Algorithm & Explanation

Step1:
Import all the necessary modules for the program.

Step2:
Load a image using imread() from cv2 module.

Step3:
Convert the image to grayscale.

Step4:
Using Canny operator from cv2,detect the edges of the image.

Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


###  Step 1: Import Libraries

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```


###  Step 2: Read the Image

```

# Read the image using OpenCV
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread("C:/Users/acer/OneDrive/Desktop/YOLOv4_Webcam/buil.webp")  # Replace 'image.jpg' with your image path

###  Step 3: Convert to Grayscale


# Convert to grayscale.

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)



###  Step 4: Display Images
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')

```

<img width="552" height="448" alt="image" src="https://github.com/user-attachments/assets/066a8142-99eb-4546-972b-4be101192339" />

### Grayscale image display

```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

```
<img width="591" height="467" alt="image" src="https://github.com/user-attachments/assets/dd2f0937-f263-4bde-be22-1fc639612a33" />


### Step 5: Edge Detection (Canny)
```
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

```

<img width="550" height="457" alt="image" src="https://github.com/user-attachments/assets/52748516-93d9-4ee8-9600-3a249ccf67af" />


###  Step 6: Hough Transform
```


lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 150, minLineLength=100, maxLineGap=20)
for line in lines:
    x1, y1, x2, y2 = line
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')

```
<img width="285" height="431" alt="image" src="https://github.com/user-attachments/assets/49ba180a-62d4-4fd1-b4d0-dff999ecdb9c" />


## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

