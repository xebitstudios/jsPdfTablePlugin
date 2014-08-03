jsPdfTablePlugin
================


 jsPdfTablePlugin expects an array of objects and an object specifying
 
 required table positioning values as an input,
 
 Each key in the object represents a column, 
 
 And the no of rows will be equal to input data length
 
 
 jsPdfTablePlugin return's the current y position of Document, 
 
 for further edition of Document



Example code :-

===================================================================

<pre>
var data = [],fontSize = 12, height = 0,doc;
doc = new jsPDF('p', 'pt', 'a4', true);
doc.setFont("courier", "normal");
doc.setFontSize(fontSize);
doc.text(50,100,"hi table");
function generate() {
for (var insert = 0; insert <= 20; insert++) {
	data.push({
		"name" : "jspdf plugin",
		"version" : insert,
		"author" : "Prashanth Nelli",
		"Designation" : "AngularJs Developer king is king so king also king"
	});
}

/**
 * height = doc.drawTable(objectArray,object); both parameters are mandatory
 * 
 * object properties xstart ,ystart,tablestart,marginleft.
 * 
 * xstart      -  horizontal starting position for table 
 * 
 * tablestart  -  vertical starting position for table in the starting page
 * 
 * ystart      -  vertical starting position for table in next pages if the records exceed present page
 * 
 * marginleft  -  this plugin uses full page width if u you wish to decrese the width of table increase marginleft value
 * 
 * doc.drawTable returns current co-ordinates values u can use those values 
 * 
 * for further editing .
 * 
 * 
 *     xstart
 * ----|--------------------
 * |    
 * |__ tablestart
 * |
 * |
 * |page 1
 * 
 * ----|--------------------
 * |   xstart 
 * |__ ystart
 * |
 * |
 * |page 2 3 4 5 ......
 * 
 * 
 * u style the table header fill color by changing values in drawRows Method 
 * 
 * table plugin uses the fontSize and fontStyle set by the user 
 * 
 */
				
height = doc.drawTable(data, {xstart:10,ystart:10,tablestart:450,marginleft:50});
doc.text(50, height + 20, 'hi world');
doc.save("some-file.pdf");
};
<pre>

  


 
 
 
 
