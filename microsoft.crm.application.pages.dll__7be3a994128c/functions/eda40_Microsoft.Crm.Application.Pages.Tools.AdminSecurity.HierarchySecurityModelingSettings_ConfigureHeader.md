# Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::ConfigureHeader

- ea: `0xeda40`
- end: `0xedab7`
- name: `Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::ConfigureHeader`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xedb30`

## string_xrefs

- `0xeda66`: `/_common/styles/dialogs.css.aspx`
- `0xeda56`: `/_common/styles/global.css.aspx`
- `0xeda46`: `HierarchySecurityConfiguration`
- `0xeda96`: `/Tools/AdminSecurity/AdminSecurityConfiguration.css.aspx`
- `0xedaac`: `/_static/tools/AdminSecurity/scripts/adminsecurity.js`

## pseudocode

```c

```

## disassembly

```asm
0xeda40  ldarg.0
0xeda41  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeda46  ldstr    aHierarchysecur_0// "HierarchySecurityConfiguration"
0xeda4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xeda50  ldarg.0
0xeda51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeda56  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0xeda5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xeda60  ldarg.0
0xeda61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeda66  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0xeda6b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xeda70  ldarg.0
0xeda71  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeda76  ldstr    aControlsNaviga// "/_controls/navigation/map.css.aspx"
0xeda7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xeda80  ldarg.0
0xeda81  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeda86  ldstr    aStaticMobileSt// "/_static/mobile/styles/console/global.c"...
0xeda8b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xeda90  ldarg.0
0xeda91  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeda96  ldstr    aToolsAdminsecu// "/Tools/AdminSecurity/AdminSecurityConfi"...
0xeda9b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xedaa0  ldarg.0
0xedaa1  call     instance void Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::IsHierarchyModelingEnabled()
0xedaa6  ldarg.0
0xedaa7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xedaac  ldstr    aStaticToolsAdm// "/_static/tools/AdminSecurity/scripts/ad"...
0xedab1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xedab6  ret
```
