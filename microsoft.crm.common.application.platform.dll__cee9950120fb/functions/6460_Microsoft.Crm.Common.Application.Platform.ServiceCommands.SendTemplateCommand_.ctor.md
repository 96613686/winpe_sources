# Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendTemplateCommand::.ctor

- ea: `0x6460`
- end: `0x64c5`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendTemplateCommand::.ctor`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x30d0`

## string_xrefs

- `0x6461`: `template`

## pseudocode

```c

```

## disassembly

```asm
0x6460  ldarg.0
0x6461  ldstr    aTemplate// "template"
0x6466  ldarg.s  8
0x6468  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x646d  ldarg.s  8
0x646f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6474  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::.ctor()
0x6479  stloc.0
0x647a  ldloc.0
0x647b  ldarg.2
0x647c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_RecipientIds(valuetype [mscorlib]System.Guid[])
0x6481  ldloc.0
0x6482  ldarg.3
0x6483  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x6488  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_RecipientType(string)
0x648d  ldloc.0
0x648e  ldarg.s  4
0x6490  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_RegardingId(valuetype [mscorlib]System.Guid)
0x6495  ldloc.0
0x6496  ldarg.s  5
0x6498  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x649d  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_RegardingType(string)
0x64a2  ldloc.0
0x64a3  ldarg.s  7
0x64a5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x64aa  ldarg.s  6
0x64ac  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x64b1  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_Sender(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x64b6  ldloc.0
0x64b7  ldarg.1
0x64b8  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_TemplateId(valuetype [mscorlib]System.Guid)
0x64bd  ldarg.0
0x64be  ldloc.0
0x64bf  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x64c4  ret
```
