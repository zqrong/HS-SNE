# HS-SNE

HS-SNE is a high-dimensional data visualization method based on a hypersphere representation system, effectively resolving the challenge of similarity measurement in high-dimensional data visualization.

**The original paper is currently under review.** However, you can access a previous version at [https://openreview.net/pdf?id=2Kf1AIdeyt](https://openreview.net/pdf?id=2Kf1AIdeyt).

If you find this method helpful, please consider citing our work. Thank you!

## Quickstart

```python
import pandas as pd
import scanpy as sc
import seaborn as sns
from hs_sne import HSSNE

data = sc.read_h5ad('PATH/TO/H5AD/DATA').X

hssne = HSSNE(n_components=2, perplexity=30, metric='geodesic', verbose=True)
loc = hssne.fit_transform(data)

loc_df = pd.DataFrame(loc)
sns.scatterplot(loc_df, x=0, y=1)
plt.xlabel('HS-SNE 0')
plt.ylabel('HS-SNE 1')
plt.show()
```

## Contact

Ziqi Rong - <ziqirong@umich.edu>
