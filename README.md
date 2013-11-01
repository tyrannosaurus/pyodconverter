## PyODConverter

PyODConverter (for Python OpenDocument Converter) is a Python package that
automates office document conversions from the command line using
LibreOffice or OpenOffice.org.

## Usage

PyODConverter requires LibreOffice/OpenOffice.org to be running as a service
and listening on port (by default) 2002; this can be achieved e.g. by starting
it from the command line as
```
	$ soffice --headless --nofirststartwizard "--accept=socket,host=localhost,port=2002;urp;StarOffice.Service"
```
Or, if you have `unoconv` installed
```
  $ unoconv -l -v
```

```python
from DocumentConverter import DocumentConverter

listener = ('localhost', 2002)
converter = DocumentConverter(listener)

# LibreOffice automatically converts relative paths
converter.convert('kittens.docx', 'kittens.pdf')
# So, if you run this code from /opt/ 
# It'll be interpreted as this:
# converter.convert('/opt/kittens.docx', '/opt/kittens.pdf')
```

## ChangeLog

v1.6 - 2013-06-05
* Fix support to print all sheets
* Fix parameters to initialize SOffice service

v1.5 - 2013-01-07
* Adding method to be able to get file base name
* Improvement files export from Presentation to Images. Now for each
  slide, an image will be created.

v1.4 - 2013-01-03

* Improvement the toProperties method to be able add array Uno properties
* Adding the Overwrite and IsSkipEmptyPages options.
* Update the README.

v1.3 - 2013-01-02

* Adding new docx format support.
* Adding paper size and orientation capable.
* Updated the options parser.
* Updated contributors.

v1.2 - 2012-03-10

* Changed default port to 2002
* Moved to GitHub

v1.1 - 2009-11-14

* Fixed HTML import issues by adding FAMILY\_WEB
* Support for specifying input formats and options
* Support for passing filter options to output formats
* Added CSV and TXT as input and output formats
* Support for overriding Page Style properties, especially useful for specifying
  how spreadsheets should fit into pages when exporting to PDF

v1.0.0 - 2008-05-05

* Let OOo determine the input document type, rather than using the file
  extension. This means all OOo-supported input types should now be accepted
  without any additional configuration.

## Contributors ##

* __mirkonasato__ <mirko.nasato@gmail.com>
* __marcelaraujo__ <admin@marcelaraujo.me>
