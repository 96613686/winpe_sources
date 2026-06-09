# Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::UpdateNextLinkedSessionIdOfParentSession

- ea: `0x16390`
- end: `0x163ef`
- name: `Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::UpdateNextLinkedSessionIdOfParentSession`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2e9a0`

## string_xrefs

- `0x163a9`: `nextlinkedsessionid`
- `0x163cc`: `For Workflow Session '{0}' Next Linked SessionId set to '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x16390  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x16395  stloc.0
0x16396  ldloc.0
0x16397  ldstr    aProcesssession_0// "processsession"
0x1639c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x163a1  ldloc.0
0x163a2  ldarg.2
0x163a3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x163a8  ldloc.0
0x163a9  ldstr    aNextlinkedsess// "nextlinkedsessionid"
0x163ae  ldstr    aProcesssession_0// "processsession"
0x163b3  ldarg.3
0x163b4  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x163b9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x163be  ldarg.1
0x163bf  ldloc.0
0x163c0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x163c5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x163ca  ldc.i4.s 0x1E
0x163cc  ldstr    aForWorkflowSes// "For Workflow Session '{0}' Next Linked "...
0x163d1  ldc.i4.2
0x163d2  newarr   [mscorlib]System.Object
0x163d7  dup
0x163d8  ldc.i4.0
0x163d9  ldarg.2
0x163da  box      [mscorlib]System.Guid
0x163df  stelem.ref
0x163e0  dup
0x163e1  ldc.i4.1
0x163e2  ldarg.3
0x163e3  box      [mscorlib]System.Guid
0x163e8  stelem.ref
0x163e9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x163ee  ret
```
