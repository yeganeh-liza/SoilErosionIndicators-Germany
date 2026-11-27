# Soil Erosion Indicators in Germany

Which type of soil erosion affects the largest share of Germany's land?
This project compares four soil erosion indicators using QGIS and Python,
by calculating the percentage of unhealthy pixels for each indicator.

## Indicators
Harvest erosion, tillage erosion, water erosion and wind erosion.

## Data
- **Soil degradation indicators:** multi-band dataset from the European
  Soil Data Centre (ESDAC), JRC (500 m resolution, EPSG:3035;
  0 = healthy, 1 = unhealthy, 127 = NoData). The raw data is **not
  included** in this repository, as the ESDAC licence does not allow
  passing it on to third parties. It can be requested from ESDAC:
  https://esdac.jrc.ec.europa.eu
- **Germany boundary:** [maps.pispace.eu](https://maps.pispace.eu/data/germany/)

## Method
1. **QGIS:** reprojected the boundary to EPSG:3035, clipped the raster to
   Germany, extracted the four indicator bands and generated pixel statistics.
2. **Calculation:** unhealthy share (%) = unhealthy pixels / valid pixels × 100
   (valid = healthy + unhealthy; NoData excluded). See
   `SoilEro_Indicators_analysis.xlsx`.
3. **Python:** visualised the results as a bar chart.

## Results
| Indicator | Unhealthy (%) |
|---|---|
| Tillage erosion | 25.97 |
| Water erosion | 17.52 |
| Harvest erosion | 5.06 |
| Wind erosion | 1.56 |

Tillage erosion affects the largest share of German land (about 26 %),
followed by water erosion (about 18 %). Harvest and wind erosion affect
only small shares (about 5 % and 2 %).

## Tools
QGIS, Python (pandas, Matplotlib), Excel

## Reference
Panagos, P., et al. (2024). How the EU Soil Observatory is providing solid
science for healthy soils. *European Journal of Soil Science*, 75(3), e13507.
https://doi.org/10.1111/ejss.13507
