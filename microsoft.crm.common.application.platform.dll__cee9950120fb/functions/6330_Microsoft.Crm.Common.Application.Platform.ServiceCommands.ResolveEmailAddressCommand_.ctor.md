# Microsoft.Crm.Common.Application.Platform.ServiceCommands.ResolveEmailAddressCommand::.ctor

- ea: `0x6330`
- end: `0x6353`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.ResolveEmailAddressCommand::.ctor`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3160`

## pseudocode

```c

```

## disassembly

```asm
0x6330  ldarg.0
0x6331  ldarg.3
0x6332  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6337  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ResolveEmailAddressRequest::.ctor()
0x633c  stloc.0
0x633d  ldloc.0
0x633e  ldarg.1
0x633f  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ResolveEmailAddressRequest::set_EmailAddresses(string)
0x6344  ldloc.0
0x6345  ldarg.2
0x6346  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ResolveEmailAddressRequest::set_ObjectTypeCodes(int32[])
0x634b  ldarg.0
0x634c  ldloc.0
0x634d  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x6352  ret
```
