# Microsoft.Crm.Service.Application.Components.PageHandlers.CalendarEntityPageHandler::ConfigureHeaderHandler

- ea: `0xcf50`
- end: `0xcf6d`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.CalendarEntityPageHandler::ConfigureHeaderHandler`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0xcf62`: `CustomerService`

## pseudocode

```c

```

## disassembly

```asm
0xcf50  ldarg.0
0xcf51  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::ConfigureHeaderHandler()
0xcf56  ldarg.0
0xcf57  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::SetCommonHeader()
0xcf5c  ldarg.0
0xcf5d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xcf62  ldstr    aCustomerservic// "CustomerService"
0xcf67  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xcf6c  ret
```
