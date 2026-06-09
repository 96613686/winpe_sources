# Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendFaxCommand::.ctor

- ea: `0x6410`
- end: `0x643e`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendFaxCommand::.ctor`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x30c0`

## pseudocode

```c

```

## disassembly

```asm
0x6410  ldarg.0
0x6411  ldstr    aFax// "fax"
0x6416  ldarg.2
0x6417  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x641c  ldarg.2
0x641d  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6422  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendFaxRequest::.ctor()
0x6427  stloc.0
0x6428  ldloc.0
0x6429  ldarg.1
0x642a  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendFaxRequest::set_FaxId(valuetype [mscorlib]System.Guid)
0x642f  ldloc.0
0x6430  ldc.i4.1
0x6431  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendFaxRequest::set_IssueSend(bool)
0x6436  ldarg.0
0x6437  ldloc.0
0x6438  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x643d  ret
```
