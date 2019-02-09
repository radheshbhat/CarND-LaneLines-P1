# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps.
1. Convert the images to grayscale
2. Perform Gausian smoothing and apply Canny edge detection
3. Select region of interest and mask other areas of the image
4. Apply Hough Transform to detect lane lines
5. Superimpose the lane lines on the original image
In order to draw a single line on the left and right lanes, I modified the draw_lines() function by calculating slope and center of each line. Based on the slope, sorted it into right or left lane line. Then, calculate the average slope and the center of right and left lane. Using Y coordinates, based on Region of Interest, figured out the X co-ordinates using the average slope and center point of lane lines [equation used: (y-y') = M (x-x')]
Similar pipeline is used for videos.


### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when road is curvy since the slope conditions used for detection are empirical. This is evident when I tried with optional challenge video.
Another shortcoming could be static region of interest limiting generalization


### 3. Suggest possible improvements to your pipeline
A possible improvement would be to have dynamic ROI and slope conditions
