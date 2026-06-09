# Microsoft.Crm.Common.Application.Platform.ServiceCommands.RemoveMembersByFetchXmlListCommand::.ctor

- ea: `0x62b0`
- end: `0x630e`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.RemoveMembersByFetchXmlListCommand::.ctor`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2fc0`

## string_xrefs

- `0x62ce`: `Qualify List by fetch xml = {0} and keep = {1}`

## pseudocode

```c

```

## disassembly

```asm
0x62b0  ldarg.0
0x62b1  ldstr    aList// "list"
0x62b6  ldarg.s  4
0x62b8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x62bd  ldarg.s  4
0x62bf  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x62c4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x62c9  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x62ce  ldstr    aQualifyListByF// "Qualify List by fetch xml = {0} and kee"...
0x62d3  ldc.i4.2
0x62d4  newarr   [mscorlib]System.Object
0x62d9  dup
0x62da  ldc.i4.0
0x62db  ldarg.2
0x62dc  stelem.ref
0x62dd  dup
0x62de  ldc.i4.1
0x62df  ldarg.3
0x62e0  box      [mscorlib]System.Boolean
0x62e5  stelem.ref
0x62e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x62eb  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.RemoveMembersByFetchXmlListRequest::.ctor()
0x62f0  stloc.0
0x62f1  ldloc.0
0x62f2  ldarg.1
0x62f3  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.RemoveMembersByFetchXmlListRequest::set_ListId(valuetype [mscorlib]System.Guid)
0x62f8  ldloc.0
0x62f9  ldarg.2
0x62fa  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.RemoveMembersByFetchXmlListRequest::set_FetchXml(string)
0x62ff  ldloc.0
0x6300  ldarg.3
0x6301  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.RemoveMembersByFetchXmlListRequest::set_KeepReturned(bool)
0x6306  ldarg.0
0x6307  ldloc.0
0x6308  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x630d  ret
```
