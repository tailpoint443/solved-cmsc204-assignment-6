Download Link: https://assignmentchef.com/product/solved-cmsc204-assignment-6
<br>






<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2019/12/153.png?w=980&amp;ssl=1" class="alignleft lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" class="alignleft" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2019/12/153.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>Behind every Google Map, there is a much more complex structure that’s the key to your queries but hidden from your view. It contains the logic of places: their no-left-turns and freeway on-ramps, speed limits and traffic conditions. This is the data that you’re drawing from when you ask Google to navigate you from point A to point B.




<table width="100%">

 <tbody>

  <tr>

   <td><strong>Assignment Description</strong></td>

  </tr>

 </tbody>

</table>

In this project you will be creating an application to maintain a network of towns and the roads connecting them. The application will use Dijkstra’s Shortest Path algorithm to find the shortest distance between any two towns.

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Concepts tested by this assignment</strong></td>

  </tr>

 </tbody>

</table>
















Implement Graph Interface

Use Graph to maintain a network of Vertices

Implement Shortest Path Algorithm

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Classes</strong></td>

  </tr>

 </tbody>

</table>










<strong> </strong>




<strong>Data Element – Town (Vertex)</strong>

Create a Town class that holds the name of the town and a list of adjacent towns, and other fields as desired, and the traditional methods (constructors, getters/setters, toString, etc.).  It will implement the Comparable interface.  This is the class header:

public class Town implements Comparable&lt;Town&gt;

Two towns will be considered the same if their name is the same.

<strong>Data Element </strong><strong>– Road (Edge)</strong>

Create a class Road that can represent the edges of a Graph of Towns.  The class must implement Comparable.  The class stores references to the two vertices(Town endpoints), the distance between vertices, and a name, and the traditional methods (constructors, getters/setters, toString, etc.), and a compareTo, which compares two Road objects. Since this is a undirected graph, an edge from A to B is equal to an edge from B to A. This is the class header:

public class Road implements Comparable&lt;Road&gt;




<strong>Data Structure </strong><strong>– TownGraph, implements GraphInterface</strong>

Create a TownGraph class that implements the GraphInterface given you.  For Graph&lt;V,E&gt;,  V is the vertex type (a Town), E is the edge type (a Road).  You will need to decide how to store the graph, use an adjacent matrix or an adjacency list.  This is the class header:

public class TownGraph implements GraphInterface&lt;Town, Road&gt;

Within the Graph interface is a method shortestPath, which finds the shortest path from a given source Town to a destination Town. Since there is a unique shortest path from every vertex to the source, there is a back-pointer to the previous vertex.  The method shortestPath calls dijkstraShortestPath which finds the shortest path from the source to every other vertex in the graph.  You will be coding the Dijkstra’s Shortest Path algorithm.  You will then be able to find the connections between two towns through the roads that connect them.

You may use the adjacency matrix approach found in the text book, or you may use a set of Towns and a set of Roads. The ShortestPath algorithm typically uses a weighted graph which means that the edges have a weight, and this is used to determine the shortest path.  For this implementation, each weight will be the distance of the road in miles.

<strong>Data Manager </strong><strong>– implements TownGraphManagerInterface</strong>

Your TownGraphManager will hold an object of your Graph. Implement the TownGraphManagerInterface. There are methods to populate the graph (reading from a text file), add a town (vertices), add a road (edge), list all towns and all roads, and list towns adjacent to a given town.

Your solution will find the shortest path from a start town to a destination town.  It will account for the possibility of a disjoint graph (i.e., not all vertices can be reached from all other vertices.)

You may add any methods as needed for your design.

<strong> </strong>

<strong>Exception Classes</strong>

IOException – created and thrown when user selects an input file that cannot be read (check out the methods of File).




<strong>GUI Driver </strong><strong>(provided for you)</strong>

The GUI will have three sections: a Town section, a Road section, and a Find Connection section.

<strong> </strong>

<strong>Testing</strong>

<ol>

 <li>Create a JUnit Test – TownGraphManagerTest_STUDENT. Test all the methods of the TownGraphManager with a different set of data than the TownGraphManagerTest provided for you.</li>

 <li>Create a JUnit Test – TownGraphTest_STUDENT. Test all the methods of the TownGraph with a different set of data than the TownGraphTest provided for you.</li>

 <li>Create a Junit Test – RoadTest_STUDENT. Test all the methods of your Road class.</li>

 <li>Create a Junit test – TownTest_STUDENT. Test all the methods of your Town class.</li>

</ol>

<strong> </strong>

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Assignment Details</strong></td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>




<strong>Populating the Data Structure</strong>

You will be reading from a data file.  You are provided with two sample files: MD Towns.txt and US Towns.txt along with two PowerPoint slides showing these graphs.




The Towns.txt files hold the information for the individual Towns and Roads, and is in the following format:

road-name,miles;town-name; town-name

For example:

I-94,282;Chicago;Detroit

Notice that the road-name and miles are separated by a comma, while the road information and the two towns are separated by semi-colons.




After reading these files, you will have an initial set of vertices and edges in your Graph.

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Examples</strong></td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>




<table width="100%">

 <tbody>

  <tr>

   <td></td>

  </tr>

 </tbody>

</table>

<strong>After reading in the MD Town file                 After reading in the US Town file            </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong>The GUI (Provided for you)</strong>

The GUI will have four sections: an Add Town section, an Add Road section, a Find Connection section, and an administration section.  There will be four ComboBoxes each containing the same list of Towns.  On startup the graph will be empty.

<strong>Add a Town Button</strong>

<strong>      </strong>The user may add a new Town by typing its name in the textfield.  If the textfield is blank when the Add Town button is selected, the GUI should show an error message.  When a new Town is added, the TownGraphManager will add it to the graph, and the Town’s name will be added to the four ComboBoxes.

<strong>Add a Road Button</strong>

<strong>      </strong>To add a road, a town must be selected from each of the two ComboBoxes in the Add Road section, an integer distance entered, and a road name entered.  When the Add Road button is selected, the edge is created and entered in the graph.







<strong>Find Connection Button</strong>

Display all the available towns in the ComboBoxes  (in alpha order by name).  When the user selects the towns, display the name in the ComboBoxes.  When the user selects the “Find Connection” button, the TownGraphManager’s shortestPath method is called.  The resulting list of roads connecting towns, and the distance along each road, is displayed in the text area.

If the “source” town and “destination” town are the same, or if there is no route between the two, state that in the text area.<strong></strong>

<strong>Read File Button</strong>

The Towns.txt files hold information for individual Towns and Roads, and is in the following format:

road-name<strong>,</strong>miles<strong>;</strong>town-name<strong>;</strong>town-name

For example:

I-94,282;Chicago;Detroit

Notice that the road-name and miles are separated by a comma, while the road information and the two towns are separated by semi-colons.




<strong>Exit Button</strong>

The program will terminate.

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Deliverables</strong></td>

  </tr>

 </tbody>

</table>













<strong><u>Deliverables / Submissions</u></strong><strong>: </strong>

Design: UML class diagram with algorithm (pseudo-code) for methods

Implementation: Submit a compressed file containing the follow (see below):  The Java application (it must compile and run correctly); Javadoc files in a directory; a write-up as specified below.  Be sure to review the provided project rubric to understand project expectations.  The write-up will include:

<ul>

 <li>UML diagram</li>

 <li>In three or more paragraphs, highlights of your learning experience</li>

</ul>




<strong><u>Deliverable format</u>:</strong> The above deliverables will be packaged as follows. Two compressed files in the following formats:

<ul>

 <li>zip, a compressed file in the zip format, with the following:

  <ul>

   <li>Write up (Word document) – reflection paragraphs</li>

   <li>UML Diagram – latest version (Word or jpg document)</li>

   <li>doc (directory) – Javadoc</li>

  </ul></li>

</ul>

<ul>

 <li style="list-style-type: none;">

  <ul>

   <li style="list-style-type: none;">

    <ul>

     <li style="list-style-type: none;">

      <ul>

       <li>File1.html (example)</li>

       <li>File2.html (example)</li>

      </ul></li>

    </ul></li>

  </ul></li>

</ul>

<ul>

 <li>src (directory)</li>

</ul>

<ul>

 <li style="list-style-type: none;">

  <ul>

   <li style="list-style-type: none;">

    <ul>

     <li style="list-style-type: none;">

      <ul>

       <li>File1.java (example)</li>

       <li>File2.java (example)</li>

      </ul></li>

    </ul></li>

  </ul></li>

</ul>




<ul>

 <li>zip, a compressed file containing one or more Java files:

  <ul>

   <li>java (example)</li>

   <li>java (example)</li>

  </ul></li>

</ul>

This folder should contain Java source files only

<strong> </strong>


