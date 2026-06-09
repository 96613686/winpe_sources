# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildArticleMenuBar

- ea: `0x21c00`
- end: `0x21d97`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildArticleMenuBar`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x1a5d0`
- `0x1ae30`
- `0x1afa0`
- `0x1b0a0`
- `0x1b140`
- `0x1b410`
- `0x21c00`
- `0x23fe0`
- `0x24210`
- `0x242b0`

## string_xrefs

- `0x21d1d`: `mnuDelete`
- `0x21d28`: `cs/articles/lookup_template.aspx`
- `0x21d3c`: `openStdDlg(Mscrm.CrmUri.create('/cs/articles/lookup_template.aspx'),window,`

## pseudocode

```c

```

## disassembly

```asm
0x21c00  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteArticle()
0x21c05  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21c0a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21c0f  brfalse.s loc_21C5C
0x21c11  ldarg.0
0x21c12  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x21c17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x21c1c  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x21c21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x21c26  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x21c2b  dup
0x21c2c  ldarg.0
0x21c2d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21c32  ldstr    aMenuitemLabelS_15// "MenuItem_Label_Submit"
0x21c37  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21c3c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x21c41  dup
0x21c42  ldarg.0
0x21c43  ldstr    aSubmit// "submit"
0x21c48  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x21c4d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x21c52  ldstr    aMnusubmit// "mnuSubmit"
0x21c57  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x21c5c  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_PublishArticle()
0x21c61  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21c66  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21c6b  brfalse  loc_21D06
0x21c70  ldarg.0
0x21c71  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x21c76  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x21c7b  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x21c80  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x21c85  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x21c8a  dup
0x21c8b  ldarg.0
0x21c8c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21c91  ldstr    aMenuitemLabelA_13// "MenuItem_Label_Approve"
0x21c96  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21c9b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x21ca0  dup
0x21ca1  ldarg.0
0x21ca2  ldstr    aApprove// "approve"
0x21ca7  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x21cac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x21cb1  ldstr    aMnuapprove// "mnuApprove"
0x21cb6  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x21cbb  ldarg.0
0x21cbc  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x21cc1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x21cc6  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x21ccb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x21cd0  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x21cd5  dup
0x21cd6  ldarg.0
0x21cd7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21cdc  ldstr    aMenuitemLabelU_1// "MenuItem_Label_Unpublish"
0x21ce1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21ce6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x21ceb  dup
0x21cec  ldarg.0
0x21ced  ldstr    aUnpublish// "unpublish"
0x21cf2  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x21cf7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x21cfc  ldstr    aMnuunpublish// "mnuUnpublish"
0x21d01  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x21d06  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteArticle()
0x21d0b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21d10  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21d15  brfalse.s loc_21D27
0x21d17  ldarg.0
0x21d18  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddDeleteButton()
0x21d1d  ldstr    aMnudelete// "mnuDelete"
0x21d22  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl::set_ID(string)
0x21d27  ldarg.0
0x21d28  ldstr    aCsArticlesLook// "cs/articles/lookup_template.aspx"
0x21d2d  call     instance valuetype WindowSize Microsoft.Crm.Application.Menus.AppGridMenuBar::GetWindowSize(string url)
0x21d32  stloc.0
0x21d33  ldarg.0
0x21d34  ldc.i4.5
0x21d35  newarr   [mscorlib]System.String
0x21d3a  dup
0x21d3b  ldc.i4.0
0x21d3c  ldstr    aOpenstddlgMscr_1// "openStdDlg(Mscrm.CrmUri.create('/cs/art"...
0x21d41  stelem.ref
0x21d42  dup
0x21d43  ldc.i4.1
0x21d44  ldloca.s 0
0x21d46  ldflda   int32 WindowSize::Width
0x21d4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21d50  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x21d55  stelem.ref
0x21d56  dup
0x21d57  ldc.i4.2
0x21d58  ldstr    asc_11387C// ","
0x21d5d  stelem.ref
0x21d5e  dup
0x21d5f  ldc.i4.3
0x21d60  ldloca.s 0
0x21d62  ldflda   int32 WindowSize::Height
0x21d67  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21d6c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x21d71  stelem.ref
0x21d72  dup
0x21d73  ldc.i4.4
0x21d74  ldstr    asc_11632C// ");"
0x21d79  stelem.ref
0x21d7a  call     string [mscorlib]System.String::Concat(string[])
0x21d7f  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript)
0x21d84  ldarg.0
0x21d85  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddPrintButton()
0x21d8a  ldarg.0
0x21d8b  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddExportButton()
0x21d90  ldarg.0
0x21d91  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddReportsButton()
0x21d96  ret
```
