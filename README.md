> Facemask recognition 
Recognizing and classifying images into correctly /incorrectly / not masked  
using yolov3

## Prerequisities
opencv
numpy

## Gather dataset of Face, Mouth and Nose
used OPEN IMAGES to gather Train and TEST dataset with ANNOTATION  for Human nose,face and mouth

To download the dataset :

1.From the desired directory you wish to copy the "dataset_downloader" folder 
	```
	git clone https://github.com/suhas-boop/facemask_detection_with-_yolov3/tree/main/dataset_downloader
	```
2. Change directories to "dataset_downloader":
	```
	cd dataset_downloader
	```
3. Type in the following command:
```
	python main.py downloader --classes Human_nose Human_mouth Human_face --type_csv train --limit 1200 
```
[image](https://drive.google.com/file/d/1p2I-yhFz6lY6kmJU9hd9Q86t7wvckS2s/view?usp=sharing)


4.Edit  classes.txt ,rewrite it with to
```
"Human mouth"
"Human face"
"Human nose"
```

5.Back on the command line/Terminal 
```
 python convert_annotations.py
```

6.remove all the Label folder from each and  put all the three folder into one and zip it and name it to "obj"

7. Upload it to Google drive into a folder named yolov3

## Configuring Files for Training
This step involves properly configuring your custom .cfg file, obj.data, obj.names and train.txt file.

1.obj.names and obj.data
Create a new file within a code or text editor called obj.names and you will make this file exactly the same as your classes.txt in the dataset generation step.

2.You will also create a obj.data file and fill it in like this (change your number of classes accordingly, as well as your backup location)

This backup path is where we will save the weights to of our model throughout training. Create a backup folder in your google drive and put its correct path in this file.

```
classes=3
train=data/train.txt
valid=data/test.txt
names=data/obj.names
backup=/mydrive/yolov3/backup/
```
## Training the model 


Click [here](https://colab.research.google.com/drive/1-sXTffc8Xe2De7QmxxvT5KGGB0bguAmF?usp=sharing)to access the code to build a the yolov3 model 


open up the colab notebook above

run the code 

## Run your Mask detector
1. Download the .weights file from backup 

2. Download the deploy file from the repo. And run it 

You have done it! You now have a custom mask detector to make your very own detections. Time to test it out and have some fun!








To just give it a try ,[download](https://drive.google.com/drive/folders/1dkTaH6Aj-1zArTsa4aaceFYdW-kF2D2_?usp=sharing)the whole folder 

and 
```
cd {directory in which u downloaded the folder}
```
run objdetection.py 
```
python objdetection.py 
```