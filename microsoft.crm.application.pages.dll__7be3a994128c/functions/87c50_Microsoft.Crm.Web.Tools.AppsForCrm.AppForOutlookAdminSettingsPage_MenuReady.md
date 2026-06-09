# Microsoft.Crm.Web.Tools.AppsForCrm.AppForOutlookAdminSettingsPage::MenuReady

- ea: `0x87c50`
- end: `0x87d16`
- name: `Microsoft.Crm.Web.Tools.AppsForCrm.AppForOutlookAdminSettingsPage::MenuReady`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x87c6b`: `(new Mscrm.AppsForCrm.AppsForCrmAdminSettings()).ScheduleCRMAppInstallForSelectedUsers('crmGrid');`
- `0x87c85`: `/_imgs/appsforcrm/add_app_commandbar_16x16.png`
- `0x87cdf`: `/_imgs/appsforcrm/add_app_commandbar_16x16.png`
- `0x87c9f`: `appForSelectedUsersCommandBtnId`
- `0x87cc5`: `(new Mscrm.AppsForCrm.AppsForCrmAdminSettings()).ScheduleCRMAppInstallOnSave(true, 'crmGrid');`
- `0x87cf9`: `appForEligbileUsersCommandBtnId`

## pseudocode

```c

```

## disassembly

```asm
0x87c50  ldarg.2
0x87c51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x87c56  ldarg.0
0x87c57  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x87c5c  ldstr    aMailappRootpag_7// "MailApp.RootPage.Grid.Ribbon.AddApp.But"...
0x87c61  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x87c66  callvirt instance string [mscorlib]System.String::ToUpper()
0x87c6b  ldstr    aNewMscrmAppsfo// "(new Mscrm.AppsForCrm.AppsForCrmAdminSe"...
0x87c70  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x87c75  ldc.i4.1
0x87c76  newarr   [mscorlib]System.Char
0x87c7b  dup
0x87c7c  ldc.i4.0
0x87c7d  ldc.i4.s 0x2F
0x87c7f  stelem.i2
0x87c80  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x87c85  ldstr    aImgsAppsforcrm_3// "/_imgs/appsforcrm/add_app_commandbar_16"...
0x87c8a  call     string [mscorlib]System.String::Concat(string, string)
0x87c8f  ldarg.0
0x87c90  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x87c95  ldstr    aMailappRootpag_8// "MailApp.RootPage.Grid.Ribbon.AddApp.Too"...
0x87c9a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x87c9f  ldstr    aAppforselected// "appForSelectedUsersCommandBtnId"
0x87ca4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x87ca9  pop
0x87caa  ldarg.2
0x87cab  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x87cb0  ldarg.0
0x87cb1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x87cb6  ldstr    aMailappRootpag_9// "MailApp.RootPage.Grid.Ribbon.AddApp.Eli"...
0x87cbb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x87cc0  callvirt instance string [mscorlib]System.String::ToUpper()
0x87cc5  ldstr    aNewMscrmAppsfo_0// "(new Mscrm.AppsForCrm.AppsForCrmAdminSe"...
0x87cca  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x87ccf  ldc.i4.1
0x87cd0  newarr   [mscorlib]System.Char
0x87cd5  dup
0x87cd6  ldc.i4.0
0x87cd7  ldc.i4.s 0x2F
0x87cd9  stelem.i2
0x87cda  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x87cdf  ldstr    aImgsAppsforcrm_3// "/_imgs/appsforcrm/add_app_commandbar_16"...
0x87ce4  call     string [mscorlib]System.String::Concat(string, string)
0x87ce9  ldarg.0
0x87cea  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x87cef  ldstr    aMailappRootpag_10// "MailApp.RootPage.Grid.Ribbon.AddApp.Eli"...
0x87cf4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x87cf9  ldstr    aAppforeligbile// "appForEligbileUsersCommandBtnId"
0x87cfe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x87d03  pop
0x87d04  ldarg.0
0x87d05  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Web.Tools.AppsForCrm.AppForOutlookAdminSettingsPage::gridMenuBar
0x87d0a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x87d0f  ldc.i4.0
0x87d10  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x87d15  ret
```
