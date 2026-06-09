# Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignResponseConfigHeader::ConfigHeader

- ea: `0x10e0`
- end: `0x114f`
- name: `Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignResponseConfigHeader::ConfigHeader`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x1135`: `LOCID_LEADCOMP_MUST_BE_SUPPLIED`
- `0x113f`: `Alert_Lead_Company_Must_Be_Supplied`

## pseudocode

```c

```

## disassembly

```asm
0x10e0  ldarg.0
0x10e1  ldarg.1
0x10e2  ldarg.2
0x10e3  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderBase::ConfigHeader(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x10e8  ldarg.1
0x10e9  ldstr    aCampaignRespon// "CAMPAIGN_RESPONSE_ACCOUNT"
0x10ee  ldc.i4.1
0x10ef  stloc.0
0x10f0  ldloca.s 0
0x10f2  ldstr    aD// "D"
0x10f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10fc  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1101  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1106  ldarg.1
0x1107  ldstr    aCampaignRespon_0// "CAMPAIGN_RESPONSE_CONTACT"
0x110c  ldc.i4.2
0x110d  stloc.0
0x110e  ldloca.s 0
0x1110  ldstr    aD// "D"
0x1115  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x111a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x111f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1124  ldarg.1
0x1125  ldstr    aCampaignGuidEm// "CAMPAIGN_GUID_EMPTY"
0x112a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x112f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, valuetype [mscorlib]System.Guid)
0x1134  ldarg.1
0x1135  ldstr    aLocidLeadcompM// "LOCID_LEADCOMP_MUST_BE_SUPPLIED"
0x113a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x113f  ldstr    aAlertLeadCompa// "Alert_Lead_Company_Must_Be_Supplied"
0x1144  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1149  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x114e  ret
```
