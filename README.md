# Image Segmentation Using K-Means Clustering

This project demonstrates the application of K-Means clustering for image segmentation, simplifying images by grouping pixels with similar colors into clusters.

## Key Features

### K-Means Clustering for Image Segmentation
- **Dynamic Clustering:** Experiment with different numbers of clusters (`K`) to observe the impact on image segmentation.
- **Simplification vs. Detail:** Low `K` values produce simplified images, while higher `K` values retain finer details.

### Visual Results
- Side-by-side comparison of the original image with segmented versions for various `K` values.

## Project Workflow

### 1. Importing Libraries
- Libraries used include:
  - `skimage` for image processing.
  - `matplotlib` for visualization.
  - `sklearn.cluster.KMeans` for clustering.

### 2. Loading the Image
- Image is loaded from a URL and displayed using `matplotlib`.

### 3. Preprocessing the Image
- Image is flattened into a 2D array of pixels for clustering.

### 4. Defining the K-Means Segmentation Function
```python
def kmeans_seg(image, k):
    kmeans = KMeans(n_clusters=k)
    kmeans.fit(X)

    # Generate the segmented image
    segmented_image = kmeans.cluster_centers_[kmeans.labels_]
    segmented_image = segmented_image.reshape(image.shape)

    return segmented_image
```

### 5. Experimenting with `K` Values
- Experiment with values such as `K = [2, 5, 10, 20]` to explore the trade-off between simplification and detail.

### 6. Displaying Results
- Visualize the original image alongside segmented images for each `K` value using `matplotlib`.

## Results and Observations

### K-Means Clustering Outcomes
- **K = 2:** Simplifies the image into two dominant colors, losing significant details.
- **K = 5:** Captures a few primary colors while retaining some structure.
- **K = 10:** Strikes a balance between detail and simplicity.
- **K = 20:** Retains most original details with finer segmentation.

### Visualization Example
- A side-by-side comparison is generated to observe the impact of varying `K` values on the segmentation quality.
