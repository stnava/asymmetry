asymmetry
=========

asymmetry analysis with ANTs

requires ANTs version Oct. 30, 2013 or later 

run the asymmetry command mapping an input to a symmetric template 

`asymmetry.sh -d 2 -a 0 -f data/symm_t.nii.gz -m data/asymm_s.nii.gz -o XXXX`

you can build a symmetric template by running [antsMultivariateTemplate construction](https://github.com/ntustison/TemplateBuildingExample)

where you input images and their reflections - J and reflection(J) around the axis of symmetry

you can reflect an image by:

`ImageMath 2 reflection.mat ReflectionMatrix r16slice.nii.gz 0 `
`antsApplyTransforms -d 2 -i r16slice.nii.gz -o test.nii.gz -t reflection.mat -r r16slice.nii.gz`

the above analysis produces an asymmetry image based on the jacobian.

![template](https://github.com/stnava/asymmetry/blob/master/data/symm_t.jpg?raw=true)
![Asymmetry](https://github.com/stnava/asymmetry/blob/master/data/asymm_s.jpg?raw=true)
![AsymmMeasurement](https://github.com/stnava/asymmetry/blob/master/data/asymm_measure.jpg?raw=true)
![Diff](https://github.com/stnava/asymmetry/blob/master/data/diff_of_images.jpg?raw=true)
