# Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::ConfigurePage

- ea: `0x18df0`
- end: `0x18eba`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::ConfigurePage`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19c00`

## callees

- `0x19360`
- `0x193f0`

## string_xrefs

- `0x18e87`: `/_static/_common/scripts/CommandBarActions.js`

## pseudocode

```c

```

## disassembly

```asm
0x18df0  ldarg.0
0x18df1  ldarg.0
0x18df2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18df7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18dfc  ldstr    aItotal// "iTotal"
0x18e01  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18e06  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18e0b  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x18e10  stfld    int32 Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::TotalRecords
0x18e15  ldarg.0
0x18e16  ldarg.0
0x18e17  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18e1c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18e21  ldstr    aIobjtype// "iObjType"
0x18e26  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18e2b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18e30  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x18e35  stfld    int32 Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::EntityTypeCode
0x18e3a  ldarg.0
0x18e3b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x18e40  ldstr    aIobjtype_0// "_iObjType"
0x18e45  ldarg.0
0x18e46  ldfld    int32 Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::EntityTypeCode
0x18e4b  conv.i8
0x18e4c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x18e51  ldarg.0
0x18e52  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x18e57  ldstr    aStaticGridCmds// "/_static/_grid/cmds/multiaction.js"
0x18e5c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x18e61  ldarg.0
0x18e62  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x18e67  ldstr    aStaticGridCmds_1// "/_static/_grid/cmds/listactivity.js"
0x18e6c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x18e71  ldarg.0
0x18e72  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x18e77  ldstr    aStaticControls_11// "/_static/_controls/PageHandler/EntityPa"...
0x18e7c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x18e81  ldarg.0
0x18e82  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x18e87  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/CommandBarActi"...
0x18e8c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x18e91  ldarg.0
0x18e92  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x18e97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0x18e9c  ldarg.0
0x18e9d  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0x18ea2  ldarg.0
0x18ea3  callvirt instance void Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::InitializeActivityEntity()
0x18ea8  ldarg.0
0x18ea9  ldarg.0
0x18eaa  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::get_CurrentActivity()
0x18eaf  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x18eb4  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x18eb9  ret
```
