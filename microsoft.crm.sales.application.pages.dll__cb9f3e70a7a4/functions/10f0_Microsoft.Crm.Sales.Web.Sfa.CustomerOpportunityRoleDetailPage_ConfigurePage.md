# Microsoft.Crm.Sales.Web.Sfa.CustomerOpportunityRoleDetailPage::ConfigurePage

- ea: `0x10f0`
- end: `0x1117`
- name: `Microsoft.Crm.Sales.Web.Sfa.CustomerOpportunityRoleDetailPage::ConfigurePage`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x110c`: `/WebResources/Sales/ClientCommon/Sales_ClientCommon.js`

## pseudocode

```c

```

## disassembly

```asm
0x10f0  ldarg.0
0x10f1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigurePage()
0x10f6  ldarg.0
0x10f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10fc  ldstr    aWebresourcesCr// "/WebResources/CRM/ClientUtility.js"
0x1101  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1106  ldarg.0
0x1107  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x110c  ldstr    aWebresourcesSa// "/WebResources/Sales/ClientCommon/Sales_"...
0x1111  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1116  ret
```
