# Microsoft.Crm.Common.Application.Platform.ServiceCommands.ConvertProductToKitCommand::.ctor

- ea: `0x5a10`
- end: `0x5a37`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.ConvertProductToKitCommand::.ctor`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f90`

## pseudocode

```c

```

## disassembly

```asm
0x5a10  ldarg.0
0x5a11  ldstr    aProduct// "product"
0x5a16  ldarg.2
0x5a17  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5a1c  ldarg.2
0x5a1d  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5a22  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ConvertProductToKitRequest::.ctor()
0x5a27  stloc.0
0x5a28  ldloc.0
0x5a29  ldarg.1
0x5a2a  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ConvertProductToKitRequest::set_ProductId(valuetype [mscorlib]System.Guid)
0x5a2f  ldarg.0
0x5a30  ldloc.0
0x5a31  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x5a36  ret
```
