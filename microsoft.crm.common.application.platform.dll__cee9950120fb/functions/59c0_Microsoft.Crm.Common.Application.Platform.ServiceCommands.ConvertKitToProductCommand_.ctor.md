# Microsoft.Crm.Common.Application.Platform.ServiceCommands.ConvertKitToProductCommand::.ctor

- ea: `0x59c0`
- end: `0x59e7`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.ConvertKitToProductCommand::.ctor`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f80`

## pseudocode

```c

```

## disassembly

```asm
0x59c0  ldarg.0
0x59c1  ldstr    aProduct// "product"
0x59c6  ldarg.2
0x59c7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x59cc  ldarg.2
0x59cd  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x59d2  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ConvertKitToProductRequest::.ctor()
0x59d7  stloc.0
0x59d8  ldloc.0
0x59d9  ldarg.1
0x59da  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ConvertKitToProductRequest::set_KitId(valuetype [mscorlib]System.Guid)
0x59df  ldarg.0
0x59e0  ldloc.0
0x59e1  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x59e6  ret
```
