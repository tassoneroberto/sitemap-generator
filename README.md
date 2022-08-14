# Sitemap Generator

A sitemap.xml generator written in Python.

This is a port in Python 3 of the code developed by Vladimir Toncar. More information at [https://toncar.cz/opensource/sitemap_gen.html](https://toncar.cz/opensource/sitemap_gen.html).

## Description

This script crawls a web site from a given starting URL and generates a Sitemap file in the format that is accepted by Google. The crawler does not follow links to other web sites. It also respects the `nofollow` tags and will not crawl into directories disallowed in the robots.txt file.

## Usage

```bash
python sitemap_gen.py -b doc -b bmp -o test_sitemap.xml http://www.your-site-name.com/index.html
```

## Options

```bash
python sitemap_gen.py <options> <starting URL>
```

|Short option|Long option|Description|
|-|-|-|
|-h|--help|Print this text and exit|
|-b `<ext>`|--block `<ext>`|Exclude URLs with the given extension; `<ext>` must be without the leading dot. The comparison is case insensitive, so for example DOC and doc are treated the same. You can use this option several times to block several extensions. Some multimedia/document extensions (e.g. JPG, MP3, etc.) are blocked by default.|
|-c `<value>`|--changefreq `<value>`|Set the change frequency. The given value is used in all sitemap entries (maybe a future version of this script will change that). The allowed values are: always, hourly, daily, weekly, monthly, yearly, never.|
|-p `<prio>`|--priority `<prio>`|Set the priority. The value must be fromthe interval between 0.0 and 1.0. The valuewill be used in all sitemap entries.|
|-m `<value>`|--max-urls `<value>`|Set the maximum number of URLs to be crawled.The default value is 1000 and the largest value that you can set is 50000 (the script generates only a single sitemap file).|
|-o `<file>`|--output-file `<file>`|Set the name of the geneated sitemap file. The default file name is sitemap.xml.|

## Excluded extensions

The files with the following extensions are exluded by default:

- JPG
- JPEG
- GIF
- BMP
- PNG
- MP4
- MKV
- AVI
- MP3
- AAC
- PDF
- DOC
- DOCX
- TXT
- ZIP
- RAR
- TAR
- GZ

## License

This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.
