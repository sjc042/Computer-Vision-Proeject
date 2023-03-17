# Computer-Vision-Project

## Problem Description
### Goal:
Increase the frame rate of a video source by a factor of ~2, i.e. interpolate a video sequence of 30 frames/sec to 59 frame/sec.

### Algorithm:
Use Farneback Optical Flow to generate an artificial frame by using the two consecutive real frames from the original video sequence.

### Data:
Got a free video from pexels.com/videos and down sampled the sequence of 60 frames/sec to 30 frames/sec by taking every other frame

First downsample a video sequence of 60 frames/sec to 30 frames/sec by taking every other frame; then interpolate based on video of 30 frames/sec; finally judge the quality of interpolated video by viewing it with human eyes or comparing the generated frames with the excluded half of the original frames.

#### Preexisting work:
The methods from cv2 such as calcOpticalFlowFarneback(), which is the working algorithm for our problem. We also used cv2.cvtColor() to gray out our frames.

#### Implementation:
Interpolate down sampled video sequence using Farneback Optical Flow. The generated video sequence will have a frame rate about twice that of the original/source video sequence(i.e. original frame rate 30fps---> new frame rate 59fps).

### Original video sequence with frame rate of 25 fps
https://user-images.githubusercontent.com/68932309/224836568-3eb8c213-2144-48a0-a822-6d43978f205a.mov

#### We found this free video online at pexels.com/video

### Farneback Interpolated video sequence with frame rate of 50 fps playback at 25 fps
https://user-images.githubusercontent.com/68932309/224836641-083c4bc8-b3ad-45c7-aa8d-e108fa4d4939.mov

### Farneback Interpolated video sequence with frame rate of 50 fps playback at 50 fps
https://user-images.githubusercontent.com/68932309/224836665-86789c1d-be8a-4150-9f13-cc5704989ed9.mov

### Examples  interpolated frames with Lucas Kanade optical flow
![frame1-1](https://user-images.githubusercontent.com/68932309/226062613-56ffba98-102b-4076-897d-a98ab37b9d49.jpg)
![frame9-1](https://user-images.githubusercontent.com/68932309/226062617-51287d8b-3aa6-4165-9765-fa228699f714.jpg)

## Results:
### Comparing to Lucas Kanade optical flow, Farneback optical flow provides better interpolation with less visible artifact in interpolated frames. Although there are still some artfacts visible in the area of image with drastic brightness change. We suspect this is due to the assumption of algorithm that the pixel values remain invariant between frames. As for interpolation with Lucas Kanade method, the resulting images exhibit large amount of artifacts. This is potentially due to limitation of Lucas Kanade method used as a dense optical flow even though conceptually it is a sparse motion estimation based only on good features (i.e. corners).

## Problems Encountered
#### Inexperience of language and tools
We had to learn many tools that why haven't had much experience using and it took a quite some time to learn how to navigate and implement what we wanted. 

Uploading video for testing and implementation to google colab took very long.
We had to adapt to use shorter videos with lower resolutions. 

## Next Steps
If we had more time and resources, we would like to implement our own working Farneback Optical Flow algorithm that is similar to the one the is implemented by OpenCV.
We would also like to experiment with different frame rates using a variety of video lengths and resolution.

## How does your approach differ from others? Was that beneficial?
We learned and implemented the sparse Lucas Kanade in class and wanted to explore the dense Farneback Optical Flow method in our project.
It was challenging but it was a great learning experience. 
