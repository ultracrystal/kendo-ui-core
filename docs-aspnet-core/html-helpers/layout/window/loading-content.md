---
title: Loading Content
page_title: Loading Content in Window | Telerik UI for ASP.NET Core HtmlHelpers
description: "Learn about the different ways of loading content in Kendo UI Window HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: htmlhelpers_window_loadingcontent_aspnetcore
position: 5
---

# Loading Content

The content of the Window HTML helper could be hardcoded or loaded dynamically at a later stage.

## Displaying Static Content

The Window exposes a `Content()` configuration method, which allows a predefined HTML content to be loaded:

###### Example

    @(Html.Kendo().Window()
        .Name("window")
        .Title("Static content")
        .Content(@<text>
                <strong>Static content</strong> of the Window.
        </text>)
    )

## Load-on-Demand Content

To configure the Window with a load-on-demand content, follow the steps listed below.

1. Create a new action method, which renders the view.

    ###### Example

        public IActionResult Index()
        {
            return View();
        }

1. Create an action method which renders the content.

    ###### Example

        public IActionResult AjaxContent()
        {
            return View();
        }

1. Add a Window.

    ###### Example

        @(Html.Kendo().Window()
            .Name("window") //The name of the Window is mandatory. It specifies the "id" attribute of the widget.
            .Title("About Alvar Aalto") //Set the title of the Window.
            .LoadContentFrom("AjaxContent", "Window") //Define the Action and Controller names.
        )

## See Also

* [Overview of Window HTML helper]({% slug htmlhelpers_window_aspnetcore %})
* [Dimensions]({% slug htmlhelpers_window_dimensions_aspnetcore %})
* [Positioning]({% slug htmlhelpers_window_positioning_aspnetcore %})
* [Constraining Position]({% slug htmlhelpers_window_constrain_aspnetcore %})
* [Using iframe]({% slug htmlhelpers_window_iframe_aspnetcore %})
* [Integration with Forms]({% slug htmlhelpers_window_forms_aspnetcore %})
