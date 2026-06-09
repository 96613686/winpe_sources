# Microsoft.Crm.Application.Components.UI.ExternalApplications::RenderSelectExternalPartyAndAutoCreateEnabledEntitiesButton

- ea: `0x184d0`
- end: `0x1855c`
- name: `Microsoft.Crm.Application.Components.UI.ExternalApplications::RenderSelectExternalPartyAndAutoCreateEnabledEntitiesButton`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18c50`

## string_xrefs

- `0x18530`: `External_Applications_Setup_AutoCreate_ExternalParty_Entities_DescriptionText`

## pseudocode

```c

```

## disassembly

```asm
0x184d0  ldarg.1
0x184d1  ldstr    aTableWidth100S// "<table width=\"100%\" style=\"padding-b"...
0x184d6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x184db  ldarg.1
0x184dc  ldstr    aTrTdClassMsCrm// "<tr><td class=\"ms-crm-Form-Section ms-"...
0x184e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x184e6  ldstr    aExternalApplic_3// "External_Applications_Setup_ExternalPar"...
0x184eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x184f0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x184f5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x184fa  ldarg.1
0x184fb  ldstr    aTrTdColspan2Wi// "<tr><td colspan=\"2\" width=\"50%\">{0}"...
0x18500  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18505  ldstr    aExternalApplic_4// "External_Applications_Setup_ExternalPar"...
0x1850a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1850f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x18514  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x18519  ldarg.0
0x1851a  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectExternalPartyEnabledEntities
0x1851f  ldarg.1
0x18520  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x18525  ldarg.1
0x18526  ldstr    aTdTrTrTdColspa// "</td></tr><tr><td colspan=\"2\" width="...
0x1852b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18530  ldstr    aExternalApplic_5// "External_Applications_Setup_AutoCreate_"...
0x18535  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1853a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1853f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x18544  ldarg.0
0x18545  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectAutoCreateExternalPartyEnabledEntities
0x1854a  ldarg.1
0x1854b  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x18550  ldarg.1
0x18551  ldstr    aTdTrTable// "</td></tr></table>"
0x18556  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1855b  ret
```
