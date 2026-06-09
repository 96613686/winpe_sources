# Microsoft.Crm.Common.Application.Platform.ServiceCommands.ListSnapshotsCommand::.ctor

- ea: `0x5c80`
- end: `0x5ca7`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.ListSnapshotsCommand::.ctor`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x30f0`

## pseudocode

```c

```

## disassembly

```asm
0x5c80  ldarg.0
0x5c81  ldstr    aReport// "report"
0x5c86  ldarg.2
0x5c87  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c8c  ldarg.2
0x5c8d  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c92  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ListSnapshotsRequest::.ctor()
0x5c97  stloc.0
0x5c98  ldloc.0
0x5c99  ldarg.1
0x5c9a  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ListSnapshotsRequest::set_ReportId(valuetype [mscorlib]System.Guid)
0x5c9f  ldarg.0
0x5ca0  ldloc.0
0x5ca1  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x5ca6  ret
```
