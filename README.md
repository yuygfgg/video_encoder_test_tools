# video_encoder_test_tools

### Tools for testing the quality of different argument of encoder and their values

Only supports vapoursynth as source.  
Use absolute path in source filter, or path relative to working folder, which not created yet you have to imagine.

### Usage

```
usage: encoder_test_tools.py [-h] --src SRC --encoder {x264,x265,svtav1,vpxenc} [--base-args BASE_ARGS] [--test-arg TEST_ARG]
                             [--values VALUES [VALUES ...]] [--quality QUALITY [QUALITY ...]] [--workspace WORKSPACE]
                             [--suffix SUFFIX] [--link LINK] [--twopass] [--vmaf-model {0,1,2,3}]
                             [--metrics {psnr-y,psnr-hvs,ssim} [{psnr-y,psnr-hvs,ssim} ...]] [--ref REF]

Video encoder testing tool

options:
  -h, --help            show this help message and exit
  --src SRC             Input video file (VapourSynth script)
  --encoder {x264,x265,svtav1,vpxenc}
                        Encoder to test
  --base-args BASE_ARGS
                        Base encoder arguments (default: --y4m --crf {q} --{test} {passopt} -o "{o}" -)
  --test-arg TEST_ARG   Parameter to test (default: preset)
  --values VALUES [VALUES ...]
                        Values for test parameter. Can be numbers or strings. If not specified, will test with/without the test-
                        arg
  --quality QUALITY [QUALITY ...]
                        Quality (CRF) values to test (default: [24, 27, 30, 33, 36])
  --workspace WORKSPACE
                        Working directory (default: test-arg name)
  --suffix SUFFIX       Output file suffix (default: auto-detected from encoder)
  --link LINK           Character to link test-arg and value (default: space)
  --twopass             Enable two-pass encoding
  --vmaf-model {0,1,2,3}
                        VMAF model to use (0:vmaf, 1:vmaf_neg, 2:vmaf_b_bagging, 3:vmaf_4k) (default: 0)
  --metrics {psnr-y,psnr-hvs,ssim} [{psnr-y,psnr-hvs,ssim} ...]
                        Additional metrics to measure (default: ['ssim'])
  --ref REF             Index of reference encoding for BD-rate calculation (default: 0)
```

---

### output screenshots

![t.PNG](https://i.loli.net/2020/11/10/pKCkDfYtG95FliT.png)

---

### requirements:

python3.10+

vapoursynth and plugins

pyecharts

BeautifulSoup4

bjontegaard
