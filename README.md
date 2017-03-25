# Hello

This project is just a simple `hello world` app running on phoenix v1.3 framework, and hosted with [nanobox](https://nanobox.io/). It was created following [this tutorial ](https://content.nanobox.io/elixir-app-deployment-with-nanobox/), with some modifications:

### The PORT environment variable

In Phoenix 1.3, the `PORT` environment variable [must be set when running when in production](https://elixirforum.com/t/failing-to-start-phoenix-1-3-0-rc-with-mix-env-prod/4245). Before staging the nanobox app in a `dry-run` context, add this variable with
```
nanobox evar add dry-run PORT=8080
```
nanobox [forwards all http/s traffic](https://docs.nanobox.io/domains-networking/protocols-incoming-requests/#http-https) on 80 and 443 to the application running on 8080. Before deploying to production, add the environment variable to your `remote` context.
```
nanobox evar add remote PORT=8080
```

Good luck! :beers:

---

To start your Phoenix server:

  * Install dependencies with `mix deps.get`
  * Create and migrate your database with `mix ecto.create && mix ecto.migrate`
  * Install Node.js dependencies with `cd assets && npm install`
  * Start Phoenix endpoint with `mix phx.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

Ready to run in production? Please [check our deployment guides](http://www.phoenixframework.org/docs/deployment).

## Learn more

  * Official website: http://www.phoenixframework.org/
  * Guides: http://phoenixframework.org/docs/overview
  * Docs: https://hexdocs.pm/phoenix
  * Mailing list: http://groups.google.com/group/phoenix-talk
  * Source: https://github.com/phoenixframework/phoenix
