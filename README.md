# The Box Model

The box model is an intent to put back the programmation to where it belongs: the data.
Every piece of program is, by essence, a tool that will process some data. An input, a process and an output.
Even every complex program can be fragmented into little pieces that will process data.

Unfortunately, as today people and most programmers see programs as a piece of code, not as a tool to process data.
This is eventually one of the many causes of poor programmation, because people does not focus on the data, but on the code itself.

So lets change the focus, and rethink why we are programming.
We are building a set of many processes that will transform the data into something usefull, for humans, for another system, for machines, etc.

Understanding the data flow is a way to master the code, and build it for this purpose.

Actually, when you start to fragment the data flow into simple tasks or processes, you rapidly become aware that many tasks are virtually the same, just with some few changes into the data.

Lets take a first simple example.

A web page for an online catalog:

Let say a user makes a request to a web server: Give me the "first page" of the category "soap" ordered by "name".
The request would take 3 parameters, page = 1, category = soap, order = name
You may have some config underlaying parameters, for instance products per page = 10, database connector (username, password, etc)

The system, after validating the parameters, will load the 10 products in memory, inject them to a template with a loop (for each product) and finally send the result back to the user.

The data will be transformed through black boxes ordered as a process.

Lets draw this simple example with detail:

BOX 1: Load data from database.
Input: page, category, order, database connector data, num per page
Output: List of objects (hierarchical structure, collection of records)

BOX 2: Load a template from file
Parameter: the template resource (filename)
Output: The template

BOX 3: Inject data into template.
Input: any structure (BOX 1), the template (BOX 2)
Output: String of the armed html5 code
