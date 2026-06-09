# Microsoft.Crm.Asynchronous.JobDataAccess::ShouldSkipProcessingJob

- ea: `0x33a0`
- end: `0x340c`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::ShouldSkipProcessingJob`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2dc0`

## callees

- `0x33a0`
- `0x3fa0`
- `0x42a0`
- `0x4320`

## string_xrefs

- `0x33c4`: `[OrgDBUpdateThrottling] OrgDBUpdatesRunning = {0}, MaxConcurrentOrgDBUpdateJobsPerAsyncServer = {1}. `

## pseudocode

```c

```

## disassembly

```asm
0x33a0  ldarg.1
0x33a1  ldc.i4.s 0x2C
0x33a3  bne.un.s loc_340A
0x33a5  ldarg.0
0x33a6  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x33ab  callvirt instance bool Microsoft.Crm.Asynchronous.JobManager::ShouldThrottleOrgDBUpdates()
0x33b0  brfalse.s loc_340A
0x33b2  ldarg.0
0x33b3  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x33b8  ldfld    int32 Microsoft.Crm.Asynchronous.JobManager::OrgDBUpdatesRunning
0x33bd  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_MaxConcurrentOrgDBUpdateJobsPerAsyncServer()
0x33c2  blt.s    loc_340A
0x33c4  ldstr    aOrgdbupdatethr_1// "[OrgDBUpdateThrottling] OrgDBUpdatesRun"...
0x33c9  ldarg.0
0x33ca  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x33cf  ldfld    int32 Microsoft.Crm.Asynchronous.JobManager::OrgDBUpdatesRunning
0x33d4  box      [mscorlib]System.Int32
0x33d9  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_MaxConcurrentOrgDBUpdateJobsPerAsyncServer()
0x33de  box      [mscorlib]System.Int32
0x33e3  call     string [mscorlib]System.String::Format(string, object, object)
0x33e8  ldstr    aSkippedAddingJ// "Skipped adding job for org {0}."
0x33ed  ldarg.2
0x33ee  box      [mscorlib]System.Guid
0x33f3  call     string [mscorlib]System.String::Format(string, object)
0x33f8  call     string [mscorlib]System.String::Concat(string, string)
0x33fd  ldc.i4.0
0x33fe  newarr   [mscorlib]System.Object
0x3403  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateThrottlingTelemetry(string messageFormat, object[] args)
0x3408  ldc.i4.1
0x3409  ret
0x340a  ldc.i4.0
0x340b  ret
```
