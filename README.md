# README.md

## Project Overview

This project contains the complete beginner-friendly academic assignment specifications for the **Library - Book Issue & Return** system (Feature Set II). It outlines all necessary functional requirements, algorithms, flowchart logic, and Entity-Relationship (ER) design details required for academic implementation.

---

## Features & Scope

The system focuses strictly on the following core modules:

1. **Student Details**: Manages student identification and personal information.


2. **Book Details**: Tracks catalog information and real-time availability.


3. **Book Issue**: Records transactions linking students to borrowed books with issue and due dates.


4. **Return Status**: Tracks return dates and determines transaction statuses (*Issued*, *Returned*, or *Overdue*).


5. **Fine Calculation**: Automatically computes fines based on overdue days and institution-defined rates.



---

## Requirements Summary

### Functional Requirements

* **FR-01 (Student Details)**: Stores unique Student ID, Student Name, Course/Class, and Contact information.


* **FR-02 (Book Details)**: Stores unique Book ID, Title, Author, Category/Publisher, and Availability Status.


* **FR-03 (Book Issue)**: Connects students and books, recording the Issue Date and Due Date.


* **FR-04 (Return Status)**: Tracks the Return Date and categorizes the status into *Issued*, *Returned*, or *Overdue*.


* **FR-05 (Fine Calculation)**: Calculates fines using the formula $\text{Fine} = \text{Overdue Days} \times \text{Fine Rate}$ if returned past the due date; otherwise, $\text{Fine} = 0$.


* **FR-06 (Availability Update)**: Automatically changes book availability to unavailable upon issue and available upon return.


* **FR-07 (Validation)**: Verifies student and book existence, prevents issuing unavailable books, and validates all dates.



### Non-Functional Requirements

* Simple and easy to use.


* Accurate data handling and quick response times.


* Organized, maintainable, and structured for academic use.



---

## System Workflow & Algorithm

The execution follows a strict sequence from validation to transaction completion:

1. **Validation Phase**: Inputs Student ID and Book ID, confirming record existence and book availability.


2. **Issue Phase**: Records the issue transaction, sets the issue date, and maps a library-defined loan period to establish the due date.


3. **Return & Fine Phase**: Inputs the Return Date, compares it against the Due Date, computes any applicable fines, updates the status (*Returned* or *Overdue*), and resets the book's availability status to *Available*.



---

## ER Diagram Architecture (Chen Notation)

* **Entities & Attributes**:
* **STUDENT**: `Student_ID` (Key), `Student_Name`, `Course_Class`, `Contact`.


* **BOOK**: `Book_ID` (Key), `Title`, `Author`, `Category`, `Publisher`, `Availability_Status`.


* **BOOK_ISSUE**: `Issue_ID` (Key), `Issue_Date`, `Due_Date`, `Return_Date`, `Return_Status`, `Fine_Amount`.




* **Relationships**:
* `STUDENT` to `BOOK_ISSUE` (**1 : N**).


* `BOOK` to `BOOK_ISSUE` (**1 : N**).
