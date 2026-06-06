# PPoll

PPoll is a multi-crop hierarchical dataset and benchmark for precision pollination perception. It is designed for operation-oriented agricultural vision, where a model must not only localize flowers but also identify visible stigma regions and actionable pollination points.

## Benchmark Tasks

PPoll defines three benchmark tasks:

1. **Flower Instance Detection**  
   Detect flower instances in each image using bounding boxes.

2. **Stigma Instance Segmentation**  
   Segment the visible stigma region for each flower instance.

3. **Pollination Point Localization**  
   Localize the target point for robotic pollination on each valid flower instance.

## Repository Contents

This repository currently provides:

- sample images and annotations;
- baseline training and evaluation scripts;
- sample data for the Standard and Challenging protocols;
- checkpoint preparation instructions;
- data access and usage terms.

The full PPoll dataset is not publicly released before publication. Researchers who need access to the complete dataset should contact the maintainers and sign the PPoll Data Use Agreement.

## Sample Data Structure

Sample data are provided under `samples/`:

```text
samples/
  data_standard/
    train/
      images/
      annotations_with_ids/
    val/
      images/
      annotations_with_ids/
    test/
      images/
      annotations_with_ids/
  data_hard/
    train/
      images/
      annotations_with_ids/
    val/
      images/
      annotations_with_ids/
    test/
      images/
      annotations_with_ids/
```

`data_standard` corresponds to the Standard Protocol, while `data_hard` corresponds to the Challenging Protocol.

## Annotation Format

Each image is paired with a JSON annotation file in `annotations_with_ids`. The annotations include:

- flower bounding boxes;
- visible stigma region polygons;
- pollination point annotations;
- instance IDs linking the flower, stigma region, and pollination point.

The instance ID enables hierarchical instance-level evaluation across the three tasks.

## Baseline Models

The benchmark includes representative baselines for each task:

- **Flower instance detection:** YOLOv8, RT-DETR, Faster R-CNN
- **Stigma instance segmentation:** YOLOv8-seg, Mask R-CNN, Mask2Former
- **Pollination point localization:** YOLOv8-pose, YOLO11-pose, Keypoint R-CNN

## Results

Baseline results are summarized in [RESULTS.md](RESULTS.md). Annotation examples and qualitative prediction examples are provided below for visual inspection.

## Annotation Examples

The following examples show original annotations, including flower bounding boxes, visible stigma regions, pollination points, and instance-level correspondence.

**Standard Protocol**

![Standard annotation example 1](assets/annotation_examples/standard/a22bcb25-8fe6-446d-a7b1-ed64536e3ab9.png)
![Standard annotation example 2](assets/annotation_examples/standard/b7e6924a-4cc9-4463-91ca-29128fe35df2.png)
![Standard annotation example 3](assets/annotation_examples/standard/fb9f2303-384b-4396-9574-87a21bcebf1a.png)

**Challenging Protocol**

![Challenging annotation example 1](assets/annotation_examples/challenging/6a8ef323-9f75-465f-b6a2-a2285744aef5.png)
![Challenging annotation example 2](assets/annotation_examples/challenging/bd38ca96-2d7e-43bd-99b0-24a7a0e98f08.png)
![Challenging annotation example 3](assets/annotation_examples/challenging/bfd95cad-dca0-423e-9dc8-104c0cd1c327.png)

## Qualitative Prediction Examples

### Flower Instance Detection

**Standard Protocol**

![Standard detection example 1](assets/qualitative_results/detect/standard/0bb29d0a-1198-4ec9-8267-fe6896e0a4c9.jpg)
![Standard detection example 2](assets/qualitative_results/detect/standard/0e6aa8aa-9f61-456e-afa6-a533607def35.jpg)
![Standard detection example 3](assets/qualitative_results/detect/standard/760a32c4-7e33-4bba-add3-eee6721dbd7d.jpg)

**Challenging Protocol**

![Challenging detection example 1](assets/qualitative_results/detect/challenging/e8f5a687-25a1-46f2-a363-e9686b9e09f9.jpg)
![Challenging detection example 2](assets/qualitative_results/detect/challenging/f49b6e97-0f02-4d4a-ad79-2e892adf85eb.jpg)
![Challenging detection example 3](assets/qualitative_results/detect/challenging/f9fa06e9-2961-494b-9501-e3c55e801332.jpg)

### Stigma Instance Segmentation

**Standard Protocol**

![Standard segmentation example 1](assets/qualitative_results/segment/standard/0bb29d0a-1198-4ec9-8267-fe6896e0a4c9.jpg)
![Standard segmentation example 2](assets/qualitative_results/segment/standard/0e6aa8aa-9f61-456e-afa6-a533607def35.jpg)
![Standard segmentation example 3](assets/qualitative_results/segment/standard/760a32c4-7e33-4bba-add3-eee6721dbd7d.jpg)

**Challenging Protocol**

![Challenging segmentation example 1](assets/qualitative_results/segment/challenging/e8f5a687-25a1-46f2-a363-e9686b9e09f9.jpg)
![Challenging segmentation example 2](assets/qualitative_results/segment/challenging/f49b6e97-0f02-4d4a-ad79-2e892adf85eb.jpg)
![Challenging segmentation example 3](assets/qualitative_results/segment/challenging/f9fa06e9-2961-494b-9501-e3c55e801332.jpg)

### Pollination Point Localization

**Standard Protocol**

![Standard pose example 1](assets/qualitative_results/pose/standard/0bb29d0a-1198-4ec9-8267-fe6896e0a4c9.jpg)
![Standard pose example 2](assets/qualitative_results/pose/standard/0e6aa8aa-9f61-456e-afa6-a533607def35.jpg)
![Standard pose example 3](assets/qualitative_results/pose/standard/760a32c4-7e33-4bba-add3-eee6721dbd7d.jpg)

**Challenging Protocol**

![Challenging pose example 1](assets/qualitative_results/pose/challenging/e8f5a687-25a1-46f2-a363-e9686b9e09f9.jpg)
![Challenging pose example 2](assets/qualitative_results/pose/challenging/f49b6e97-0f02-4d4a-ad79-2e892adf85eb.jpg)
![Challenging pose example 3](assets/qualitative_results/pose/challenging/f9fa06e9-2961-494b-9501-e3c55e801332.jpg)

## Checkpoints

Model weights are not included in this public repository.

Please manually download or prepare the required pretrained weights before running the baseline scripts. The `checkpoints/` directory can be used to store pretrained weights locally.

## Data Access

The complete PPoll dataset is available upon request for academic research only. To request access, please provide:

1. Name
2. Affiliation
3. Position
4. Institutional email
5. Research purpose
6. Agreement not to redistribute the dataset
7. Agreement to cite the PPoll paper after publication

Please see [DATA_USE_AGREEMENT.md](DATA_USE_AGREEMENT.md) for the data usage terms.

## Citation

The citation will be added after publication.

## Contact

Please contact the maintainers for full dataset access.

Contact email: wuj49397@gmail.com
