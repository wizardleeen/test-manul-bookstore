# Manul Bookstore

A simple online bookstore built with the Manul programming language, featuring automatic persistence and REST API generation.

## Features

- **Author Management**: Create and manage book authors with biographical information
- **Book Catalog**: Comprehensive book management with ISBN, pricing, stock tracking, and genre classification
- **Search & Discovery**: Find books by title, author, genre, or ISBN
- **Stock Management**: Track and update book inventory
- **Automatic REST API**: All service methods are automatically exposed as REST endpoints

## Entities

### Author
- Name, biography, birth year
- Indexed by name for fast lookups
- Automatic relationship with books

### Book
- Title, author, ISBN, price, stock, genre, description, publication year
- Multiple indexes for efficient searching (title, ISBN, author, genre)
- Stock management with validation
- Support for multiple currencies via Money value class

## Services

### BookstoreService
- Get all books or filter by availability
- Search books by title, author, genre, or ISBN
- Add new books with validation
- Update book stock levels

### AuthorService
- Manage authors and their biographical information
- Find authors by name
- Get all books by a specific author

## Sample Data

The application comes pre-loaded with sample data including:
- Classic authors (Tolkien, Rowling, George R.R. Martin, Agatha Christie, George Orwell)
- Popular books across various genres (Fantasy, Mystery, Fiction)
- Realistic pricing and stock levels

## API Endpoints

Once deployed, the following REST endpoints will be automatically available:

- `GET /BookstoreService/getAllBooks` - Get all books
- `GET /BookstoreService/getAvailableBooks` - Get books in stock
- `GET /BookstoreService/findBookByIsbn?isbn={isbn}` - Find book by ISBN
- `GET /BookstoreService/findBooksByTitle?title={title}` - Search by title
- `GET /BookstoreService/findBooksByAuthor?authorName={name}` - Search by author
- `GET /BookstoreService/findBooksByGenre?genre={genre}` - Filter by genre
- `GET /AuthorService/getAllAuthors` - Get all authors
- `GET /AuthorService/findAuthorByName?name={name}` - Find author by name
- `GET /AuthorService/getAuthorBooks?authorName={name}` - Get books by author

## Deployment

This project is designed to be deployed on the Miaobu platform as a Manul application. The Manul runtime provides:
- Automatic object persistence
- REST API generation
- Search indexing
- Transaction management
