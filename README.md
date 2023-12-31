# Turso at the polls

An poll-making website.

Technologies used.

- [SvelteKit]
- [Turso]
- [Drizzle]
- [Vercel]
- [TailwindCSS]

## Database Setup

[Install the Turso CLI].

Create a new turso database.

```sh
turso db create turso-at-the-polls
```

> **Note**
>
> We use `turso-at-the-polls` as the database name in this command, but you can give
> it any name.

To access the data stored inside your database, you need the Turso database url
and an authentication token.

To obtain the database url, run the following command:

```sh
turso db show turso-at-the-polls --url
```

And, to create an authentication token for your database, run:

```sh
turso db tokens create turso-at-the-polls
```

Add a `.env` file with the following variables, populating them with the
values obtained above.

```txt
VITE_TURSO_DB_AUTH_TOKEN=<AUTH-TOKEN>
VITE_TURSO_DB_URL=<DB-URL>
```

## Schema generation and migration

To generate the database schema with Drizzle, run:

```sh
npm run drizzle:generate
```

Migrate the generated database schema by running:

```sh
npm run drizzle:migrate
```

## Developing

Once you've created a database, generated, and migrate the schema by following the instructions above, install the project's dependencies by running:

```typescript
npm install
```

To start a development server, run:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

> **_Note_**
>
> Do not stage the `.env` file used in local development.

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an
> [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.

[TailwindCSS]: https://github.com/tailwindlabs/tailwindcss
[Turso]: https://turso.tech
[Drizzle]: https://github.com/drizzle-team/drizzle-orm
[SvelteKit]: https://github.com/sveltejs/kit
[Vercel]: https://vercel.com/
[Install the Turso CLI]: https://docs.turso.tech/reference/turso-cli#installation
