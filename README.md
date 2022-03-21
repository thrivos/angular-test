
# Thrivos Angular Test Project

This is a test project to evaluate Angular candidates.

## Prerequisites

You need to have Node.js installed and (ideally) Yarn. It can be done with NPM but Yarn is assumed.

## Installation

Clone this repository and run inside the root folder.

```bash
yarn
```

This will install all dependencies. Once it finishes you can run the projects.

## Development

The repo is composed of 2 projects, `users` (an Angular SPA app) and `users-api` (a NestJS API). In order to run both you will need to open 2 terminal sessions.

#### To run users-api

Run the following command to start the API server on `http://localhost:3333/api`.

```bash
yarn nx serve users-api
```

#### To run the users project

Run the following command to start the application on `http://localhost:4200`

```
yarn nx serve users
```

## Goals

The goal of the test is to create an autocomplete input that can search for users in the users-api and show them as a list as the app user types. For instance, when the user types the word `fr` the list should show results containing the string `fr` (case-insensitive).

To do this the autocomplete should call the endpoint `http://localhost:3333/api/users?name=fr` where the query param `name` contains the string the user typed in. The autocomplete should be designed as a standalone component.

Objectives of the test:
1. Create an autocomplete that calls the users endpoint to search for users.
2. The autocomplete should display the search results in a list below the input itself.
3. The autocomplete should be handle delays in the response from the API, as well as optimizing the amount of calls made if the user continues to type.
4. The list of resuts should support keyboard navigation up and down.