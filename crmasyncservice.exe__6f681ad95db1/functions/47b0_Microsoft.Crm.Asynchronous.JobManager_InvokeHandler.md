# Microsoft.Crm.Asynchronous.JobManager::InvokeHandler

- ea: `0x47b0`
- end: `0x483f`
- name: `Microsoft.Crm.Asynchronous.JobManager::InvokeHandler`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x9d0`
- `0xa10`
- `0x3f40`
- `0x4320`
- `0x4340`
- `0x4480`
- `0x47b0`
- `0x4840`

## string_xrefs

- `0x47e0`: `[DBUPDATES] DB Update job for org {0} completed.`
- `0x47fe`: `[OrgDBUpdateThrottling] Decremented orgDBUpdatesRunning to {0} after completing job for org {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x47b0  ldarg.1
0x47b1  castclass Microsoft.Crm.Asynchronous.AsyncJob
0x47b6  stloc.0
0x47b7  ldarg.0
0x47b8  ldloc.0
0x47b9  call     instance void Microsoft.Crm.Asynchronous.JobManager::ProcessAsyncJob(class Microsoft.Crm.Asynchronous.AsyncJob asyncJob)
0x47be  ldarg.0
0x47bf  ldflda   int32 Microsoft.Crm.Asynchronous.JobManager::_jobsFinished
0x47c4  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x47c9  pop
0x47ca  ldloc.0
0x47cb  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncJob::get_OperationType()
0x47d0  ldc.i4.s 0x2C
0x47d2  bne.un.s loc_482A
0x47d4  ldarg.0
0x47d5  ldflda   int32 Microsoft.Crm.Asynchronous.JobManager::OrgDBUpdatesRunning
0x47da  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x47df  pop
0x47e0  ldstr    aDbupdatesDbUpd_0// "[DBUPDATES] DB Update job for org {0} c"...
0x47e5  ldc.i4.1
0x47e6  newarr   [mscorlib]System.Object
0x47eb  dup
0x47ec  ldc.i4.0
0x47ed  ldloc.0
0x47ee  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x47f3  box      [mscorlib]System.Guid
0x47f8  stelem.ref
0x47f9  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x47fe  ldstr    aOrgdbupdatethr_5// "[OrgDBUpdateThrottling] Decremented org"...
0x4803  ldc.i4.2
0x4804  newarr   [mscorlib]System.Object
0x4809  dup
0x480a  ldc.i4.0
0x480b  ldarg.0
0x480c  ldfld    int32 Microsoft.Crm.Asynchronous.JobManager::OrgDBUpdatesRunning
0x4811  box      [mscorlib]System.Int32
0x4816  stelem.ref
0x4817  dup
0x4818  ldc.i4.1
0x4819  ldloc.0
0x481a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x481f  box      [mscorlib]System.Guid
0x4824  stelem.ref
0x4825  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateThrottlingTelemetry(string messageFormat, object[] args)
0x482a  ldarg.0
0x482b  ldfld    int32 Microsoft.Crm.Asynchronous.JobManager::_jobsFinished
0x4830  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_ModuloForNewJobRetrieval()
0x4835  rem
0x4836  brtrue.s loc_483E
0x4838  ldarg.0
0x4839  call     instance void Microsoft.Crm.Asynchronous.JobManager::RetrieveAndQueueJobs()
0x483e  ret
```
