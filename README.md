CSV Converter
=============

Create ruby script which takes csv file and prints result to standard output.
Example csv file should consist of 3 columns where first column contains valid country alpha3 code.
Script should check if each country code is valid iso alpha3 code and print apropriate error if not.
It should also validate row length.

By default output should print ascii table consisting of 4 rows where 1 column is English country name for country code from csv, and rest are other columns from given row.

User is allowed to pass `--html` parameter - table will be printed in html format instead of ascii.

Example
-------

for test.csv file:

```
POL,10,'something'
```

`. csv-convert test.csv`

it should result in:

```
  +---------+-----+----+-----------+
  | Poland  | POL | 10 | something |
  +---------+-----+----+-----------+
```

`. csv-convert test.csv --html`

it should result in:

```
  <table><tr><td>Poland</td><td>POL</td><td>10</td><td>something</td></tr></table>
```

If no input given it should print usage info.

Libraries
------------

* use gem `countries` for country alpha3 code validation and country names 

* use gem `text-table` to generate ascii table output

* use TDD using minitest-spec and guard
