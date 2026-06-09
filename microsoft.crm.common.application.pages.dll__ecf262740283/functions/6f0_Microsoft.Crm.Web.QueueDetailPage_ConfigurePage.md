# Microsoft.Crm.Web.QueueDetailPage::ConfigurePage

- ea: `0x6f0`
- end: `0x711`
- name: `Microsoft.Crm.Web.QueueDetailPage::ConfigurePage`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x706`: `/_static/_common/scripts/ribbonactions.js`

## pseudocode

```c

```

## disassembly

```asm
0x6f0  ldarg.0
0x6f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f6  ldstr    aStaticControls// "/_static/_controls/lookup/lookup.js"
0x6fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x700  ldarg.0
0x701  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x706  ldstr    aStaticCommonSc// "/_static/_common/scripts/ribbonactions."...
0x70b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x710  ret
```
