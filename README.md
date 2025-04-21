# KS-KSS Dataset

**Please note that this repository is moved to a new repository. Most of the dataset files are not in this repository. This README.md file will also not be updated after 2025/04/21. Link - https://github.com/sankamohotttala/KS-KSS-Dataset/tree/main**

This folder contains a curated subset of the Kinetics-600 dataset. These classes have been selected to represent a diverse range of physical activities relevant to children's action recognition tasks.

## Included Action Classes

| Class Name               | Text File Name         | Kinetics-600 Class ID | KS-KSS Class ID |
|--------------------------|------------------------|------------------------|------------------|
| Hopscotch                | hopscotch_156.txt      | 156                    | 0                |
| Clapping                 | clapping_57.txt        | 57                     | 1                |
| Bouncing on trampoline   | jumping_30.txt         | 30                     | 2                |
| Baseball throw           | baseball_48.txt        | 48                     | 3                |
| Climbing tree            | climbingTree_68.txt    | 68                     | 4                |
| Cutting watermelon       | watermelon_83.txt      | 83                     | 5                |
| Squat                    | squat_330.txt          | 330                    | 6                |
| Pullups                  | pullups_255.txt        | 255                    | 7                |


## Dataset Composition Overview

Below is a visual summary of the class distribution in the KS and KSS datasets. These tables provide detailed breakdowns of:

- Total samples per class
- Child and adult data split
- Child data percentage

| KS Dataset | KSS Dataset |
|------------|-------------|
| ![KS Dataset](Dataset%20details/KS_dataset.png) | ![KSS Dataset](Dataset%20details/KSS_dataset.png) |


These images/tables provide useful insights into the number of clips per class, train/validation/test split ratios, and dataset coverage. There may be two,three files missing from KS-KSS dataset due to some errors.

More detailed information regarding the class distribution and dataset splits can be found in the Dataset details folder. 

## Content

We have added most of the data and some of the codes as well. A detailed breakdown of added/not-added features are given below:

 - [x] text files of child-adult annotated KS dataset
 - [x] RGB modality KS dataset
 - [x] JSON formatted KS dataset
 - [x] .npy and .pkl of KS with train-test split and without train-test split
 - [x] .tfrecord of KS-Full protocol
 - [ ] .tfrecord of KS other protocols (KS-Balanced, KS-Large, KS-Small)
 - [ ] text files of child-adult annotated KS dataset
 - [ ] RGB modality KS dataset
 - [ ] JSON formatted KSS dataset
 - [x] .npy and .pkl of KSS with train-test split
 - [x] .tfrecord of KSS-Full protocol
 - [ ] .tfrecord of KSS other protocols (KS-Balanced, KS-Large, KS-Small)
 - [ ] pre-processing codes
---

## Additional Folder Summaries

### `Processed data - KS/`  
This folder contains various versions of the **KS dataset in processed formats**, organized for streamlined preprocessing and experimentation:

- `1_kinetics-skeleton format/`:  
  KS dataset in **Kinetics-Skeleton JSON format**, used in pose-estimation-based pipelines. Enables standardized preprocessing.

- `2_full_npy_pkl_format/`:  
  The entire KS dataset in `.npy` and `.pkl` formats, without predefined train-test splits. Suitable for flexible KS-X protocol experiments.

- `3_final_split_and_tfrecord/`:  
  Final dataset used in paper and journal implementations, including all 8 classes and `.tfrecord` files aligned with the KS-Full protocol.

- `STGCN_PreProcess_code/`:  
  Python scripts for preprocessing, including:
  - JSON → `.npy` and `.pkl`  
  - `.npy`/`.pkl` → `.tfrecord`  

### `Processed data - KSS/`  
This folder contains the **fully processed KSS dataset**, ready for direct use in training and evaluation:
- `.npy` and `.pkl` data files
- `.tfrecord` files aligned with the **KSS-Full protocol**

These are the final cleaned and formatted data resources used for our KSS-based transfer learning experiments. For other protocols, custom splitting and `.tfrecord` generation may be needed.

---


## Accessing Raw Video References

The `Raw Dataset - KS` directory in this repository contains metadata files categorized under:

- `All adult`
- `all child`
- `All data (child and adult)`

Each file in these folders lists YouTube video IDs corresponding to a specific action class. The filenames follow the format `<class_name>_<class_id>.txt`, and each file contains a list of samples for that class.

These `.txt` files reference the original Kinetics-600 videos and can be used—along with the official [Kinetics-600 dataset](https://github.com/cvdfoundation/kinetics-dataset)—to obtain the RGB action clips. The official dataset provides CSV files containing key metadata such as:

- `youtube_id`
- `label` (action class)
- `start_time` and `end_time` of the action
- `subset` (train/val/test split)

Using this information, you can download the full videos and extract the relevant action clips.

Alternatively, already-trimmed action clips can be directly downloaded from the [CVD Foundation Kinetics Dataset](https://github.com/cvdfoundation/kinetics-dataset), which provides easy access to preprocessed segments. You can select the KS subset from this RGB dataset.


**Note**: The Kinetics-600 dataset must be separately obtained and is not included in this repository due to licensing and size constraints.

---

### Pre-Processed RGB Videos Available

For convenience, we have already trimmed and processed the required RGB videos corresponding to the KS dataset. These are available for direct access via Google Drive:

[Download RGB Videos (KS Dataset)](https://drive.google.com/drive/folders/1CaeN2eee1TLbrFxCGEdWhGis-AaZXvD7?usp=sharing)

This saves users the effort of video collection and processing, making it easier to directly work on downstream tasks like action recognition or transfer learning.



## Citation and Contact

If you have any questions regarding this dataset, detailed guidelines on usage or related codes, please contact:

**Sanka Mohottala**  
Email: `sanka.m@sliit.lk`, `divandyasm@gmail.com`

If you use this dataset in your research, please consider citing the following work that resulted this dataset:

```bibtex
@INPROCEEDINGS{sanka2022tencon,
  title   = {2D Pose Estimation based Child Action Recognition},
  author  = {Mohottala, Sanka and Abeygunawardana, Sandun and Samarasinghe, Pradeepa and Kasthurirathna, Dharshana and Abhayaratne, Charith},
  conference= {TENCON 2022 - 2022 IEEE Region 10 Conference (TENCON)},
  location = {Hong Kong, Hong Kong},
  publisher= {IEEE},
  year    = {2022},
  doi     = {10.1109/TENCON55691.2022.9977799},
}
