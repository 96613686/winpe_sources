# Microsoft.Crm.Asynchronous.JobDataAccess::GetNextJob

- ea: `0x2b30`
- end: `0x2d03`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::GetNextJob`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2ae0`

## callees

- `0x2950`
- `0x2b30`
- `0x2d10`
- `0x3410`
- `0x3600`
- `0x36a0`
- `0x3730`
- `0x3850`
- `0x3f20`
- `0x3fa0`
- `0x4340`

## string_xrefs

- `0x2bda`: `[JOBPROCESSING] Picked {0} org update jobs.`
- `0x2c24`: `[JOBPROCESSING] Picked {0} non org update jobs.`

## pseudocode

```c

```

## disassembly

```asm
0x2b30  ldarg.0
0x2b31  ldc.i4.1
0x2b32  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.JobDataAccess::CreateConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope configScope)
0x2b37  stloc.0
0x2b38  ldarg.1
0x2b39  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x2b3e  brtrue.s loc_2B69
0x2b40  ldstr    aJobprocessingN// "[JOBPROCESSING] No orgs available for m"...
0x2b45  ldarg.2
0x2b46  box      [mscorlib]System.DateTime
0x2b4b  ldarg.3
0x2b4c  box      [mscorlib]System.Int32
0x2b51  call     string [mscorlib]System.String::Format(string, object, object)
0x2b56  ldc.i4.0
0x2b57  newarr   [mscorlib]System.Object
0x2b5c  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x2b61  ldnull
0x2b62  stloc.s  4
0x2b64  leave    loc_2D00
0x2b69  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_JobsToReturnInSql()
0x2b6e  stloc.1
0x2b6f  ldloc.0
0x2b70  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x2b75  ldarg.0
0x2b76  ldloc.0
0x2b77  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.JobDataAccess::GetNumJobsCurrentlyRunningPerServer(class [System.Data]System.Data.IDbConnection connection)
0x2b7c  stloc.2
0x2b7d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::.ctor()
0x2b82  stloc.3
0x2b83  ldloc.0
0x2b84  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x2b89  stloc.s  5
0x2b8b  ldsfld   string [mscorlib]System.String::Empty
0x2b90  stloc.s  6
0x2b92  ldstr    aAndJOrganizati// "AND j.OrganizationId IN "
0x2b97  ldarg.0
0x2b98  ldarg.1
0x2b99  call     instance string Microsoft.Crm.Asynchronous.JobDataAccess::GetInClause(class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> list)
0x2b9e  call     string [mscorlib]System.String::Concat(string, string)
0x2ba3  stloc.s  6
0x2ba5  ldc.i4.0
0x2ba6  stloc.s  7
0x2ba8  ldarg.0
0x2ba9  call     instance bool Microsoft.Crm.Asynchronous.JobDataAccess::ShouldSkipOrgUpdates()
0x2bae  brtrue.s loc_2BF6
0x2bb0  ldarg.0
0x2bb1  ldc.i4.1
0x2bb2  ldloc.0
0x2bb3  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_MaxConcurrentOrgDBUpdateJobsPerAsyncServer()
0x2bb8  ldloc.1
0x2bb9  ldloc.2
0x2bba  ldloc.s  6
0x2bbc  ldarga.s 2
0x2bbe  ldc.r8   15.0
0x2bc7  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x2bcc  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob> Microsoft.Crm.Asynchronous.JobDataAccess::RetrieveJobs(bool isOrgUpdate, class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, int32 maxJobsToReturn, int32 maxItemsToRetrieveFromDatabase, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> numJobsCurrentlyRunningPerServer, string maintenanceOrgInclusionClause, valuetype [mscorlib]System.DateTime startCycleTime)
0x2bd1  stloc.3
0x2bd2  ldloc.3
0x2bd3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2bd8  stloc.s  7
0x2bda  ldstr    aJobprocessingP// "[JOBPROCESSING] Picked {0} org update j"...
0x2bdf  ldloc.s  7
0x2be1  box      [mscorlib]System.Int32
0x2be6  call     string [mscorlib]System.String::Format(string, object)
0x2beb  ldc.i4.0
0x2bec  newarr   [mscorlib]System.Object
0x2bf1  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x2bf6  ldloc.3
0x2bf7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2bfc  ldarg.3
0x2bfd  bge.s    loc_2C4D
0x2bff  ldarg.0
0x2c00  ldc.i4.0
0x2c01  ldloc.0
0x2c02  ldarg.3
0x2c03  ldloc.3
0x2c04  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2c09  sub
0x2c0a  ldloc.1
0x2c0b  ldloc.2
0x2c0c  ldloc.s  6
0x2c0e  ldarg.2
0x2c0f  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob> Microsoft.Crm.Asynchronous.JobDataAccess::RetrieveJobs(bool isOrgUpdate, class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, int32 maxJobsToReturn, int32 maxItemsToRetrieveFromDatabase, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> numJobsCurrentlyRunningPerServer, string maintenanceOrgInclusionClause, valuetype [mscorlib]System.DateTime startCycleTime)
0x2c14  stloc.s  8
0x2c16  ldloc.s  8
0x2c18  brfalse.s loc_2C4D
0x2c1a  ldloc.s  8
0x2c1c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2c21  ldc.i4.0
0x2c22  ble.s    loc_2C4D
0x2c24  ldstr    aJobprocessingP_0// "[JOBPROCESSING] Picked {0} non org upda"...
0x2c29  ldloc.s  8
0x2c2b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2c30  box      [mscorlib]System.Int32
0x2c35  call     string [mscorlib]System.String::Format(string, object)
0x2c3a  ldc.i4.0
0x2c3b  newarr   [mscorlib]System.Object
0x2c40  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x2c45  ldloc.3
0x2c46  ldloc.s  8
0x2c48  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x2c4d  ldloc.3
0x2c4e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2c53  brtrue.s loc_2C74
0x2c55  ldstr    aJobprocessingD// "[JOBPROCESSING] Did not pick any job fo"...
0x2c5a  ldc.i4.0
0x2c5b  newarr   [mscorlib]System.Object
0x2c60  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x2c65  ldarg.0
0x2c66  ldloc.0
0x2c67  call     instance void Microsoft.Crm.Asynchronous.JobDataAccess::LogPendingOrgDBUpdateJobsInfo(class [System.Data]System.Data.IDbConnection connection)
0x2c6c  ldnull
0x2c6d  stloc.s  4
0x2c6f  leave    loc_2D00
0x2c74  ldarg.0
0x2c75  ldloc.0
0x2c76  ldloc.3
0x2c77  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.AsyncJob, valuetype [mscorlib]System.Guid> <>c::<>9__26_0
0x2c7c  dup
0x2c7d  brtrue.s loc_2C96
0x2c7f  pop
0x2c80  ldsfld   class <>c <>c::<>9
0x2c85  ldftn    instance valuetype [mscorlib]System.Guid <>c::<GetNextJob>b__26_0(class Microsoft.Crm.Asynchronous.AsyncJob x)
0x2c8b  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.AsyncJob, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x2c90  dup
0x2c91  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.AsyncJob, valuetype [mscorlib]System.Guid> <>c::<>9__26_0
0x2c96  call     T0x2B000007
0x2c9b  call     T0x2B000008
0x2ca0  call     instance void Microsoft.Crm.Asynchronous.JobDataAccess::UpdateMaintenanceJobs(class [System.Data]System.Data.IDbConnection connection, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> ids)
0x2ca5  ldstr    aJobprocessingF// "[JOBPROCESSING] Final: Picked {0} out o"...
0x2caa  ldloc.3
0x2cab  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2cb0  box      [mscorlib]System.Int32
0x2cb5  ldarg.3
0x2cb6  box      [mscorlib]System.Int32
0x2cbb  call     string [mscorlib]System.String::Format(string, object, object)
0x2cc0  ldc.i4.0
0x2cc1  newarr   [mscorlib]System.Object
0x2cc6  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x2ccb  ldloc.s  7
0x2ccd  ldc.i4.0
0x2cce  ble.s    loc_2CD9
0x2cd0  ldloc.3
0x2cd1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2cd6  ldc.i4.0
0x2cd7  bgt.s    loc_2CE0
0x2cd9  ldarg.0
0x2cda  ldloc.0
0x2cdb  call     instance void Microsoft.Crm.Asynchronous.JobDataAccess::LogPendingOrgDBUpdateJobsInfo(class [System.Data]System.Data.IDbConnection connection)
0x2ce0  ldloc.3
0x2ce1  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::ToArray()
0x2ce6  stloc.s  4
0x2ce8  leave.s  loc_2D00
0x2cea  ldloc.s  5
0x2cec  brfalse.s loc_2CF5
0x2cee  ldloc.s  5
0x2cf0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2cf5  endfinally
0x2cf6  ldloc.0
0x2cf7  brfalse.s loc_2CFF
0x2cf9  ldloc.0
0x2cfa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2cff  endfinally
0x2d00  ldloc.s  4
0x2d02  ret
```
