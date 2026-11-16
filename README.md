# Restful Booker – API Test Automation with Postman & Newman

API test suite for the public [Restful Booker](https://restful-booker.herokuapp.com) API, built with Postman and executed in CI with Newman and GitHub Actions.

## What is covered
- **Smoke tests:** health check, booking list and booking details (using a dynamic booking ID to avoid flaky tests).
- **Booking CRUD flow:** authentication, create, read, update, delete and deletion check, chaining the token and booking ID through environment variables.
- Assertions on status codes, response structure, data integrity and response times (18 assertions across 9 requests).

## Tech stack
Postman · JavaScript (pm API) · Newman · newman-reporter-htmlextra · GitHub Actions

## Run locally
```bash
npm install -g newman newman-reporter-htmlextra
newman run collections/restful-booker.postman_collection.json \
  -e environments/restful-booker.postman_environment.json \
  -r cli,htmlextra --reporter-htmlextra-export reports/report.html
```

## CI
Tests run automatically on every push and pull request. The HTML report is uploaded as a build artifact.
