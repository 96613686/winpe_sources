# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::ConfigureHeaderHandler

- ea: `0xca70`
- end: `0xcab9`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::ConfigureHeaderHandler`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0xca98`: `CustomerService`

## pseudocode

```c

```

## disassembly

```asm
0xca70  ldarg.0
0xca71  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureHeaderHandler()
0xca76  ldarg.0
0xca77  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xca7c  ldc.i4.0
0xca7d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header::set_DeferAllScripts(bool)
0xca82  ldarg.0
0xca83  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xca88  ldstr    aWorkflow// "Workflow"
0xca8d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xca92  ldarg.0
0xca93  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xca98  ldstr    aCustomerservic// "CustomerService"
0xca9d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xcaa2  ldarg.0
0xcaa3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcaa8  ldstr    aSlatype// "slatype"
0xcaad  ldarg.0
0xcaae  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::useSLAKPI
0xcab3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xcab8  ret
```
