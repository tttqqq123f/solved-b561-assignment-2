Download Link: https://assignmentchef.com/product/solved-b561-assignment-2
<br>
In this assignment, you will practice working with SQL as discussed in lectures SQL Part 1, SQL Part 2, and Views.<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> Your solutions, containing the PostgreSQL statements for solving the problems, should be submitted to IUCanvas in the required format. (See previous announcement.) It is strongly recommended that you include comments in this file to elaborate on your solutions.

In this assignment, we will use the following relation schemas about students and books.

Student(<em><u>Sid</u>,Sname</em>)

Major(<em>Sid,Major</em>)

Book(<em><u>BookNo</u>,Title,Price</em>)

Cites(<em>BookNo,CitedBookNo</em>) Buys(<em>Sid,BookNo</em>)

The relation Major stores students and their majors. A student can have multiple majors but we also allow that a student has no major. major. A tuple (<em>b,c</em>) in the relation Cites indicates that the book with book number <em>b </em>cites the book with book number <em>c</em>. Note that a book may cite multiple other books. Also, a book does not have to cited.

The primary keys of the relations are the underlined attributes and we assume the following foreign keys:

<table width="369">

 <tbody>

  <tr>

   <td width="144">Attribute in Relation</td>

   <td width="226">References Primary Key of Relation</td>

  </tr>

  <tr>

   <td width="144">Sid in Major</td>

   <td width="226">Sid in Student</td>

  </tr>

  <tr>

   <td width="144">BookNo in Cites</td>

   <td width="226">BookNo in Book</td>

  </tr>

  <tr>

   <td width="144">CitedBookNo in Cites</td>

   <td width="226">BookNo in Book</td>

  </tr>

  <tr>

   <td width="144">Sid in Buys</td>

   <td width="226">Sid in Student</td>

  </tr>

  <tr>

   <td width="144">BookNo in Buys</td>

   <td width="226">BookNo in Book</td>

  </tr>

 </tbody>

</table>

Furthermore, assume the following domains for the attributes:

<table width="173">

 <tbody>

  <tr>

   <td width="94">Attribute</td>

   <td width="79">Domain</td>

  </tr>

  <tr>

   <td width="94">Sid</td>

   <td width="79">INTEGER</td>

  </tr>

  <tr>

   <td width="94">Sname</td>

   <td width="79">TEXT</td>

  </tr>

  <tr>

   <td width="94">Major</td>

   <td width="79">TEXT</td>

  </tr>

  <tr>

   <td width="94">BookNo</td>

   <td width="79">INTEGER</td>

  </tr>

  <tr>

   <td width="94">Title</td>

   <td width="79">TEXT</td>

  </tr>

  <tr>

   <td width="94">Price</td>

   <td width="79">INTEGER</td>

  </tr>

  <tr>

   <td width="94">CitedBookNo</td>

   <td width="79">INTEGER</td>

  </tr>

 </tbody>

</table>

To do this assignment, you will have to create the above relations, including the primary and foreign keys. For data, use the data.sql file provided with this assignment.

Formulate the following queries in SQL. In these queries, unless otherwise specified, you can not use views (including temporary and parameterized views).

<ol>

 <li>Find the sid and name of each student who majors in CS and who boughta book that cost more than $10.

  <ul>

   <li>Formulate this query in SQL without using subqueries and set predicates.</li>

   <li>Formulate this query in SQL by only using the IN or NOT IN set predicates.</li>

   <li>Formulate this query in SQL by only using the SOME or ALL set predicates.</li>

   <li>Formulate this query in SQL by only using the EXISTS or NOT EXISTS set predicates.</li>

  </ul></li>

 <li>Find the bookno, title, and price of each book that was not bought by anyMath student.

  <ul>

   <li>Formulate this query in SQL without using subqueries and set predicates.</li>

   <li>Formulate this query in SQL by only using the IN or NOT IN set predicates.</li>

   <li>Formulate this query in SQL by only using the SOME or ALL set predicates.</li>

   <li>Formulate this query in SQL by only using the EXISTS or NOT EXISTS set predicates.</li>

  </ul></li>

 <li>Find the bookno, title, and price of each book that cites at least two booksthat cost less than $60.

  <ul>

   <li>Formulate this query in SQL without using subqueries and set predicates.</li>

   <li>Formulate this query in SQL by only using the IN or NOT IN set predicates.</li>

   <li>Formulate this query in SQL by only using the EXISTS or NOT EXISTS set predicates.</li>

  </ul></li>

 <li>Find the sid and name of each student along with the title and price ofthe most expensive book(s) bought by that student.

  <ul>

   <li>Formulate this query in SQL without using subqueries. (Observe that a most expensive book is a book wherefore there does not exists another book that is more expensive.)</li>

   <li>Formulate this query in SQL by using subqueries and set predicates.</li>

  </ul></li>

 <li>Find the sid and name of each student who bought at most one book thatcost more than $20.</li>

 <li>Without using the ALL or SOME set predicates, find the booknos and titles of books with the next to highest price.</li>

 <li>Find the bookno, title, and price of each book that cites a book which isnot among the most expensive books.</li>

 <li>Find the sid and name of each student who has a single major and suchthat none of the book(s) bought by that student cost less than $40.</li>

 <li>Find the bookno and title of each book that is bought by all students whomajor in both ‘CS’ and in ‘Math’.</li>

 <li>Find the sid and name of each student who, if he or she bought a bookthat cost at least $70 then he also bought a book that cost less than $30.</li>

 <li>Find each pair (<em>s</em><sub>1</sub><em>,s</em><sub>2</sub>) where <em>s</em><sub>1 </sub>and <em>s</em><sub>2 </sub>are the sids of students who have a common major but who did not buy the same books.</li>

 <li>Find the tuple (<em>s</em><sub>1</sub><em>,b</em><sub>1</sub><em>,s</em><sub>2</sub><em>,s<sub>b</sub></em>) such that if the student with sid <em>s</em><sub>1 </sub>bought book with bookno <em>b</em><sub>1 </sub>then the student with sid <em>s</em><sub>2 </sub>did not buy the book with bookno <em>b</em><sub>2</sub>.</li>

 <li>Define a view bookAtLeast30 that defines the books whose price is at least $30.</li>

</ol>

Consider the query “Find the sid and name of each student who bought fewer than two books that cost less than $30.”

Write a SQL that uses the view bookAtLeast30 to solve this query. After solving this problem drop the view bookAtLeast30

<ol start="14">

 <li>Reconsider the query in Problem 13. Redo this problem but this time byusing temporary views (i.e., use the WITH statement).</li>

 <li>Write a parameterized view citesBooks (b integer) that returns the relation of books that are cited by book <em>b</em>. (For each book returned by citesBooks include all information, i.e., bookno, title, and price.)

  <ul>

   <li>Use this parameterized view to write a SQL query that finds thebookno and title of each book that cites the book with bookno 2001 as well as cites a book that cost less than $50.</li>

   <li>Use this parameterized view to write a SQL query that finds thebookno and title of each book that cites at least two books.</li>

  </ul></li>

</ol>

<a href="#_ftnref1" name="_ftn1">[1]</a> <strong>Restrictions on SQL code</strong>: You can use views but you can not use the GROUP BY clause and aggregate functions. You can also not use the INNER JOIN (or other joins) operators.

Solutions with SQL statements that do not obey these requirements will not receive credit.