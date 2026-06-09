# Microsoft.Crm.Common.Application.Platform.ServiceCommands.CopyDynamicListCommand::.ctor

- ea: `0x5a60`
- end: `0x5a87`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.CopyDynamicListCommand::.ctor`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2fa0`

## pseudocode

```c

```

## disassembly

```asm
0x5a60  ldarg.0
0x5a61  ldstr    aCampaign// "campaign"
0x5a66  ldarg.2
0x5a67  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5a6c  ldarg.2
0x5a6d  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5a72  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CopyDynamicListToStaticRequest::.ctor()
0x5a77  stloc.0
0x5a78  ldloc.0
0x5a79  ldarg.1
0x5a7a  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CopyDynamicListToStaticRequest::set_ListId(valuetype [mscorlib]System.Guid)
0x5a7f  ldarg.0
0x5a80  ldloc.0
0x5a81  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x5a86  ret
```
