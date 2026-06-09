# Microsoft.Crm.Common.Application.Platform.ServiceCommands.ResolveEmailAddressCommand::Execute

- ea: `0x6360`
- end: `0x638c`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.ResolveEmailAddressCommand::Execute`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3160`

## callees

- `0x6360`

## pseudocode

```c

```

## disassembly

```asm
0x6360  ldarg.0
0x6361  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x6366  isinst   [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ResolveEmailAddressResponse
0x636b  stloc.0
0x636c  ldloc.0
0x636d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ResolveEmailAddressResponse::get_Entities()
0x6372  brtrue.s loc_637A
0x6374  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor()
0x6379  ret
0x637a  ldloc.0
0x637b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ResolveEmailAddressResponse::get_Entities()
0x6380  ldarg.0
0x6381  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_OrganizationContext()
0x6386  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x638b  ret
```
