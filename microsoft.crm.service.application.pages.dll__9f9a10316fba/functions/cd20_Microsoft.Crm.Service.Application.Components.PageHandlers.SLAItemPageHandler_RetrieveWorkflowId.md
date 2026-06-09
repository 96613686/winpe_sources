# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::RetrieveWorkflowId

- ea: `0xcd20`
- end: `0xcd6c`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::RetrieveWorkflowId`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xc720`

## callees

- `0xcd20`

## pseudocode

```c

```

## disassembly

```asm
0xcd20  ldstr    aSlaitem// "slaitem"
0xcd25  ldarg.1
0xcd26  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xcd2b  ldc.i4.1
0xcd2c  newarr   [mscorlib]System.String
0xcd31  dup
0xcd32  ldc.i4.0
0xcd33  ldstr    aWorkflowid// "workflowid"
0xcd38  stelem.ref
0xcd39  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcd3e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcd43  stloc.0
0xcd44  ldloc.0
0xcd45  brfalse.s loc_CD6A
0xcd47  ldloc.0
0xcd48  ldstr    aWorkflowid// "workflowid"
0xcd4d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcd52  brfalse.s loc_CD6A
0xcd54  ldloc.0
0xcd55  ldstr    aWorkflowid// "workflowid"
0xcd5a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcd5f  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xcd64  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xcd69  ret
0xcd6a  ldnull
0xcd6b  ret
```
