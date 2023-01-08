# Introduction

This repository contains examples for the [SOZip (Seek-Optimized Zip)](https://sozip.org)
profile to the ZIP file format.

# Contents

- [nz-building-outlines.gpkg.zip](https://download.osgeo.org/gdal/data/sozip/nz-building-outlines.gpkg.zip)
  (stored in external server for size reasons):
  494 MB SOZip file containing a 1.6 GB large [GeoPackage](https://geopackage.org)
  file with 3.2 million polygons and 13 attributes per feature.

- [nz-building-outlines-extract.shp.zip](nz-building-outlines-extract.shp.zip):
  subset of previous file (limited to first 400,000 features), in
  [Shapefile](https://en.wikipedia.org/wiki/Shapefile) format.
  352 MB uncompressed, 48 MB compressed.
  Generated with the following command:
  ```shell
  docker run --rm -it -v $PWD:$PWD rouault/sozip \
      ogr2ogr $PWD/nz-building-outlines-extract.shp.zip \
      $PWD/nz-building-outlines.gpkg.zip -limit 400000 -progress -lco ENCODING=UTF-8
  ```

- [foo.zip](foo.zip): 204 bytes large SOZip containing a 3 byte large file :-). Minimal
  example of [Annex G: commented dump of a dummy SOZip file](https://github.com/sozip/sozip-spec/blob/master/sozip_specification.md#annex-g-commented-dump-of-a-dummy-sozip-file)
