# task3
Sequence classification for propaganda dataset (QCRI)

1. pip install -r requirements.txt 
2. Run python -m spacy download en
3. dataset_train.csv and dataset_dev.csv are created from datasets_v5 by running preprocess.py on it. To create a different 
dataset, change the parameters appropriately in preprocess.py.
4. Create folder ./exp - This is where the logs and model states will be stored for training runs. 
5. Run the trainer, for example 
python train.py --expID test_run --trainDataset dataset_train.csv --valDataset dataset_dev.csv --model bert-base-cased --LR 3e-5 --trainBatch 12 --nEpochs 5
6. Run python predict.py to get output in the character level. Change parameters inside the file accordingly.


# Evaluation 
cd tools # assuming the predictions are in file dev.labels and the gold labels in the folder task3-gold-labels/dev-task3-labels
	 # the following command evaluates the predictions on the development set 
python task3_scorer_onefile.py -s dev.labels -r task3-gold-labels/dev-task3-labels -t propaganda-techniques-names.txt
