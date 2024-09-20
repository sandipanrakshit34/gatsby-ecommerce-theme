

This beautiful theme from the Matter Design Team gives you the styling and scaffolding for your next e-commerce site. You can customize to your heart's content and add the tooling for cart, transactions, product, and more. This theme uses:

Gatsby
CSS Modules
Prettier
React Helmet

Take a look at the screenshot below or preview the live site here: https://gatsby-ecommerce-theme.netlify.app/!
![full page screenshot](https://res.cloudinary.com/dzkoxrsdj/image/upload/v1653371030/CleanShot_2022-05-24_at_01.11.52_2x_bspa8c.jpg)

> 🧐 Please be aware that some aspects of this theme are not fully functional and will need to be integrated with the recommended tooling mentioned at the end of the [README](#next-steps-with-this-theme). 

## Table of Contents:

- [Quick Steps + Deploy Options](#quick-setup--deploy-option)
  - [Cloning + Installing Packages](#cloning--installing-packages)
- [Deploying](#deploying)
- [Project Structure](#project-structure)
  - [Making Changes to the Hero Component](#making-changes-to-the-hero-component)
  - [Making Changes to the Header or Footer](#making-content-changes-to-the-header-or-footer)
- [Testing](#testing)
  - [Included Default Testing](#included-default-testing)
  - [Removing Renovate](#removing-renovate)
  - [Removing Cypress](#removing-cypress)
- [Next Steps with This Theme](#next-steps-with-this-theme)

## Quick Setup + Deploy Option

Click the button below and it will help you create a new repo, create a new Netlify project, and deploy this Theme!


## Regular Setup

 ### Cloning + Installing Packages
 
  - Clone this repo with one of these options:

    - Click the 'Use this template' button at the top of the page
    - Via the command line:
       ```shell
       ```

  From there, you can install the project's dependencies by running:

  ```shell
  npm install or yarn install
  ```

  Finally, you can run your project locally with:

  ```shell
  cd gatsby-sydney-ecommerce-theme/
  npm start or yarn start
  ```
  
  or, run it using the Netlify CLI with:
  
  ```shell
  netlify run dev
  ```
  
  Open your browser and visit , your project should now be running!
  
  ## Deploying
 
  After installing and customizing your new e-commerce theme it's now time to deploy! 
  

      ```bash
      netlify init # initialize a new Netlify project & deploy
      ```

   It will use the information from the included Netlify configuration file, to set up the build command as `gatsby build` to create a static project and locate the build project in the `public` directory.

   The `init` process will also set up continuous deployment for your project so that a new build will be triggered & deployed when you push code to the repo (you can change this from your project dashboard: Site Settings/Build & deploy/Continuous Deployment).

   You can also use `netlify deploy (--prod)` to manually deploy and `netlify open` to open your project dashboard.

  > 💡 we only have so many keystrokes to give, use `ntl` shorthand for `netlify` or make [an alias of your own] to save hours...of accumulated milliseconds

  - You can deploy within the Netlify site by connecting to git, this [video] will walk you through that process. 
  - Or, you can use the Deploy to Netlify button which will walk you through the process of spinning up a repo, creating a new project in Netlify, AND deploying it :)

## Project Structure

Here is a bit of an overview of the directory structure of the project:

| Directory | Description |
| :---- | :---- |
| `src/components/` | Stores reusable elements across the site. (e.g. BlogPreview element) |
| `src/pages/` | Stores routes for a user to go to based on each `.js` file and nested folder (e.g. `src/pages/about.js` creates a route `/about` in the web app) |
| `src/helpers` | Stores mock data for the blog or product list and general utility functions. |

### Making changes to the Hero component

On the homepage of the website and a few other places, there is a full-width image component. We refer to this as the `<Hero/>` component. Here is a bit of an overview of what its API looks like:

```jsx
<Hero
  maxWidth='500px' // how big the image's maxumim should be
  image={'/banner1.png'} // the source location for the image
  title={'Essentials for a cold winter'} // the main text displayed
  subtitle={'Discover Autumn Winter 2021'} // text found below the main text
  ctaText={'shop now'} // the presented text for a user to click on
  ctaAction={goToShop} // the location the call-to-action text directs users
/>
```

### Making content changes to the Header or Footer

The project contains a file named `src/config.json`. Inside of this file describes the content of the header links (`headerLinks`) as well as the footer links (`footerLinks`). For the header, each element in the array has a base structure of:

```json
{
  "menuLabel": "The label that is given to a user",
  "menuLink": "The URL that this should take a user to"
}
```

If you want the menu item to have a dropdown, you can also add a `category` key with the value being an array of the categories and their containing elements, here's what the base could look like:

```json
{
  "menuLabel": "The label that is given to a user",
  "menuLink": "The URL that this should take a user to",
  "category": [
    {
      "categoryLabel": "Label you want the category to have",
      "submenu": [
        {
          "menuLabel": "A label underneath the category",
          "menuLink": "The associated link to this label"
        }
      ]
     }
  ]
}
```

The footer works in a similar way. It assumes each element in the array has a heading and an array of associated links to direct folks to:

```json
"footerLinks": [
    {
      "subTitle": "Label of the column in the footer",
      "links": [
        {
          "text": "Text to display to the user",
          "link": "URL of where to take the user to when clicked"
        },
      ]
    }
]
```

## Testing

### Included Default Testing

We’ve included some tooling that helps us maintain these templates. This template currently uses:


If your team is not interested in this tooling, you can remove them with ease!

### Removing Cypress

For our testing, we use [Cypress](https://www.cypress.io/) for end-to-end testing. This makes sure that we can validate that our templates are rendering and displaying as we’d expect. By default, we have Cypress not generate deploy links if our tests don’t pass. If you’d like to keep Cypress and still generate the deploy links, go into your `netlify.toml` and delete the plugin configuration lines:

```diff

If you’d like to remove the `netlify-plugin-cypress` build plugin entirely, you’d need to delete the entire block above instead. And then make sure sure to remove the package from the dependencies using:

```bash
npm uninstall -D netlify-plugin-cypress
```

And lastly if you’d like to remove Cypress entirely, delete the entire `cypress` folder and the `cypress.config.ts` file. Then remove the dependency using:

```bash
npm uninstall cypress
```

## Next Steps with this theme
