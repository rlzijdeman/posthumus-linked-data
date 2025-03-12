# Assignment 6: Make an RDF file

The past few weeks we have been working with tabulated data in CSV’s. However, data can come in many formats. Some are variations on the tables we have worked with before, such as dBase (.dbf), Excel (.xls or .xlsx), SPSS (.sav), or Stata (.dta) files, etc. 

These file types are all proprietary variations on CSV-files used by programs that have been or are being widely used and offer some advantages with the accompanying software. Nowadays, it is pretty easy to open and save data in these formats, thanks to R packages like foreign and read.xlsx. However, communicating information from these file types remains tricky without the proprietary software. 

Easy access and being able to interact with data are part of the FAIR principles. We have had you working with CSV as it is already a great improvement over proprietary formats such as MS Excel. Yet there are other World Web Web Council (W3C) recommended formats, such JSON and XML. The ‘latest (2 decades old) and greatest (you probably haven’t heard of it)’ is the Resource Description Framework or RDF. The key benefit of RDF over all the others is that not just allows one to share data across the Web, but also express the data in a common (shared) vocabulary. 

The next series of lessons will go into the use of RDF, aka ‘Linked Data’ or ‘Semantic Web’. For this assignment, next week’s teacher – Richard Zijdeman – has asked whether you could please comply with the Netwerk Digitaal Erfgoed and the Ministry of Education, that have made RDF the de facto standard for exchange of digital heritage data. Practically, the question is whether you can please transform the attached data file into RDF.

# Specifications
A quick search for more information learns that RDF works a little bit like the long format that we saw in the mid-term assignment. If RDF would be expressed as a table, it would have 3 columns: entity, attribute, value (actually, the EAV model has existed for the longest time and the Intermediate Data Structure (IDS) is based on it!). So for the table below:

| ID     	 | Resident	  | Name                            |	Born |
|----------|------------|---------------------------------|------|
| Person_1 |Household_1	|Rachel Baëza weduwe D J de Vries	| 1874 |


We could read this table in a grammar of short statements using the EAV model. To do so, you read the identifier for the person, the column header and the column value. I.e.:

-	`person 1` `is resident of` `household 1`
-	`person 1` `has name` `Rachel Baëza weduwe D J de Vries`
-	`person 1` `was born in` `1874`

This thus represent the data in the EAV model and a big step towards RDF:

| Entity	 | Attribute | 	Value                           |
|----------|-----------|----------------------------------|
| Person_1 |	Resident | Household_1                      |
| Person_1 |	Name	   | Rachel Baëza weduwe D J de Vries |
| Person_1 |	Born	   | 1874                             |

Seems easy enough right? Now your task is to make an RDF of the provided data file. You can use a fancy script to convert your table into these 'triples', but perhaps it is much quicker to type it:
`<Person_1>` `<isResidentOf>` `<Household_1>` etc...

Don't worry about the brackets or the formuliation of the attribute. This is just about getting feel for these three-part statements we call triples!

Done? Show and compare your results with someone else!
