# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 7 steps：
1. converting the images to grayscale
2. applying a Gaussian Noise kernel
3. applying the Canny transform
4. applying region of interest image mask
5. applying hough transform to get line segments
6. using line segments to get a single line on the left and right lanes
7. drawing left and right lines on the initial image

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by:
1. using line segments slope sign to determine if the segment belongs to left or right lane
2. using RANSAC to fit left and right lines
3. using line coefficients to calculate the x value when y equals to ROI top and bottom of left and right lines
4. drawing a line from ROI top point to bottom point of left and right lines


### 2. Identify potential shortcomings with your current pipeline


Potential shortcoming of current approche would be:
1. when the lane is curved, it is not appropriate to fit a line, better to fit a curve
2. using line segments slope sign to determine if it belongs to left or right lane is too brief

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

Possible improvement would be:
1. fitting lane with curve instead of line
2. better approche to generate left and right line segments candidate
3. parameters tuning
4. handle shadows and reflections of the image
