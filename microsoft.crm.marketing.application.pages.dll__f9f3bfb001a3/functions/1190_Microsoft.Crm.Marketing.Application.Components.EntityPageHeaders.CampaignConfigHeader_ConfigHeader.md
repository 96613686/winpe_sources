# Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignConfigHeader::ConfigHeader

- ea: `0x1190`
- end: `0x11ed`
- name: `Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignConfigHeader::ConfigHeader`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x11cf`: `Object_Singular_CampaignTemplate`
- `0x11e1`: `LOCID_CAMPAIGN_NEWTEMPLATE`

## pseudocode

```c

```

## disassembly

```asm
0x1190  ldarg.0
0x1191  ldarg.1
0x1192  ldarg.2
0x1193  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderBase::ConfigHeader(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x1198  ldarg.1
0x1199  ldstr    aMarketingautom// "MarketingAutomation"
0x119e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x11a3  ldarg.1
0x11a4  ldstr    aStaticMaCampai// "/_static/MA/campaign/campaign.js"
0x11a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x11ae  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x11b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11b8  ldstr    aFormTitleNewWi// "Form_Title_New_With_Entity_Display_Name"
0x11bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11c2  ldc.i4.1
0x11c3  newarr   [mscorlib]System.Object
0x11c8  dup
0x11c9  ldc.i4.0
0x11ca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11cf  ldstr    aObjectSingular// "Object_Singular_CampaignTemplate"
0x11d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11d9  stelem.ref
0x11da  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11df  stloc.0
0x11e0  ldarg.1
0x11e1  ldstr    aLocidCampaignN// "LOCID_CAMPAIGN_NEWTEMPLATE"
0x11e6  ldloc.0
0x11e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x11ec  ret
```
