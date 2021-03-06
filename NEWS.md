# blscrapeR 0.4.2

## New Features
* Added stateName argument to get_bls_county() that allows user to specify a state or list of states.

* Added stateName argument to map_bls_county() that allows user to specify state(s) to map.

## Documentation
* Added mapping vignette.

* Added manual pages for the `county_map_data` and `state_map_data` internal data sets.

## Data
* Added tigris and broom packages to prep_maps.R in data-raw folder.

## Bug Fixes
* Fixed date argument in get_bls_county() and get_bls_state() to return the most recent date if argument is NULL.

* Added error handling to map_bls_state() and map_bls_county().

* Added tests for map_bls_state() and map_bls_county() to the /testthat directory.


# blscrapeR 0.4.1

## New Features

* Added quick functions to pull popular data sets from the API without the need of the user inputing a series id.

* Addded data argument to get_bls_county. If NULL the function will return the most recent month.

* Added the inflaction_adjust() function to help users with calculating inflation from the CPI. Since the API will only allow twenty years of data, the inflation function pulls data from a text file instead that allows the user to get CPI data back to 1947.

* Added more error handling to bls_api() function.

## Documentation

* Added documentation to get_bls_county() to explain the new date argument.

* Added package vignettes.


# blscrapeR 0.4.0

## Major Changes
* Added the `set_bls_key()` function to be used with the `bls_api()` function. The new function writes the user's api key to the Renviron.
The change is backward compatible since the user is sill able to enter their api key as a string. However, for security purposes, the stored key method is preferred and should be promoted.

* Added testthat directory and added `test_bls_api.R`. The tests won't affect anything in the package functionality, but will be useful for future testing.

## Deprecated Features
* Truncated the `bls_state_data()` function and added those features to the `get_bls_state()` function.

* Removed dplyr from imports since it's not necessary anymore. Added leaflet and cron to package recommends.

## Documentation
* Renamed `blscrape.R` to `bls_api.R` since the `bls_api()` function was the only function in that file.

* Added testthat to recommends.


# blscrapeR 0.3.2

## New Features

* Revised the map prep in `data-raw` to render smaller data frames, thereby making the total package size much smaller.

* Added a label title argument to map functions `bls_map_state()` and `bls_map_county()`

* Standardized colnames in all returned data frames throughout the package.

## Deprecated Features

* Truncated the `inflation()` function for now. The API seems to return adjusted dollar-values.

## Documentation

* Made documentation for helper functions invisable in the manual.

* Added News.Rd


# blscrapeR 0.3.1

## New Features

* Changed name of `county_map()` to avoid conflicts with other packages. I didn't mark this as a major release becasue no other functions in the package are dependant on this.

* Various fixes in map functions including removing unused themes and general code tidyness.

## Documentation

* Various fixes to examples.

* Made descriptions more robust.


# blscrapeR 0.3.0

## Major Changes

* Changed name of `get_data()` to `bls_api()` to avoid any problems in the global environment. Bumped the version to 0.3.0 because this is the primary workhorse function of the package.


# blscrapeR 0.2.1

## New Features

* Added custom maps rendered from shape files

## Major Changes

* Removed shape files from package data to cut down on size. This fundamentaly changes the way the mapping functions work. Opted instead, for spacial poly data frames rendered from the shapefiles.


# blscrapeR 0.2.0

## Major Changes

* Complete re-write of old `get_data()` function to pull from API only.

* Added arguments to `get_data()` to pass the BLS API perams.


# blscrapeR 0.1.0

## New features

* Added `bls_state_data()` function to pull most recent sate-level employment data for mapping.

* Added arguments to `get_data()` to pass the BLS API perams.

* Added documentation for data sets.

## Bug Fixes

* Fixed `zoo::index()` error.

