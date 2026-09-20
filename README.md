# Wisconsin Autonomous Perception Coding Challenge - Xin Chen Submission

## Method

For this challenge, I used the provided traffic light bounding boxes to find the center pixel of the traffic light in each frame.

For each frame, I matched it with the corresponding npz file and used the center pixel of the traffic light to look up its 3D position relative to the camera.

I skipped frames where the data returned NaN values.

Since we want the traffic light as origin, I reversed the coordinates to find car's position relative to the traffic light instead of the traffic light's position relative to the car.

I then rotated the coordinates so that the starting direction from the car to the traffic light aligned with the X-axis as requested by the world frame definition in the challenge.

Finally, I plotted the car's trajectory in bird's-eye-view coordinates and created an animated version of the trajectory.

## Assumptions

I assumed that the car did not change its heading very much during the short video, so I assumed the camera orientation as approximately aligned with the initial world frame.

I also used the center pixel of the traffic light bounding box to get the depth value. Because some of the depth values were noisy or invalid, so I skipped those frames.

## Results

The final trajectory shows the car following a slightly curved path relative to the traffic light.
