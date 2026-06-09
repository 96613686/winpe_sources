# Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::ConfigureHeader

- ea: `0x3830`
- end: `0x38b1`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::ConfigureHeader`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3830`

## string_xrefs

- `0x3842`: `Title_Create_MiniCampaign_Wizard`
- `0x3896`: `/_static/_common/scripts/CommandBarActions.js`

## pseudocode

```c

```

## disassembly

```asm
0x3830  ldarg.0
0x3831  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x3836  ldarg.0
0x3837  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x383c  ldarg.0
0x383d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3842  ldstr    aTitleCreateMin// "Title_Create_MiniCampaign_Wizard"
0x3847  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x384c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x3851  ldarg.0
0x3852  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3857  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x385c  ldstr    aObjecttypecode_0// "objectTypeCode"
0x3861  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3866  ldc.i4   0x1069
0x386b  stloc.0
0x386c  ldloca.s 0
0x386e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3873  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x3878  ldc.i4.5
0x3879  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x387e  brtrue.s loc_38A0
0x3880  ldarg.0
0x3881  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3886  ldstr    aStaticControls_0// "/_static/_controls/startendduration/sta"...
0x388b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3890  ldarg.0
0x3891  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3896  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/CommandBarActi"...
0x389b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x38a0  ldarg.0
0x38a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x38a6  ldstr    aStaticControls_1// "/_static/_controls/PageHandler/EntityPa"...
0x38ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x38b0  ret
```
