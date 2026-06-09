# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::RetrieveWorkflowId

- ea: `0xda70`
- end: `0xdabc`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::RetrieveWorkflowId`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xd590`

## callees

- `0xda70`

## pseudocode

```c

```

## disassembly

```asm
0xda70  ldstr    aConvertruleite// "convertruleitem"
0xda75  ldarg.1
0xda76  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xda7b  ldc.i4.1
0xda7c  newarr   [mscorlib]System.String
0xda81  dup
0xda82  ldc.i4.0
0xda83  ldstr    aWorkflowid// "workflowid"
0xda88  stelem.ref
0xda89  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xda8e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xda93  stloc.0
0xda94  ldloc.0
0xda95  brfalse.s loc_DABA
0xda97  ldloc.0
0xda98  ldstr    aWorkflowid// "workflowid"
0xda9d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xdaa2  brfalse.s loc_DABA
0xdaa4  ldloc.0
0xdaa5  ldstr    aWorkflowid// "workflowid"
0xdaaa  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xdaaf  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xdab4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xdab9  ret
0xdaba  ldnull
0xdabb  ret
```
