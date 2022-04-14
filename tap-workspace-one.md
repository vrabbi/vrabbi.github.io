Configuring Tanzu Application Platform to use WorkspaceONE
authentication.

**[Workspace ONE Configuration]{.underline}**

1.  Login to the admin portal and navigate to **Catalog \> Web Apps**

![Graphical user interface, application Description automatically
generated](./images//media/image1.png)

2.  Create a new Web App by selecting the **New** button

![Graphical user interface, text, application Description automatically
generated](./images//media/image2.png)

3.  Enter the **Name** and if desired select an icon and add a
    description for the Web App in Workspace ONE

![Graphical user interface, application Description automatically
generated](./images//media/image3.png)

4.  Web App configuration

    a.  Set the **Authentication Type** to be "OpenID Connect"

    b.  Set the **Target URL** to be the URL of your Tanzu Application
        Platform GUI

    c.  Set the **Redirect URL** to be the URL of your Tanzu Application
        Platform GUI with the path suffix of
        "/api/auth/oidc/handler/frame"

    d.  Set the **Client ID** to be any descriptive name that makes
        sense such as "tap-gui"

    e.  Set the **Client Secret** to be a unique string (can be
        generated via a command such as "openssl rand -base64 32")

    f.  Set the **Show in User Portal** to true

![Graphical user interface, text, application, email Description
automatically
generated](./images//media/image4.png)

![A picture containing graphical user interface Description
automatically
generated](./images//media/image5.png)

5.  Select the access policy you want applied to your Web App

![Graphical user interface, text, application, email Description
automatically
generated](./images//media/image6.png)

6.  Validate on the summary page everything is correct and then click on
    **Save and Assign** to add access for users to the Web App

![Graphical user interface, text, application Description automatically
generated](./images//media/image7.png)

7.  Select Users and or Groups via the search bar that should have
    access to the TAP GUI via Workspace ONE

![Graphical user interface, text, application, email Description
automatically
generated](./images//media/image8.png)

8.  Navigate to **Catalog \> Settings**

![Graphical user interface, text, application, chat or text message
Description automatically
generated](./images//media/image9.png)

9.  Select the **Remote App Access** tab

![Graphical user interface, text, application Description automatically
generated](./images//media/image10.png)

10. Find your Web App in the list and click on it to view the advanced
    configurations

![](./images//media/image11.png)

11. Click on the **Edit** button under the **Scope** section

![Graphical user interface, text, application Description automatically
generated](./images//media/image12.png)

12. Select the scopes as depicted in the picture bellow

![Graphical user interface, text, application, email Description
automatically
generated](./images//media/image13.png)

13. Your Web App is now fully configured and ready to use with TAP GUI!

**[Tanzu Application Platform GUI Configuration]{.underline}**

In your values file for the TAP installation where you will be
installing TAP GUI you need to configure the Authentication backend to
use our newly created Web App from WorkspaceONE as described bellow:

![Text Description automatically
generated](./images//media/image14.png)

Once configured you can now either install TAP GUI or reconfigure it
using the standard Tanzu CLI method.
