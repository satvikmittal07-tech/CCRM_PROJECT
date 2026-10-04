# CCRM: Campus Course & Records Manager

CCRM is a menu-driven Java console application that keeps an institution's academic records in one place. An administrator can register students, publish courses, enroll students into them, record marks, and produce transcripts, all from the terminal and without a database server.

> **Author:** Satvik Mittal (24BCY10107)
> **Language:** Java (8 or newer)  |  **Interface:** Command line

---

## What it does

| Area | Capabilities |
|------|--------------|
| **Students** | Register a student, edit details, mark as inactive, look up by ID or name |
| **Courses** | Create and edit courses, retire old ones, search by code, title, department or credits |
| **Enrollment** | Enroll or withdraw a student, with a check that blocks enrollment beyond the allowed credit load |
| **Grades** | Store marks per course, convert them to grade points, compute GPA, print a transcript |
| **Data files** | Load records from CSV, save them back to CSV, snapshot all data into a backup and restore it later |
| **Reports** | Summaries and statistics such as enrollment counts, grade distribution and top performers |

---

## How the code is organised

The project is written to practise core Java concepts rather than to hide them. You will find:

- **Object-oriented design:** encapsulated entities, an inheritance hierarchy for people (student / teacher), abstract base classes and interfaces, and polymorphic behaviour in the services.
- **Error handling:** custom exception types for cases such as a duplicate ID or exceeding the credit limit, handled with `try`/`catch`/`finally`.
- **Modern Java APIs:** the Stream API for filtering, grouping and sorting; `java.time` for dates; NIO.2 (`Path`, `Files`) for reading and writing files.
- **Language features:** enums that carry fields and constructors (for example grade-to-points mapping), lambdas and functional interfaces, nested classes, and a small amount of recursion.
- **Design patterns:** Singleton for shared application services and Builder for constructing entities with many optional fields.

---

## Requirements

- JDK 8 or later (JDK 17 LTS recommended)
- Any Java IDE (Eclipse, IntelliJ IDEA, VS Code) or just a terminal

Check your setup with:

```
java -version
javac -version
```

If the commands are not found, install a JDK, set `JAVA_HOME` to its folder, and add `JAVA_HOME/bin` to your `PATH`.

---

## Getting started

### Option 1: Using an IDE (e.g. Eclipse)

1. Clone this repository.
2. Create a new Java project and point it at the cloned source folder.
3. Make sure the project uses your installed JDK.
4. Run the `Main` class.

### Option 2: Using the terminal

```
git clone <your-repository-url>
cd <project-folder>
javac -d out $(find . -name "*.java")
java -cp out Main
```

(On Windows, compile with `dir /s /b *.java > sources.txt` followed by `javac -d out @sources.txt`.)

### Turning on assertions

Assertions are off by default. To enable them while running:

```
java -ea -cp out Main
```

---

## Using the application

When the program starts it shows a numbered menu. A typical session goes like this:

1. Add a few students and courses.
2. Enroll a student into one or more courses.
3. Record grades once a course is complete.
4. View the transcript or a report.
5. Export the data to CSV and create a backup before closing.

Every menu option prompts you for the input it needs, so no command syntax has to be memorised.

---

## A short note on Java

For context, the project relies on features added over several Java releases: generics and annotations (Java 5), lambdas, streams and the new date/time API (Java 8), and modules (Java 9). Java 17 is the current long-term-support release most people target today.

Java also comes in three editions: **Java SE** for desktop and server programs (the one used here), **Java EE** for large enterprise systems, and **Java ME** for small embedded devices.

---

## Future improvements

- Store data in a real database instead of flat files
- Add login roles for administrators, teachers and students
- Provide a graphical or web front end

---

*Built as a learning project to practise object-oriented programming and the Java standard library.*
