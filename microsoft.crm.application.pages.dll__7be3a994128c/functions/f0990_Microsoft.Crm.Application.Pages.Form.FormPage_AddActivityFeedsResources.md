# Microsoft.Crm.Application.Pages.Form.FormPage::AddActivityFeedsResources

- ea: `0xf0990`
- end: `0xf0bbd`
- name: `Microsoft.Crm.Application.Pages.Form.FormPage::AddActivityFeedsResources`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0xf0090`

## callees

- `0xf0990`
- `0xf0bc0`

## string_xrefs

- `0xf0996`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xf0afe`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0xf09a6`: `/_static/_common/scripts/Wall.Interfaces.js`
- `0xf09b6`: `/_static/_common/scripts/Wall.Control.js`
- `0xf0b1e`: `/_static/_controls/ActivityContainer/ActivityCommandBar.js`
- `0xf09d7`: `CrmSoapServiceProxy.js`
- `0xf09e2`: `Wall.Service.js`
- `0xf09f8`: `ActivityFeeds.Services.js`
- `0xf0a19`: `Wall.Extensions.js`
- `0xf0a24`: `Follow.Command.js`
- `0xf0a2f`: `Filters.Command.js`
- `0xf0a3a`: `InstalledLocales.js`

## pseudocode

```c

```

## disassembly

```asm
0xf0990  ldarg.0
0xf0991  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0996  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0xf099b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf09a0  ldarg.0
0xf09a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf09a6  ldstr    aStaticCommonSc_26// "/_static/_common/scripts/Wall.Interface"...
0xf09ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf09b0  ldarg.0
0xf09b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf09b6  ldstr    aStaticCommonSc_27// "/_static/_common/scripts/Wall.Control.j"...
0xf09bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf09c0  ldarg.0
0xf09c1  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0xf09c6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::RenderYammerGlobalVariables()
0xf09cb  ldarg.0
0xf09cc  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0xf09d1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::RenderActionHubGlobalVariables()
0xf09d6  ldarg.0
0xf09d7  ldstr    aCrmsoapservice// "CrmSoapServiceProxy.js"
0xf09dc  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf09e1  ldarg.0
0xf09e2  ldstr    aWallServiceJs// "Wall.Service.js"
0xf09e7  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf09ec  ldarg.0
0xf09ed  ldstr    aActivityfeedsM// "ActivityFeeds.Mentions.js"
0xf09f2  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf09f7  ldarg.0
0xf09f8  ldstr    aActivityfeedsS// "ActivityFeeds.Services.js"
0xf09fd  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf0a02  ldarg.0
0xf0a03  ldstr    aActivityfeedsU// "ActivityFeeds.UI.js"
0xf0a08  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf0a0d  ldarg.0
0xf0a0e  ldstr    aWallFollowacti// "Wall.FollowActions.js"
0xf0a13  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf0a18  ldarg.0
0xf0a19  ldstr    aWallExtensions// "Wall.Extensions.js"
0xf0a1e  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf0a23  ldarg.0
0xf0a24  ldstr    aFollowCommandJ// "Follow.Command.js"
0xf0a29  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf0a2e  ldarg.0
0xf0a2f  ldstr    aFiltersCommand// "Filters.Command.js"
0xf0a34  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf0a39  ldarg.0
0xf0a3a  ldstr    aInstalledlocal// "InstalledLocales.js"
0xf0a3f  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf0a44  ldarg.0
0xf0a45  ldstr    aActivityfeedsF// "ActivityFeeds.Form.js"
0xf0a4a  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf0a4f  ldarg.0
0xf0a50  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf0a55  ldstr    aActivityfeedsR// "ActivityFeeds.Resources.{0}js"
0xf0a5a  ldc.i4.1
0xf0a5b  newarr   [mscorlib]System.Object
0xf0a60  dup
0xf0a61  ldc.i4.0
0xf0a62  ldarg.1
0xf0a63  ldstr    a1033// "1033"
0xf0a68  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf0a6d  brtrue.s loc_F0A7C
0xf0a6f  ldarg.1
0xf0a70  ldstr    asc_11B5DE// "."
0xf0a75  call     string [mscorlib]System.String::Concat(string, string)
0xf0a7a  br.s     loc_F0A81
0xf0a7c  ldsfld   string [mscorlib]System.String::Empty
0xf0a81  stelem.ref
0xf0a82  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf0a87  call     instance void Microsoft.Crm.Application.Pages.Form.FormPage::AddWebResourceScript(string scriptFile)
0xf0a8c  ldarg.0
0xf0a8d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0a92  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf0a97  ldstr    a0MsdynStylesWa// "{0}msdyn_/Styles/WallContent.{1}.css"
0xf0a9c  ldc.i4.2
0xf0a9d  newarr   [mscorlib]System.Object
0xf0aa2  dup
0xf0aa3  ldc.i4.0
0xf0aa4  ldstr    aWebresource_0// "$webresource:"
0xf0aa9  stelem.ref
0xf0aaa  dup
0xf0aab  ldc.i4.1
0xf0aac  ldarg.1
0xf0aad  stelem.ref
0xf0aae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf0ab3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf0ab8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf0abd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xf0ac2  ldarg.0
0xf0ac3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0ac8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf0acd  ldstr    a0MsdynStylesUs// "{0}msdyn_/Styles/UserWall.{1}.css"
0xf0ad2  ldc.i4.2
0xf0ad3  newarr   [mscorlib]System.Object
0xf0ad8  dup
0xf0ad9  ldc.i4.0
0xf0ada  ldstr    aWebresource_0// "$webresource:"
0xf0adf  stelem.ref
0xf0ae0  dup
0xf0ae1  ldc.i4.1
0xf0ae2  ldarg.1
0xf0ae3  stelem.ref
0xf0ae4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf0ae9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf0aee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf0af3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xf0af8  ldarg.0
0xf0af9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0afe  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/jquery_ui_1.8."...
0xf0b03  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0b08  ldarg.0
0xf0b09  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0b0e  ldstr    aStaticControls_57// "/_static/_controls/ActivityContainer/Ac"...
0xf0b13  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0b18  ldarg.0
0xf0b19  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0b1e  ldstr    aStaticControls_50// "/_static/_controls/ActivityContainer/Ac"...
0xf0b23  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0b28  ldarg.0
0xf0b29  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0b2e  ldstr    aStaticFormsAct_0// "/_static/_forms/ActivitiesWallPage.js"
0xf0b33  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0b38  ldarg.0
0xf0b39  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0b3e  ldstr    aStaticWallcont// "/_static/WallControl/ActivitiesWallCont"...
0xf0b43  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf0b48  ldarg.0
0xf0b49  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0b4e  ldstr    aStaticWallcont_0// "/_static/WallControl/ActivitiesWallCont"...
0xf0b53  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf0b58  ldarg.0
0xf0b59  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0b5e  ldstr    aControlsTabsTa// "/_controls/tabs/tabs.css.aspx"
0xf0b63  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf0b68  ldarg.0
0xf0b69  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0b6e  ldstr    aStaticFormsTab_0// "/_static/_forms/Tabs.js"
0xf0b73  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0b78  ldarg.0
0xf0b79  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0b7e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf0b83  ldstr    aStaticCss0Note// "/_static/css/{0}/notesv2.css.aspx"
0xf0b88  ldc.i4.1
0xf0b89  newarr   [mscorlib]System.Object
0xf0b8e  dup
0xf0b8f  ldc.i4.0
0xf0b90  ldarg.1
0xf0b91  stelem.ref
0xf0b92  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf0b97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf0b9c  ldarg.0
0xf0b9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0ba2  ldstr    aStaticFormsNot// "/_static/_forms/Notesv2.js"
0xf0ba7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0bac  ldarg.0
0xf0bad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0bb2  ldstr    aStaticFormTurb// "/_static/form/Turbo.ActivityFeeds.js"
0xf0bb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0bbc  ret
```
