<template>
    <div>
        <h1>{{ title }}</h1>
        <ul>
            <book-item v-for="(book, index) in books" v-bind:book="book" v-bind:key="book.title">{{ book.title }}: {{ book.author }}</book-item>
        </ul>
        <hr>
        <book-form v-on:addBook="appendBook"></book-form>
    </div>
</template>

<script>
import BookItem from './BookItem';
import BookForm from './BookForm';
export default {
    name: 'BookList',
    components: {
        BookItem,
        BookForm
    },
    data(){
        return {
            title: "All books",
            books: [
                {
                    title: 'Self-Reliance', 
                    author: 'Ralph Waldo Emerson'
                },
                {
                    title: 'American Gods', 
                    author: 'Neil Gaiman'
                },
                {
                    title: 'Amusing Ourselves to Death', 
                    author: 'Neil Postman'
                },
            ]
        }
    },
    methods: {
        appendBook(bookTitle, bookAuthor){
            this.books.push({
                title: bookTitle,
                author: bookAuthor
            })
        }
    }
}
</script>

<style>
    h1, h2 {
        font-weight: normal;
    }
    ul {
        list-style-type: none;
        padding: 0;
    }
   
</style>


