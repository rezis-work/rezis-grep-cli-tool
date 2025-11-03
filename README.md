# ReziGrep

_ReziGrep_ is a simple, blazing-fast, and user-friendly command-line tool for searching for lines containing a query string in a text file. Inspired by tools like `grep`, this project demonstrates core principles of Rust, including error handling, easy configurability, and safe string processing.

## Features

- Search for a query string in a file, case-sensitive or case-insensitive.
- Fast scanning using Rust's safe and efficient standard library.
- Outputs each matching line, with leading and trailing whitespace trimmed.
- Simple ergonomic CLI for easy use and scripting.

## Installation

1. **Clone the repository:**

   ```bash
   git clone <repository_url>
   cd rezigrep
   ```

2. **Build the project:**

   ```bash
   cargo build --release
   ```

3. The compiled binary will be located in `target/release/rezigrep`.

## Usage

Basic usage:

```bash
rezigrep <query> <filename>
```

Example:

Suppose you have a file `poem.txt`:

```
Beneath the silver willow’s shade,
A gentle breeze in June has played,
The river slips past moss and stone,
As evening’s hush begins to sigh.
```

To search for the word "the":

```bash
rezigrep the poem.txt
```

This will output:

```
The river slips past moss and stone,
As evening’s hush begins to sigh.
```

### Case Insensitivity

By default, ReziGrep is case-sensitive. To run a case-insensitive search, set the environment variable `CASE_INSENSITIVE` to any value:

```bash
CASE_INSENSITIVE=1 rezigrep the poem.txt
```

### Example Output

Output is formatted as:

```
Searching for <query>
In file <filename>
<matching line 1>
<matching line 2>
...
```

## Project Structure

- `src/main.rs` – CLI entry point and error handling.
- `src/lib.rs` – Core search logic and configuration parsing.
- `poem.txt` – Example text file used for demonstration or testing.
- `output.txt` – Example of search results.

## Testing

Run the included tests using:

```bash
cargo test
```

## Error Handling

- The app gracefully handles errors such as missing arguments or file I/O failure, printing a clear message to `stderr` and exiting with a non-zero code.

## Contributing

Issues and pull requests are welcome. Please fork the repository and submit your changes via a pull request.

## License

This project is open-source and available under the [MIT License](LICENSE).

## Credits

Developed as a demonstration of Rust programming basics, inspired by educational material from [The Rust Programming Language Book](https://doc.rust-lang.org/book/).

