# Microsoft.Crm.Asynchronous.JobDataAccess::ShouldSkipOrgUpdates

- ea: `0x3410`
- end: `0x3574`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::ShouldSkipOrgUpdates`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x2b30`

## callees

- `0x3410`
- `0x3b70`
- `0x3f80`
- `0x3f90`
- `0x3fa0`
- `0x42a0`
- `0x42e0`
- `0x4320`
- `0x4340`

## string_xrefs

- `0x3453`: `[DBUPDATES] DB Update Scheduling feature is enabled. Non-Business hours start: {0}, `
- `0x3493`: `[DBUPDATES][ENABLED] Current time {0} is outside of business hours, will allow db updates to be run.`
- `0x34ab`: `[DBUPDATES][DISABLED] Current time {0} is NOT outside of business hours, will NOT allow db updates to be run.`
- `0x34c3`: `[DBUPDATES][DISABLED] Unable to determine if current time {0} is outside of business hours, will NOT allow db updates to be run.`
- `0x34db`: `[DBUPDATES][DISABLED] DB Update Scheduling feature is NOT enabled, will NOT allow db updates to be run.`
- `0x34fe`: `[OrgDBUpdateThrottling] Feature is enabled.`
- `0x3522`: `[OrgDBUpdateThrottling] OrgDBUpdatesRunning = {0}, `
- `0x353c`: `MaxConcurrentOrgDBUpdateJobsPerAsyncServer = {0}. Will NOT retrieve org db update jobs (type 44).`
- `0x3562`: `[OrgDBUpdateThrottling] Feature is disabled.`

## pseudocode

```c

```

## disassembly

```asm
0x3410  ldc.i4.1
0x3411  stloc.0
0x3412  ldarg.0
0x3413  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x3418  callvirt instance bool Microsoft.Crm.Asynchronous.JobManager::ShouldScheduleOrgDBUpdates()
0x341d  brfalse  loc_34DB
0x3422  ldc.i4.0
0x3423  stloc.1
0x3424  ldloca.s 1
0x3426  call     bool Microsoft.Crm.Asynchronous.JobDataAccess::TryCheckIfIsOutsideOfBusinessHour([out] bool& isOutsideOfBusinessHour)
0x342b  stloc.2
0x342c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3431  stloc.s  4
0x3433  ldloca.s 4
0x3435  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0x343a  stloc.s  4
0x343c  ldloca.s 4
0x343e  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x3443  stloc.s  5
0x3445  ldloca.s 5
0x3447  constrained. [mscorlib]System.TimeSpan
0x344d  callvirt instance string [mscorlib]System.Object::ToString()
0x3452  stloc.3
0x3453  ldstr    aDbupdatesDbUpd// "[DBUPDATES] DB Update Scheduling featur"...
0x3458  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_NonBusinessHourStartTimeOfDay()
0x345d  box      [mscorlib]System.Int32
0x3462  call     string [mscorlib]System.String::Format(string, object)
0x3467  ldstr    aNonBusinessHou// "Non-Business hours end: {0}."
0x346c  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_NonBusinessHourEndTimeOfDay()
0x3471  box      [mscorlib]System.Int32
0x3476  call     string [mscorlib]System.String::Format(string, object)
0x347b  call     string [mscorlib]System.String::Concat(string, string)
0x3480  ldc.i4.0
0x3481  newarr   [mscorlib]System.Object
0x3486  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x348b  ldloc.2
0x348c  brfalse.s loc_34C3
0x348e  ldloc.1
0x348f  brfalse.s loc_34AB
0x3491  ldc.i4.0
0x3492  stloc.0
0x3493  ldstr    aDbupdatesEnabl// "[DBUPDATES][ENABLED] Current time {0} i"...
0x3498  ldloc.3
0x3499  call     string [mscorlib]System.String::Format(string, object)
0x349e  ldc.i4.0
0x349f  newarr   [mscorlib]System.Object
0x34a4  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x34a9  br.s     loc_34EB
0x34ab  ldstr    aDbupdatesDisab// "[DBUPDATES][DISABLED] Current time {0} "...
0x34b0  ldloc.3
0x34b1  call     string [mscorlib]System.String::Format(string, object)
0x34b6  ldc.i4.0
0x34b7  newarr   [mscorlib]System.Object
0x34bc  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x34c1  br.s     loc_34EB
0x34c3  ldstr    aDbupdatesDisab_0// "[DBUPDATES][DISABLED] Unable to determi"...
0x34c8  ldloc.3
0x34c9  call     string [mscorlib]System.String::Format(string, object)
0x34ce  ldc.i4.0
0x34cf  newarr   [mscorlib]System.Object
0x34d4  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x34d9  br.s     loc_34EB
0x34db  ldstr    aDbupdatesDisab_1// "[DBUPDATES][DISABLED] DB Update Schedul"...
0x34e0  ldc.i4.0
0x34e1  newarr   [mscorlib]System.Object
0x34e6  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x34eb  ldloc.0
0x34ec  brtrue   loc_3572
0x34f1  ldarg.0
0x34f2  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x34f7  callvirt instance bool Microsoft.Crm.Asynchronous.JobManager::ShouldThrottleOrgDBUpdates()
0x34fc  brfalse.s loc_3562
0x34fe  ldstr    aOrgdbupdatethr_2// "[OrgDBUpdateThrottling] Feature is enab"...
0x3503  ldc.i4.0
0x3504  newarr   [mscorlib]System.Object
0x3509  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateThrottlingTelemetry(string messageFormat, object[] args)
0x350e  ldarg.0
0x350f  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x3514  ldfld    int32 Microsoft.Crm.Asynchronous.JobManager::OrgDBUpdatesRunning
0x3519  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_MaxConcurrentOrgDBUpdateJobsPerAsyncServer()
0x351e  blt.s    loc_3572
0x3520  ldc.i4.1
0x3521  stloc.0
0x3522  ldstr    aOrgdbupdatethr_3// "[OrgDBUpdateThrottling] OrgDBUpdatesRun"...
0x3527  ldarg.0
0x3528  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x352d  ldfld    int32 Microsoft.Crm.Asynchronous.JobManager::OrgDBUpdatesRunning
0x3532  box      [mscorlib]System.Int32
0x3537  call     string [mscorlib]System.String::Format(string, object)
0x353c  ldstr    aMaxconcurrento// "MaxConcurrentOrgDBUpdateJobsPerAsyncSer"...
0x3541  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_MaxConcurrentOrgDBUpdateJobsPerAsyncServer()
0x3546  box      [mscorlib]System.Int32
0x354b  call     string [mscorlib]System.String::Format(string, object)
0x3550  call     string [mscorlib]System.String::Concat(string, string)
0x3555  ldc.i4.0
0x3556  newarr   [mscorlib]System.Object
0x355b  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateThrottlingTelemetry(string messageFormat, object[] args)
0x3560  br.s     loc_3572
0x3562  ldstr    aOrgdbupdatethr_4// "[OrgDBUpdateThrottling] Feature is disa"...
0x3567  ldc.i4.0
0x3568  newarr   [mscorlib]System.Object
0x356d  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateThrottlingTelemetry(string messageFormat, object[] args)
0x3572  ldloc.0
0x3573  ret
```
