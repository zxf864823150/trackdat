# trackdat

## Setup datasets

We show how to set up the VOT 2018 dataset as an example.

To download the compressed dataset:
```bash
VOT_YEAR=2018 bash scripts/download_vot.sh dl/vot2018
```
To unpack the compressed dataset to a temporary directory:
```bash
temp=$(mktemp -d)
bash scripts/unpack_vot.sh dl/vot2018 $temp/vot2018
```
To compress this dataset into a single tar-ball:
```bash
tar -cf tar/original/vot2018.tar -C $temp vot2018)
```
To extract the dataset, resize all images and save as a tar-ball:
```
sbatch scripts/slurm/resize.sh tar/ vot2018 fit 480x480
```