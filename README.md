# Audio-Visual Scene-Aware Dialog

code for the paper:
**[AVSD][1]**
Huda Alamri, Vincent Cartillier, Abhishek Das, Jue Wang, Stefan Lee, Peter Anderson, Irfan Essa, Devi Parikh, Dhruv Batra, Anoop Cherian, Tim K. Marks, Chiori Hori

duplicate repo. from: https://github.com/batra-mlp-lab/avsd

website:
[video-dialog.com][3]

This code has been developed upon [batra-mlp-lab/visdial-challenge-starter-pytorch][2]

## Setup
```sh
# create and activate environment
conda env create -n avsd -f=env.yml
conda activate avsd
```

## Data
 * download 'split'.json data at: video-dialog.com


## Workflow

 * Build dialogs json file with otions using ```makejson_with_options.py``` (output: 'split'_options.json)
 * Adapt JSON format using ```convert_json_to_visdial_style.py``` (output: 'split'_options_2.json can be renamed after to 'split'_options.json)
 * Build tokenized captions, dialogs and image paths with ```prepro.py``` (output: dialogs.h5 and params.json)
 * Build the image features (if working with images) using ```prepro_img_vgg16.lua``` or ```prepro_img_resnet.lua```  from the [batra-mlp-lab/visdial-challenge-starter-pytorch][2] (output: data_img.h5)
 * Build video features I3D (output: data_video.h5) [https://github.com/piergiaj/pytorch-i3d.git][5]
 * Build audio features AENET (output: data_audio.h5) [https://github.com/znaoya/aenet.git][4]


 * Training: run train.py
 * evaluation: run evaluate.py --use_gt
 * visualize: run viz.py

## If you find this code useful in your research, please consider citing:
```
@inproceedings{alamri2019audio,
  title={Audio visual scene-aware dialog},
  author={Alamri, Huda and Cartillier, Vincent and Das, Abhishek and Wang, Jue and Cherian, Anoop and Essa, Irfan and Batra, Dhruv and Marks, Tim K and Hori, Chiori and Anderson, Peter and others},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={7558--7567},
  year={2019}
}
```

## License
BSD

[1]: https://arxiv.org/abs/1806.00525
[2]: https://github.com/batra-mlp-lab/visdial-challenge-starter-pytorch
[3]: https://video-dialog.com
[4]: https://github.com/znaoya/aenet.git
[5]: https://github.com/piergiaj/pytorch-i3d.git
