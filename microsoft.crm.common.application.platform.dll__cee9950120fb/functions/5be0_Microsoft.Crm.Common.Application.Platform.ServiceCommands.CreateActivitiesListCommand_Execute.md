# Microsoft.Crm.Common.Application.Platform.ServiceCommands.CreateActivitiesListCommand::Execute

- ea: `0x5be0`
- end: `0x5bf1`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.CreateActivitiesListCommand::Execute`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f60`

## pseudocode

```c

```

## disassembly

```asm
0x5be0  ldarg.0
0x5be1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x5be6  isinst   [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListResponse
0x5beb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListResponse::get_BulkOperationId()
0x5bf0  ret
```
