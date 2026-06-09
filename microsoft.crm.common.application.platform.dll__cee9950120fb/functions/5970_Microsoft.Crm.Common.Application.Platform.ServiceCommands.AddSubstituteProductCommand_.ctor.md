# Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddSubstituteProductCommand::.ctor

- ea: `0x5970`
- end: `0x599e`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddSubstituteProductCommand::.ctor`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x30a0`

## pseudocode

```c

```

## disassembly

```asm
0x5970  ldarg.0
0x5971  ldstr    aProduct// "product"
0x5976  ldarg.3
0x5977  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x597c  ldarg.3
0x597d  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5982  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddSubstituteProductRequest::.ctor()
0x5987  stloc.0
0x5988  ldloc.0
0x5989  ldarg.1
0x598a  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddSubstituteProductRequest::set_ProductId(valuetype [mscorlib]System.Guid)
0x598f  ldloc.0
0x5990  ldarg.2
0x5991  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddSubstituteProductRequest::set_SubstituteId(valuetype [mscorlib]System.Guid)
0x5996  ldarg.0
0x5997  ldloc.0
0x5998  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x599d  ret
```
