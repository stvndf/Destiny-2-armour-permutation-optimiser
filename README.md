# Destiny 2 Armour Permutation Optimiser

* Returns the most-to-least optimal gear permutation from the imported dataset
    * Download armour data (includes equipped, inventory and vault gear) from DIM (Destiny Item Manager)
* More flexible than DIM's loadout optimiser
* Functionality includes:
    * Simple filtering of preferred gear to input into the algorithm
    * Easy prioritisation of selected stat categories (e.g. mobility, resilience, etc)
    * Option to add masterwork bonuses to determine best (non-masterworked) armour pieces to select for masterworking
* Built using Python & Pandas

## Example
Determining optimal loadouts containing Helm of Saint-14, sorted by resilience & recovery
```python
input_df = df[~( (df['Type'] == "Helmet") & (df["Name"] != "Helm of Saint-14"))]
input_df = input_df[ ~( (input_df['Tier'] == "Exotic") & (input_df["Name"] != "Helm of Saint-14") ) ]

saint14_mw = process_gear(input_df, sort_tier_by=["Resilience, Recovery"], masterwork="Helmet")
```
