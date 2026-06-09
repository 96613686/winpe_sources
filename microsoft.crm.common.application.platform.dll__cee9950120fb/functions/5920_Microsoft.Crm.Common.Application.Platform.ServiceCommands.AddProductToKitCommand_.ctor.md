# Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddProductToKitCommand::.ctor

- ea: `0x5920`
- end: `0x594e`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddProductToKitCommand::.ctor`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3090`

## pseudocode

```c

```

## disassembly

```asm
0x5920  ldarg.0
0x5921  ldstr    aProduct// "product"
0x5926  ldarg.3
0x5927  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x592c  ldarg.3
0x592d  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5932  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddProductToKitRequest::.ctor()
0x5937  stloc.0
0x5938  ldloc.0
0x5939  ldarg.1
0x593a  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddProductToKitRequest::set_KitId(valuetype [mscorlib]System.Guid)
0x593f  ldloc.0
0x5940  ldarg.2
0x5941  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddProductToKitRequest::set_ProductId(valuetype [mscorlib]System.Guid)
0x5946  ldarg.0
0x5947  ldloc.0
0x5948  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x594d  ret
```
