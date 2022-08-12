# Project for handling secrets with docker-compose

## Basic policy

- Use [direnv](https://github.com/direnv/direnv) to manage environment variables.
- Exclude `.envrc` from git management because it contains secrets.

## Usage

1. Create a `.envrc` file with your secrets. ( referring to `.envrc.example` )
2. Run `docker compose up test`
3. Check that `SECRET: xxx` is printed in the log of the container. (`xxx` is the value of the secret)

## Explanation of example

- In the `test` container, secret data is taken from the environment variable `SECRET`.
- In `docker-compose.yml`, the environment variable of the same name on the hos is referenced by defining it as `SECRET:` in the `environment` section.
- Finally, in the running container, `${SECRET}` is printed out the secret data received from outside the container.
