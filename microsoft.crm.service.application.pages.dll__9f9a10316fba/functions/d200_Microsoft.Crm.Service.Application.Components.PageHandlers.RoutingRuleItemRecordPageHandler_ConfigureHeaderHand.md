# Microsoft.Crm.Service.Application.Components.PageHandlers.RoutingRuleItemRecordPageHandler::ConfigureHeaderHandler

- ea: `0xd200`
- end: `0xd217`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.RoutingRuleItemRecordPageHandler::ConfigureHeaderHandler`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0xd20c`: `CustomerService`

## pseudocode

```c

```

## disassembly

```asm
0xd200  ldarg.0
0xd201  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureHeaderHandler()
0xd206  ldarg.0
0xd207  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd20c  ldstr    aCustomerservic// "CustomerService"
0xd211  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xd216  ret
```
