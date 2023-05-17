# Persian Text Readability Dataset

A readability dataset in the Persian language.

## Information

| **Level** | # of texts | Avg. words per text |
| - | - | - |
| 0 (easy) | 2953 | 28.8 |
| 1 (medium) | 572 | 39.8 |
| 2 (hard) | 322 | 62.1 |
| Total | 3847 | 33.2 |

## How to load?

```python
import pickle

address = "/path/to/dataset.pkl"
with open(address, 'rb') as handle:
    dataset = pickle.load(handle) # <class 'list'[<class 'str'> <class 'int'> <class 'list'[<class 'float'> <class 'float'> <class 'float'>]>]>
```

## What is in the dataset?

The dataset (pickle file) contains a list of data points. Each data point includes a `string` (text), an `int` (label), and a list of `floats` (rater readability level). The `text` is in Persian and rated by at least three raters. The `label` is the score given to the text by the raters. Only texts with over 80% agreement between raters are included. The `rater readability level` is the average bias of raters toward each readability level. For example, a rater readability level of `[0.1, 0.5, 0.4]` tells you that the raters of this text have scored other texts `0` 10% of the time, `1` 50% of the time, and `2` 40% of the time. Utilization of this metric is critical as raters have different education and reading levels.

## Acknowledgement

Our sincere gratitude goes out to the undergraduate computer engineering students at the K.N. Toosi University of Technology who participated in gathering annotations.

## Citation

```bibtex
@inproceedings{mohammadi2020machine,
  title={A machine learning approach to Persian text readability assessment using a crowdsourced dataset},
  author={Mohammadi, Hamid and Khasteh, Seyed Hossein},
  booktitle={2020 28th Iranian Conference on Electrical Engineering (ICEE)},
  pages={1--7},
  year={2020},
  organization={IEEE}
}
```
