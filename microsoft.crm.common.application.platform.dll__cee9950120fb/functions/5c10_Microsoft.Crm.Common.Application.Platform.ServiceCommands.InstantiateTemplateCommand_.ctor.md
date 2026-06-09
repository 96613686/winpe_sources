# Microsoft.Crm.Common.Application.Platform.ServiceCommands.InstantiateTemplateCommand::.ctor

- ea: `0x5c10`
- end: `0x5c4c`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.InstantiateTemplateCommand::.ctor`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2fd0`

## string_xrefs

- `0x5c11`: `template`

## pseudocode

```c

```

## disassembly

```asm
0x5c10  ldarg.0
0x5c11  ldstr    aTemplate// "template"
0x5c16  ldarg.s  4
0x5c18  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c1d  ldarg.s  4
0x5c1f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c24  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InstantiateTemplateRequest::.ctor()
0x5c29  stloc.0
0x5c2a  ldloc.0
0x5c2b  ldarg.2
0x5c2c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InstantiateTemplateRequest::set_ObjectId(valuetype [mscorlib]System.Guid)
0x5c31  ldloc.0
0x5c32  ldarg.3
0x5c33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x5c38  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InstantiateTemplateRequest::set_ObjectType(string)
0x5c3d  ldloc.0
0x5c3e  ldarg.1
0x5c3f  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InstantiateTemplateRequest::set_TemplateId(valuetype [mscorlib]System.Guid)
0x5c44  ldarg.0
0x5c45  ldloc.0
0x5c46  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x5c4b  ret
```
