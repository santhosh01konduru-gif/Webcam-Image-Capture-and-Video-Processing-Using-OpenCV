# NAME: konduru santhosh
# REG.No: 212225240074
# EXP-2:Image Capture and Video Processing Using OpenCV
---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program


## Output

## i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`
~~~
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
~~~
~~~
cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_image.jpg", frame)
    print("Image Saved Successfully")

cap.release()
~~~
<img width="542" height="427" alt="image" src="https://github.com/user-attachments/assets/bfb35ec0-2c9c-4375-902b-f2384e4683a1" />



## ii) Display the video
Live webcam video is displayed
~~~
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()

~~~
<img width="541" height="412" alt="image" src="https://github.com/user-attachments/assets/1dcca2b4-07e4-4f16-9168-ea67c5b573f8" />

### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
~~~
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    # Resize the frame
    resized_frame = cv2.resize(frame, (640, 480))

    # Convert BGR to RGB
    resized_frame = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(resized_frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()

~~~
<img width="278" height="418" alt="image" src="https://github.com/user-attachments/assets/9aaf2e8d-2dcc-426f-b70b-50fdb1b95813" />

## iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
~~~
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    # Rotate the frame
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)

    # Convert BGR to RGB
    rotated_frame = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(rotated_frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)
 cap.release()
~~~

<img width="318" height="421" alt="image" src="https://github.com/user-attachments/assets/77c0012b-9d98-4359-9fff-13593c4839f1" />

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
