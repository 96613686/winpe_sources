# Microsoft.Crm.Common.Application.Platform.ServiceCommands.InstantiateTemplateCommand::Execute

- ea: `0x5c50`
- end: `0x5c6c`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.InstantiateTemplateCommand::Execute`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2fd0`

## pseudocode

```c

```

## disassembly

```asm
0x5c50  ldarg.0
0x5c51  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x5c56  isinst   [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InstantiateTemplateResponse
0x5c5b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InstantiateTemplateResponse::get_EntityCollection()
0x5c60  ldarg.0
0x5c61  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_OrganizationContext()
0x5c66  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c6b  ret
```
