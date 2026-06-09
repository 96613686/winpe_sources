# Microsoft.Crm.Asynchronous.IncrementalRollupOperation::<ExecuteCleanup>b__11_0

- ea: `0xc2b0`
- end: `0xc30e`
- name: `Microsoft.Crm.Asynchronous.IncrementalRollupOperation::<ExecuteCleanup>b__11_0`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0xc0a0`
- `0xc2b0`
- `0xce90`
- `0xceb0`
- `0xced0`
- `0xd240`
- `0xd3b0`

## string_xrefs

- `0xc2f7`: `totalRollupJobsDeleted`

## pseudocode

```c

```

## disassembly

```asm
0xc2b0  ldarg.0
0xc2b1  ldfld    class Microsoft.Crm.Asynchronous.RollupsAsyncContext Microsoft.Crm.Asynchronous.IncrementalRollupOperation::_rollupsAsyncContext
0xc2b6  ldc.i4.0
0xc2b7  ldc.i4.2
0xc2b8  newobj   instance void Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::.ctor(class Microsoft.Crm.Asynchronous.RollupsAsyncContext rollupsAsyncContext, valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RollupJobState initialState, valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RollupJobState finalState)
0xc2bd  stloc.0
0xc2be  ldarg.0
0xc2bf  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.IncrementalRollupOperation::get_AsyncEvent()
0xc2c4  dup
0xc2c5  ldvirtftn instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0xc2cb  newobj   instance void class [mscorlib]System.Func`1<valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest>::.ctor(object, native int)
0xc2d0  ldnull
0xc2d1  newobj   instance void Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::.ctor(class [mscorlib]System.Func`1<valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest> queryForEarlyExit, class Microsoft.Crm.Asynchronous.Rollups.JobSelector selector)
0xc2d6  stloc.1
0xc2d7  ldc.i4.0
0xc2d8  stloc.3
0xc2d9  ldloc.0
0xc2da  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::DeleteJobsRelatedToNonExistingRollupFields()
0xc2df  stloc.2
0xc2e0  ldloc.3
0xc2e1  ldloc.2
0xc2e2  add
0xc2e3  stloc.3
0xc2e4  ldloc.1
0xc2e5  callvirt instance bool Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::CheckForEarlyExit()
0xc2ea  brfalse.s loc_C2F3
0xc2ec  ldloc.1
0xc2ed  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::Execute()
0xc2f2  ret
0xc2f3  ldloc.2
0xc2f4  ldc.i4.0
0xc2f5  bgt.s    loc_C2D9
0xc2f7  ldstr    aTotalrollupjob// "totalRollupJobsDeleted"
0xc2fc  ldloca.s 3
0xc2fe  call     instance string [mscorlib]System.Int32::ToString()
0xc303  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0xc308  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0xc30d  ret
```
