Shiny 0.14 Updates
================

The primary goal of this vignette is so CS / Sales can answer the question, "Whats new with Shiny" or demo the new concepts to further driver customer engagement. None of the updates are specifically Pro features.

Shiny 0.14 release to CRAN is planned to be complete and blogged by **Sept 2, 2016**. Until then, the documentation described below will be accessible at the [Shiny Staging Site](https://shiny.rstudio-staging.com/articles). The staging url should be shared with customers. Prior to the CRAN release you will also need to install Shiny from Github.

`devtools::install_github("rstudio/shiny")`

> Some updates described in Bookmarkable State will not work with SSP or RSC. Updates to SSP are planned in 3 releases over the next 2 months: Security Update (no user impact), Parity with OS SS (full support for bookmarkable state), Node.js update (no user impact)

-   [Bookmarkable State](#bookmarkable-state)
-   [Databases](#databases)
-   [Modals](#modals)
-   [Progress Bars / Notifications](#progress-bars-notifications)
-   [insertUI / removeUI](#insertui-removeui)

Many, many other minor additions that will be life savers. For instance, Shiny now prints helpful messages if an error is caused by a missing paranthesis, bracket, etc. You can also update the appearance of an action button dynamically,

Full news to share with clients: <https://github.com/rstudio/shiny/blob/master/NEWS.md>

Bookmarkable State
------------------

[Article 1 of 3](http://shiny.rstudio-staging.com/articles/bookmarking-state.html)

Bookmarkable State allows a user to save a particular view of an application. The inputs will be caputured when the user clicks bookmark and a custom url will be generated. The url will either embed the inputs or will point to hidden file saved automatically on the server. (**This feature is not yet available in Shiny Server Pro or RStudio Connect**).

When the user enters the supplied url the app will be initialized with the given inputs. There are some caveats (if the state of your app is not completely defined by the inputs) as well as many ways to customize the save and restore functionality.

The power of bookmarkable state *compared to shinyURL* is that you can save much more complicated states.

Databases
---------

[Article 5 of 5](http://shiny.rstudio-staging.com/articles/pool-dplyr.html)

The pool package was written to help users manage connections to databases within Shiny applications dynamically. (Instead of the alternatives, letting all users share a single connection or opening / closing connections for every reactive).

Pool requires the DBI package, which in turn relies on packages with specific database driveres (such as RMySql). However, used with dplyr, the user should not notice a difference between using pool and using a regular DBI connection.

Modals
------

[Article](http://shiny.rstudio-staging.com/articles/modal-dialogs.html)

Modals allow users to create pop-ups that contain instructions, messages, etc. These popups can be triggered off an observeEvent, or they could be used to display messages when the user first opens an app (ie, be sure to attend the RStudio presentation on Monday.)

Progress Bars / Notifications
-----------------------------

[Article](http://shiny.rstudio-staging.com/articles/progress.html)

Progress bars have been in Shiny for a longtime. Shiny 0.14 changes how progress bars work behind the scenes which in turn changes their appearance. There is also a new option to display notifications. Notifications are similar to modals, but by default disappear after a certain amount of time.

insertUI / removeUI
-------------------

[Addition to Dynamic UI Article](http://shiny.rstudio-staging.com/articles/dynamic-ui.html)

insertUI and removeUI allows users to dynamically generate multiple UI elements (as opposed to renderUI which is always linked to 1 UI element.) insertUI and removeUI can be used when you want to generate conditional lists (ie maps of every city in a county). Used in conjunction with modules they allow users to create complex apps.
