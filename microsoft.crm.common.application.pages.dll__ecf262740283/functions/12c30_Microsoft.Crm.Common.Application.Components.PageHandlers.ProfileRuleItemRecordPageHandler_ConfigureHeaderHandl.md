# Microsoft.Crm.Common.Application.Components.PageHandlers.ProfileRuleItemRecordPageHandler::ConfigureHeaderHandler

- ea: `0x12c30`
- end: `0x12c47`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.ProfileRuleItemRecordPageHandler::ConfigureHeaderHandler`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x12c3c`: `CustomerService`

## pseudocode

```c

```

## disassembly

```asm
0x12c30  ldarg.0
0x12c31  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureHeaderHandler()
0x12c36  ldarg.0
0x12c37  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x12c3c  ldstr    aCustomerservic// "CustomerService"
0x12c41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x12c46  ret
```
