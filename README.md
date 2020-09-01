# Semi-supervised-Image-Semantic-Segmentation
train：

GAN-base：

python train.py --snapshot-dir snapshots \
                --partial-data 0.125 \
                --num-steps 20000 \
                --lambda-adv-pred 0.01 \
                --lambda-semi 0.1 --semi-start 5000 --mask-T 0.2

GAN-base+gp：

python train_gp.py --snapshot-dir snapshots \
                --partial-data 0.125 \
                --num-steps 20000 \
                --lambda-adv-pred 0.01 \
                --lambda-semi 0.1 --semi-start 5000 --mask-T 0.2

GAN-base+gp+ed：

python train_gp_lpls.py --snapshot-dir snapshots \
                --partial-data 0.125 \
                --num-steps 20000 \
                --lambda-adv-pred 0.01 \
                --lambda-semi 0.1 --semi-start 5000 --mask-T 0.2

evaluate：

python evaluate_voc.py --restore-from snapshots/VOC_20000.pth \
                       --save-dir results
