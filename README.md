# CT Image Segmentation Using Manual Thresholding

## 1. Objective

The objective of this experiment is to investigate manual threshold-based segmentation of a suspected tumor in a brain CT image. The process involves loading the image, identifying a Region of Interest (ROI), analyzing its intensity histogram, and evaluating the limitations of manual threshold selection.

## 2. Methodology

### Step 1: Loading and displaying the CT image

The CT image (`Tumor1.jpg`) was loaded using the OpenCV library (`cv2`) in grayscale format.

The grayscale JPG image contains pixel intensity values ranging from 0 (black) to 255 (white).

The image was then displayed using Matplotlib to visually inspect the brain structures and identify the approximate location of the suspected tumor.

### Step 2: Selecting the Region of Interest (ROI)

After visually inspecting the CT image, the approximate center coordinates of the suspected tumor were selected manually.

- Center coordinates: **(x = 125, y = 90)**
- Square size: **55 × 55 pixels**

A square ROI was defined around the selected center point, and a red rectangle was drawn on the original image to visualize the selected region.

The ROI was then cropped from the grayscale image for further analysis.

### Step 3: Calculating the ROI intensity histogram

An intensity histogram was calculated using the pixel values within the selected ROI.

The histogram was generated using Matplotlib with 256 bins, corresponding to the possible grayscale intensity values from 0 to 255.

The horizontal axis represents pixel intensity, while the vertical axis represents the number of pixels at each intensity.

### Step 4: Histogram analysis and limitations of manual threshold selection

The ROI histogram shows that most pixel intensities are concentrated approximately between **90 and 180**, with a prominent peak around **125–130**.

Several overlapping local peaks are visible, and there is no clearly defined valley separating the intensity distributions.

Furthermore, the suspected tumor and surrounding brain tissue appear to have similar grayscale intensity values. This makes it difficult to distinguish the two regions using pixel intensity alone. The histogram by itself cannot confirm which intensities correspond to tumor or surrounding tissue.

As a result, selecting a single threshold manually is challenging because the intensity ranges of different tissues may overlap. A low threshold may include surrounding healthy tissue, while a high threshold may exclude parts of the suspected tumor.

This highlights a limitation of manual global thresholding: it relies only on pixel intensity and does not consider anatomical structure or spatial relationships.

## 3. Conclusion

The experiment illustrates an important limitation of manual global thresholding in CT image segmentation.

When the suspected tumor and surrounding brain tissue have similar pixel intensities, selecting an appropriate threshold becomes challenging and subjective.

Additional methods, such as Otsu's automatic thresholding and adaptive thresholding, can be investigated and compared to determine whether they provide better segmentation results. Segmentation quality would need to be assessed against a suitable reference rather than inferred from the histogram alone. 

