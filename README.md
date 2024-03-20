# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera

### Step 2:
Use cv2.imread to read the video or image

### Step 3:
Use cv2.imwrite to save the image

### Step 4:
Use cv2.imshow to show the video

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
``` Python
### Developed By: Syed Mokthiyar S.M
### Register No:212222230156

## i) Write the frame as JPG file
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("lily.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('lily',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window

```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230038_GOKUL J',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230156_syed',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![out 1 dipt sy](https://github.com/syedmokthiyar/Image_Acqusition-_using_Web_Camera/assets/118787294/ca22cf1c-1d0d-4ccf-b651-e2270ccc9322)

### ii) Display the video
![out 2 dipt sy](https://github.com/syedmokthiyar/Image_Acqusition-_using_Web_Camera/assets/118787294/fcf187c5-bd6c-4f37-8240-96355a23b117)

### iii) Display the video by resizing the window
![out 3 dipt sy](https://github.com/syedmokthiyar/Image_Acqusition-_using_Web_Camera/assets/118787294/9160505e-2320-482e-add7-4cd90660fcae)

### iv) Rotate and display the video

![out 4 dip syed 1](https://github.com/syedmokthiyar/Image_Acqusition-_using_Web_Camera/assets/118787294/1bd46c23-d23c-4b63-b840-06400ec5795b)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
