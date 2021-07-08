List
- has a unique name

Todo
- Has a name
- belongs to a list
- can be completed, but should default to not being completed

CREATE TABLE lists (
  id serial PRIMARY KEY,
  name text NOT NULL UNIQUE
);

CREATE TABLE todos (
  id serial PRIMARY KEY,
  name text NOT NULL,
  completed boolean NOT NULL DEFAULT false,
  list_id integer NOT NULL REFERENCES lists(id)
);