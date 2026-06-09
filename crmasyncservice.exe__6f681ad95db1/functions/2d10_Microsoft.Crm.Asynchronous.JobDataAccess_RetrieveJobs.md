# Microsoft.Crm.Asynchronous.JobDataAccess::RetrieveJobs

- ea: `0x2d10`
- end: `0x2dbb`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::RetrieveJobs`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2b30`

## callees

- `0x2d10`
- `0x2dc0`
- `0x3060`
- `0x3200`
- `0x3290`
- `0x4340`

## string_xrefs

- `0x2d45`: `[JOBPROCESSING] Pre-Validation: OrgUpdate = {0}.Picked {1} out of {2}.`
- `0x2d7a`: `[JOBPROCESSING] Post-Validation: OrgUpdate = {0}.Picked {1} out of {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x2d10  ldarg.2
0x2d11  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x2d16  stloc.0
0x2d17  ldarg.1
0x2d18  brfalse.s loc_2D29
0x2d1a  ldarg.0
0x2d1b  ldloc.0
0x2d1c  ldarg.s  4
0x2d1e  ldarg.s  6
0x2d20  ldarg.s  7
0x2d22  call     instance void Microsoft.Crm.Asynchronous.JobDataAccess::SetOrgUpdateJobsSql(class [System.Data]System.Data.IDbCommand selectCommand, int32 maxItemsToRetrieveFromDatabase, string maintenanceOrgInclusionClause, valuetype [mscorlib]System.DateTime startCycleTime)
0x2d27  br.s     loc_2D36
0x2d29  ldarg.0
0x2d2a  ldloc.0
0x2d2b  ldarg.s  4
0x2d2d  ldarg.s  6
0x2d2f  ldarg.s  7
0x2d31  call     instance void Microsoft.Crm.Asynchronous.JobDataAccess::SetNonOrgUpdateJobsSql(class [System.Data]System.Data.IDbCommand selectCommand, int32 maxItemsToRetrieveFromDatabase, string maintenanceOrgInclusionClause, valuetype [mscorlib]System.DateTime startCycleTime)
0x2d36  ldarg.0
0x2d37  ldloc.0
0x2d38  ldarg.1
0x2d39  ldc.i4.0
0x2d3a  ceq
0x2d3c  ldarg.s  5
0x2d3e  ldarg.3
0x2d3f  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob> Microsoft.Crm.Asynchronous.JobDataAccess::RetrieveJobs(class [System.Data]System.Data.IDbCommand selectCommand, bool checkState, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> numJobsCurrentlyRunningPerServer, int32 maxJobsToReturn)
0x2d44  stloc.1
0x2d45  ldstr    aJobprocessingP_1// "[JOBPROCESSING] Pre-Validation: OrgUpda"...
0x2d4a  ldarg.1
0x2d4b  box      [mscorlib]System.Boolean
0x2d50  ldloc.1
0x2d51  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2d56  box      [mscorlib]System.Int32
0x2d5b  ldarg.3
0x2d5c  box      [mscorlib]System.Int32
0x2d61  call     string [mscorlib]System.String::Format(string, object, object, object)
0x2d66  ldc.i4.0
0x2d67  newarr   [mscorlib]System.Object
0x2d6c  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x2d71  ldarg.0
0x2d72  ldarg.2
0x2d73  ldloc.1
0x2d74  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob> Microsoft.Crm.Asynchronous.JobDataAccess::UpdateJobsTargetServer(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob> jobs)
0x2d79  stloc.2
0x2d7a  ldstr    aJobprocessingP_2// "[JOBPROCESSING] Post-Validation: OrgUpd"...
0x2d7f  ldarg.1
0x2d80  box      [mscorlib]System.Boolean
0x2d85  ldloc.2
0x2d86  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2d8b  box      [mscorlib]System.Int32
0x2d90  ldloc.1
0x2d91  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2d96  box      [mscorlib]System.Int32
0x2d9b  call     string [mscorlib]System.String::Format(string, object, object, object)
0x2da0  ldc.i4.0
0x2da1  newarr   [mscorlib]System.Object
0x2da6  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x2dab  ldloc.2
0x2dac  stloc.3
0x2dad  leave.s  loc_2DB9
0x2daf  ldloc.0
0x2db0  brfalse.s loc_2DB8
0x2db2  ldloc.0
0x2db3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2db8  endfinally
0x2db9  ldloc.3
0x2dba  ret
```
