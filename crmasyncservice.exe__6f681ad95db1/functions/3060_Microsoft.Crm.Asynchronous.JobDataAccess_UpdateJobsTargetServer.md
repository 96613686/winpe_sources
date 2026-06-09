# Microsoft.Crm.Asynchronous.JobDataAccess::UpdateJobsTargetServer

- ea: `0x3060`
- end: `0x31fe`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::UpdateJobsTargetServer`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d10`

## callees

- `0x9d0`
- `0xa10`
- `0x22a0`
- `0x3060`
- `0x3580`
- `0x4320`
- `0x4340`

## string_xrefs

- `0x30b8`: `[DBUPDATES] Failed to add DB Update job for org {0} to queue. Error:{1}`
- `0x30de`: `[OrgDBUpdateThrottling] Decremented orgDBUpdatesRunning to {0} after failing to add org {1}.`
- `0x3110`: `[JOBPROCESSING] Exception occurred while attempting to process job {0} for org {1}. Error:{2}`
- `0x31b5`: `Updated NextRunTime of job {0} for org {1} to {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x3060  ldc.i4.0
0x3061  stloc.0
0x3062  br       loc_31F0
0x3067  ldarg.2
0x3068  ldloc.0
0x3069  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Item(!!T0)
0x306e  stloc.1
0x306f  ldloc.1
0x3070  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x3075  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x307a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x307f  brfalse  loc_31EC
0x3084  ldarg.0
0x3085  ldloc.1
0x3086  call     instance void Microsoft.Crm.Asynchronous.JobDataAccess::UpdateJobTargetServer(class Microsoft.Crm.Asynchronous.AsyncJob job)
0x308b  leave    loc_31EC
0x3090  stloc.2
0x3091  ldarg.2
0x3092  ldloc.1
0x3093  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::Remove(var<u1>)
0x3098  pop
0x3099  ldloc.0
0x309a  ldc.i4.1
0x309b  sub
0x309c  stloc.0
0x309d  ldloc.1
0x309e  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncJob::get_OperationType()
0x30a3  ldc.i4.s 0x2C
0x30a5  bne.un.s loc_3110
0x30a7  ldarg.0
0x30a8  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x30ad  ldflda   int32 Microsoft.Crm.Asynchronous.JobManager::OrgDBUpdatesRunning
0x30b2  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x30b7  pop
0x30b8  ldstr    aDbupdatesFaile// "[DBUPDATES] Failed to add DB Update job"...
0x30bd  ldloc.1
0x30be  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x30c3  box      [mscorlib]System.Guid
0x30c8  ldloc.2
0x30c9  callvirt instance string [mscorlib]System.Object::ToString()
0x30ce  call     string [mscorlib]System.String::Format(string, object, object)
0x30d3  ldc.i4.0
0x30d4  newarr   [mscorlib]System.Object
0x30d9  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x30de  ldstr    aOrgdbupdatethr_0// "[OrgDBUpdateThrottling] Decremented org"...
0x30e3  ldarg.0
0x30e4  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x30e9  ldfld    int32 Microsoft.Crm.Asynchronous.JobManager::OrgDBUpdatesRunning
0x30ee  box      [mscorlib]System.Int32
0x30f3  ldloc.1
0x30f4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x30f9  box      [mscorlib]System.Guid
0x30fe  call     string [mscorlib]System.String::Format(string, object, object)
0x3103  ldc.i4.0
0x3104  newarr   [mscorlib]System.Object
0x3109  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateThrottlingTelemetry(string messageFormat, object[] args)
0x310e  br.s     loc_3141
0x3110  ldstr    aJobprocessingE// "[JOBPROCESSING] Exception occurred whil"...
0x3115  ldloc.1
0x3116  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncJob::get_OperationType()
0x311b  box      [mscorlib]System.Int32
0x3120  ldloc.1
0x3121  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x3126  box      [mscorlib]System.Guid
0x312b  ldloc.2
0x312c  callvirt instance string [mscorlib]System.Object::ToString()
0x3131  call     string [mscorlib]System.String::Format(string, object, object, object)
0x3136  ldc.i4.0
0x3137  newarr   [mscorlib]System.Object
0x313c  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x3141  ldloc.2
0x3142  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x3147  brtrue.s loc_3164
0x3149  ldloc.2
0x314a  isinst   [System.Data]System.Data.SqlClient.SqlException
0x314f  brtrue.s loc_3164
0x3151  ldloc.2
0x3152  isinst   [mscorlib]System.InvalidOperationException
0x3157  brtrue.s loc_3164
0x3159  ldloc.2
0x315a  isinst   [mscorlib]System.ArgumentException
0x315f  brfalse  loc_31E8
0x3164  ldarg.0
0x3165  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x316a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_EventLog()
0x316f  ldc.i4.1
0x3170  ldc.i4   0xC000440A
0x3175  conv.u8
0x3176  ldc.i4.2
0x3177  newarr   [mscorlib]System.Object
0x317c  dup
0x317d  ldc.i4.0
0x317e  ldarg.0
0x317f  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x3184  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x3189  stelem.ref
0x318a  dup
0x318b  ldc.i4.1
0x318c  ldloc.2
0x318d  stelem.ref
0x318e  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventLogHelper::LogEvent(class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x3193  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3198  ldc.r8   2.0
0x31a1  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromHours(float64)
0x31a6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x31ab  stloc.3
0x31ac  ldarg.0
0x31ad  ldarg.1
0x31ae  ldloc.1
0x31af  ldloc.3
0x31b0  call     instance void Microsoft.Crm.Asynchronous.JobDataAccess::SetJobNextRunTime(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, class Microsoft.Crm.Asynchronous.AsyncJob job, valuetype [mscorlib]System.DateTime nextRunTime)
0x31b5  ldstr    aUpdatedNextrun// "Updated NextRunTime of job {0} for org "...
0x31ba  ldloc.1
0x31bb  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncJob::get_OperationType()
0x31c0  box      [mscorlib]System.Int32
0x31c5  ldloc.1
0x31c6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x31cb  box      [mscorlib]System.Guid
0x31d0  ldloc.3
0x31d1  box      [mscorlib]System.DateTime
0x31d6  call     string [mscorlib]System.String::Format(string, object, object, object)
0x31db  ldc.i4.0
0x31dc  newarr   [mscorlib]System.Object
0x31e1  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x31e6  br.s     loc_31EA
0x31e8  rethrow
0x31ea  leave.s  loc_31EC
0x31ec  ldloc.0
0x31ed  ldc.i4.1
0x31ee  add
0x31ef  stloc.0
0x31f0  ldloc.0
0x31f1  ldarg.2
0x31f2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x31f7  blt      loc_3067
0x31fc  ldarg.2
0x31fd  ret
```
