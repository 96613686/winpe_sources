# Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMembersByFetchXmlListCommand::.ctor

- ea: `0x5860`
- end: `0x58ac`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMembersByFetchXmlListCommand::.ctor`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3050`

## string_xrefs

- `0x587c`: `Addmembers in List by fetch xml = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5860  ldarg.0
0x5861  ldstr    aList// "list"
0x5866  ldarg.3
0x5867  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x586c  ldarg.3
0x586d  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5872  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x5877  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x587c  ldstr    aAddmembersInLi// "Addmembers in List by fetch xml = {0}"
0x5881  ldc.i4.1
0x5882  newarr   [mscorlib]System.Object
0x5887  dup
0x5888  ldc.i4.0
0x5889  ldarg.2
0x588a  stelem.ref
0x588b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5890  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.AddMembersByFetchXmlListRequest::.ctor()
0x5895  stloc.0
0x5896  ldloc.0
0x5897  ldarg.1
0x5898  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.AddMembersByFetchXmlListRequest::set_ListId(valuetype [mscorlib]System.Guid)
0x589d  ldloc.0
0x589e  ldarg.2
0x589f  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.AddMembersByFetchXmlListRequest::set_FetchXml(string)
0x58a4  ldarg.0
0x58a5  ldloc.0
0x58a6  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x58ab  ret
```
