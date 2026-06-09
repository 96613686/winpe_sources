# Microsoft.Crm.Workflow.Services.UpdateActivityService::Execute_0

- ea: `0x1a410`
- end: `0x1a452`
- name: `Microsoft.Crm.Workflow.Services.UpdateActivityService::Execute_0`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14930`
- `0x14ec0`
- `0x1a410`
- `0x1a460`

## string_xrefs

- `0x1a413`: `Invalid argument: updateEntity`

## pseudocode

```c

```

## disassembly

```asm
0x1a410  ldarg.2
0x1a411  brtrue.s loc_1A423
0x1a413  ldstr    aInvalidArgumen_2// "Invalid argument: updateEntity"
0x1a418  ldc.i4   0x80040203
0x1a41d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1a422  throw
0x1a423  ldarg.1
0x1a424  brtrue.s loc_1A436
0x1a426  ldstr    aInvalidArgumen_0// "Invalid argument: executionContext"
0x1a42b  ldc.i4   0x80040203
0x1a430  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1a435  throw
0x1a436  ldarg.0
0x1a437  ldarg.2
0x1a438  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog(class [System.Activities]System.Activities.Activity activity)
0x1a43d  pop
0x1a43e  ldarg.0
0x1a43f  ldarg.1
0x1a440  ldarg.2
0x1a441  call     instance void Microsoft.Crm.Workflow.Services.UpdateActivityService::ExecuteInternal(class [System.Activities]System.Activities.ActivityContext executionContext, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.UpdateEntity updateEntity)
0x1a446  leave.s  loc_1A451
0x1a448  stloc.0
0x1a449  ldarg.0
0x1a44a  ldloc.0
0x1a44b  call     instance class [mscorlib]System.Exception Microsoft.Crm.Workflow.Services.ActivityServiceBase::GenerateRuntimeExceptionWrapper(class [mscorlib]System.Exception exception)
0x1a450  throw
0x1a451  ret
```
