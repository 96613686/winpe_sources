# Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendEmailCommand::.ctor

- ea: `0x63a0`
- end: `0x63d5`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendEmailCommand::.ctor`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x30b0`

## pseudocode

```c

```

## disassembly

```asm
0x63a0  ldarg.0
0x63a1  ldstr    aEmail// "email"
0x63a6  ldarg.3
0x63a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x63ac  ldarg.3
0x63ad  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x63b2  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailRequest::.ctor()
0x63b7  stloc.0
0x63b8  ldloc.0
0x63b9  ldarg.1
0x63ba  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailRequest::set_EmailId(valuetype [mscorlib]System.Guid)
0x63bf  ldloc.0
0x63c0  ldc.i4.1
0x63c1  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailRequest::set_IssueSend(bool)
0x63c6  ldloc.0
0x63c7  ldarg.2
0x63c8  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailRequest::set_TrackingToken(string)
0x63cd  ldarg.0
0x63ce  ldloc.0
0x63cf  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x63d4  ret
```
