# morphometrixnonadult
osteoarchaeology morphometrics



This is a continuation of my osteoarchaeology BSc dissertation at  Durham University which looked at non-adult sex estimation techniques. I have here a set of images of the hip bones from around 65 individuals from the York Fishergate House Skeletal Collection housed at our department.
The auricular surface as a sex predictor has been investigated by Luna et al. 2017 using statistical methodologies on metric traits from images. I am now keen to develop a machine learning method to classify my data to take this model and approach one step further. So far, I have manually used Affinity to paint masks for the auricular surfaces on all the individuals I photographed, then processed them and ran PCA. The next step is to access other documented collections to validate sex estimation techniques.

![masks](masks.gif?raw=true "masks")

Consider this grey literature until published, and please credit if used or remixed, Teodor Tranca 2025, Durham University

SETUP
Windows: py -m venv .venv
```
.venv\Scripts\python.exe -m pip install -r requirements.txt
.venv\Scripts\python.exe -m jupyterlab
```

macOS/Linux: python3 -m venv .venv
```
.venv/bin/python -m pip install -r requirements.txt
.venv/bin/python -m jupyterlab
```


NOTEBOOK 1

Auricular-final is for exploring the data with Fourier Transforms to see what morphologies can be clustered.

- Open auricular_final.ipynb. Run cells in order and inspect QC.
- The final CSV includes only 68 mask individuals, sorted numerically. 20 have canine values (192 measurements).
- Notebook syntax and JSON checked; not run end-to-end on the 111 masks.

NOTEBOOK 2

The Luna Grid ratios notebook is using a methodology from Luna, Aranda & Santos (2017), International Journal of Osteoarchaeology 27:898–911, [doi:10.1002/oa.2604](https://onlinelibrary.wiley.com/doi/abs/10.1002/oa.2604), pp.900–902

This Jupyter notebook should simplify data collection.

- Install: ```python -m pip install -r luna_requirements.txt```
- Launch local JupyterLab in that project, open notebook, run cells in order.
- Automatic batch saves draft grids and unreviewed ratios. Editor allows anatomical correction and residual rotation; explicit approval required for final measurements.

![Screenshot of UI](Screenshot_UI_grid.png?raw=true "Screenshot of UI")

- Left-first selection; right-only automatically reflected. Use original unreflected masks, not previously reflected analysis outputs. Configure RIGHT_ALREADY_REFLECTED if necessary.
- Save each approved grid, then run export cell. Change observer/session for repeats. Annotations persist, UI starts with fresh suggestions for blinded reannotation.


- No true missing side is fabricated; right-derived measurements retain source side.
- No sex classifier; age validity of original study 7–18 years.
- Notebook JSON, Python syntax and grid arithmetic checked. Not run on the full local mask collection; anatomical landmark suggestions are not validated.
