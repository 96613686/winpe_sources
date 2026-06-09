# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::ConfigureHeader

- ea: `0xed30`
- end: `0xed61`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::ConfigureHeader`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x96f0`

## string_xrefs

- `0xed36`: `/_static/_forms/linkcontrolbehavior.js`

## pseudocode

```c

```

## disassembly

```asm
0xed30  ldarg.0
0xed31  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xed36  ldstr    aStaticFormsLin// "/_static/_forms/linkcontrolbehavior.js"
0xed3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xed40  ldarg.0
0xed41  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xed46  ldstr    aLocidRequiredv// "LOCID_REQUIREDVALUE"
0xed4b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xed50  ldstr    aMsgValuerequir// "Msg_ValueRequired"
0xed55  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed5a  ldc.i4.0
0xed5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xed60  ret
```
