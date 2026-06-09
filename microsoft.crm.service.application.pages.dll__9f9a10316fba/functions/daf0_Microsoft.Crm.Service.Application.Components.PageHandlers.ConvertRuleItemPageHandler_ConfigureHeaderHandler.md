# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::ConfigureHeaderHandler

- ea: `0xdaf0`
- end: `0xdb27`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::ConfigureHeaderHandler`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0xdb0c`: `CustomerService`

## pseudocode

```c

```

## disassembly

```asm
0xdaf0  ldarg.0
0xdaf1  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureHeaderHandler()
0xdaf6  ldarg.0
0xdaf7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xdafc  ldstr    aStaticToolsSys_0// "/_static/Tools/SystemCustomization/Scri"...
0xdb01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdb06  ldarg.0
0xdb07  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xdb0c  ldstr    aCustomerservic// "CustomerService"
0xdb11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xdb16  ldarg.0
0xdb17  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xdb1c  ldstr    aWorkflow// "Workflow"
0xdb21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xdb26  ret
```
