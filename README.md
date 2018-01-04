# pyodbviewer

"pyodbsql" and "pyodbsql2" is simple python script.
It uses PandasDataFrameGUI to support the tabular view of the ODB query result.
Basically, the output of ODB(-1,-2) sql-query is displayed on the terminal. 
If ther are many columns, it's not easy to distingusish each column.

The result of "pyodbsql" and "pyodbsql2" is a minimalistic GUI for ODB sql-query based on PandasDataFrameGUI.
It makes user understand the data efficiently. Of course, user can use the metview software. But it's not light program.


PandasDataFrameGUI : https://github.com/bluenote10/PandasDataFrameGUI

### Features
1. Tabular view of ODB sql query
1. Include the PandasDataFrameGUI original features: refer the upper site.

### Requirements
1. Dfgui module
1. wxPython
1. Pandas/Numpy
1. Matplotlib

### Basic Usage

#### pyodbsql
<code> pyodbsql -q [sql_query] -t [table_name] -n [output line number] -i [odb(-1)file]
  * -t, -n : optional
</code>
<pre>
1. pyodbsql -q 'select date, time, ident, lat, lon, ops_obstype,  varno, initial_obsvalue, obsvalue, corvalue, bgvalue from hdr, body, conv where ops_obstype=10101' -i /[path]/odb/surface
2. pyodbsql -t body -i /[path]/ECMA.Aircraft
3. pyodbsql -t body -n 50 -i /[path]//ECMA.Aircraft
</pre>
 
#### pyodbsql2
<code> pyodbsql2 -q [sql_query] -n [output line number] -i [odb(-2)file]
  * -n : optional
<pre>
1)	without -n option
pyodbsql2 -q 'lat@hdr,lon@hdr,varno@body,vertco_reference[1]@body,initial_obsvalue@body, obsvalue@body, bgvalue@body, fg_depar@body' -i ECMA.Aircraft.odb
2)	with -n option
pyodbsql2 -q 'lat@hdr,lon@hdr,varno@body,vertco_reference[1]@body,initial_obsvalue@body, obsvalue@body, bgvalue@body, fg_depar@body' -n 10 -i ECMA.Aircraft.odb
  </pre>
