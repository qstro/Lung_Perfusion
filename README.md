# Script for lung segmentation and lobar fractional iodine calculation (batch processing)

Accompanying Jupyter notebook for the research article: 

Strotzer QD, Heidemanns S, Mayr V, Stuerzl R, Meiler S, Schmidt D, Blaas S, Grosse J, Hellwig D, Stroszczynski C, Hamer OW (2023) Head-to-Head Comparison of Dual-Source and Split-Beam Filter Multi-Energy CT versus SPECT/CT for Assessing Lobar Lung Perfusion in Emphysema. Radiology: Cardiothoracic Imaging. https://doi.org/10.1148/ryct.220273 

Provided data is structured as described below, DICOM slices are loaded, lobar segmentation is applied, and lobar volume and perfusion fraction are calculated for each case stored in cases.txt. Results are saved in tabular format as *results.xlsx*.

## Prerequisites:
- SimpleITK
- numpy
- pandas
- lungmask
- os

## Args: 
- cases.txt: a text file containing case ids (one per line)
- for each case, a folder containing a structural chest CT (one DICOM file per slice) 
and an equally spaced dual-energy-CT-derived iodine map (e.g., exported from syngo.via CT Dual Energy)

## Output:
- caseID_segmentation.nii.gz
- caseID_backdrop.nii.gz
- caseID_iodine_map.nii.gz
- results.xlsx

## Data Structure: 

```bash
main_directory/
├── caseID_01/
│   ├── backdrop/ # Contains DICOM-files (one per slice)     
│   └── iodine_map/ # Contains DICOM-files (one per slice)   
├── caseID_02/
│   ├── ...      
...    
└── cases.txt     
```

## License:
```python
__author__ = "Quirin D. Strotzer"
__license__ = "Apache License 2.0"
__version__ = "1.0"
__email__ = "quirin.strotzer@ukr.de"
```

## Cite as:
Strotzer QD, Heidemanns S, Mayr V, Stuerzl R, Meiler S, Schmidt D, Blaas S, Grosse J, Hellwig D, Stroszczynski C, Hamer OW (2023) Head-to-Head Comparison of Dual-Source and Split-Beam Filter Multi-Energy CT versus SPECT/CT for Assessing Lobar Lung Perfusion in Emphysema. Radiology: Cardiothoracic Imaging. https://doi.org/10.1148/ryct.220273 
