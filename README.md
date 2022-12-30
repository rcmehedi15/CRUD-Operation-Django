<h1> What is CRUD? </h1>
Create, Read, Update, and Delete (CRUD) are the four basic functions that models should be able to do, at most.

<h1>Create, Read, Update, Delete</h1>
When we are building APIs, we want our models to provide four basic types of functionality. The model must be able to Create, Read, Update, and Delete resources. Computer scientists often refer to these functions by the acronym CRUD. A model should have the ability to perform at most these four functions in order to be complete. If an action cannot be described by one of these four operations, then it should potentially be a model of its own.

The CRUD paradigm is common in constructing web applications, because it provides a memorable framework for reminding developers of how to construct full, usable models. For example, let’s imagine a system to keep track of library books. In this hypothetical library database, we can imagine that there would be a books resource, which would store book objects. Let’s say that the book object looks like this:

“book”: {
  "id": <Integer>,
  “title”: <String>,
  “author”: <String>,
  “isbn”: <Integer>
}
To make this library system usable, we would want to make sure there were clear mechanisms for completing the CRUD operations:

<h3>Create</h3> — This would consist of a function which we would call when a new library book is being added to the catalog. The program calling the function would supply the values for “title”, “author”, and “isbn”. After this function is called, there should be a new entry in the books resource corresponding to this new book. Additionally, the new entry is assigned a unique id, which can be used to access this resource later.

<h3>Read</h3> — This would consist of a function which would be called to see all of the books currently in the catalog. This function call would not alter the books in the catalog - it would simply retrieve the resource and display the results. We would also have a function to retrieve a single book, for which we could supply the title, author, or ISBN. Again, this book would not be modified, only retrieved.

<h3>Update</h3> — There should be a function to call when information about a book must be changed. The program calling the function would supply the new values for “title”, “author”, and “isbn”. After the function call, the corresponding entry in the books resource would contain the new fields supplied.

<h3>Delete</h3> — There should be a function to call to remove a library book from the catalog. The program calling the function would supply one or more values (“title”, “author”, and/or “isbn”) to identify the book, and then this book would be removed from the books resource. After this function is called, the books resource should contain all of the books it had before, except for the one just deleted.

<h2>CRUD and REST</h2>
In a REST environment, CRUD often corresponds to the HTTP methods POST, GET, PUT, and DELETE, respectively. These are the fundamental elements of a persistent storage system.

Throughout the rest of the article, we will recommend standards and response codes that are typically followed by developers when creating RESTful applications. Conventions may differ so feel free to experiment with different return values and codes as you become comfortable with the CRUD paradigm.

Imagine we are working with a system that is keeping track of meals and their corresponding prices for a restaurant. Let’s look at how we would implement CRUD operations.

<h2>Create</h2>
To create resources in a REST environment, we most commonly use the HTTP POST method. POST creates a new resource of the specified resource type.
