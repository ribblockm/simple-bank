# simple-bank

A simple but consistent backend for a back, written in Clojure

In this application, we will create a back in which we:

- create and manage accounts
- record all balance changes
- do money transfer transactions

1. Design a DB model
    We generated the `bank-schema.sql` file to create a db in PostgreSQL.

2. Migrations
    Migrations are a crucial part of a db management. We plan to use Migratus, a general migration framework written in Clojure. But for now we'll use a cli and golang library, `golang-migrate`.

    We run `migrate create -ext sql -dir db/migration -seq init_schema` to create the files for `up` and `down` migrations. In the `up` script we'll use the model defined in `bank-schema.sql`, and for the `down` script we will drop the tables (in sequential order, they are dependent).

    Our first up migration becomes `migrate -path db/migration -database "postgresql://localhost:5432/simple_bank?sslmode=disable" -verbose up`.

3. Makefile
    We add the above commands to a Makefile.


## Installation

Download from http://example.com/FIXME.

## Usage

FIXME: explanation

    $ java -jar simple-bank-0.1.0-standalone.jar [args]

## Options

FIXME: listing of options this app accepts.

## Examples

...

### Bugs

...

### Any Other Sections
### That You Think
### Might be Useful

## License

Copyright © 2023 FIXME

This program and the accompanying materials are made available under the
terms of the Eclipse Public License 2.0 which is available at
http://www.eclipse.org/legal/epl-2.0.

This Source Code may also be made available under the following Secondary
Licenses when the conditions for such availability set forth in the Eclipse
Public License, v. 2.0 are satisfied: GNU General Public License as published by
the Free Software Foundation, either version 2 of the License, or (at your
option) any later version, with the GNU Classpath Exception which is available
at https://www.gnu.org/software/classpath/license.html.
