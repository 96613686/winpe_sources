# Microsoft.Crm.Asynchronous.JobManager::RetrieveAndQueueJobs

- ea: `0x4480`
- end: `0x459b`
- name: `Microsoft.Crm.Asynchronous.JobManager::RetrieveAndQueueJobs`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x4470`
- `0x47b0`

## callees

- `0x2100`
- `0x2180`
- `0x3f00`
- `0x4340`
- `0x4480`
- `0x4770`
- `0x4a60`

## string_xrefs

- `0x44d9`: `[JOBPROCESSING] Completed RetrieveAndQueueJobs for cycle time {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x4480  ldarg.0
0x4481  ldflda   int32 Microsoft.Crm.Asynchronous.JobManager::_isRetrievingJobs
0x4486  ldc.i4.1
0x4487  ldc.i4.0
0x4488  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0x448d  brtrue   loc_459A
0x4492  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_JobsToProcessAtOnce()
0x4497  stloc.0
0x4498  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x449d  stloc.1
0x449e  ldarg.0
0x449f  ldfld    class Microsoft.Crm.Asynchronous.IJobDataAccessFactory Microsoft.Crm.Asynchronous.JobManager::_dataAccessFactory
0x44a4  ldarg.0
0x44a5  callvirt instance class Microsoft.Crm.Asynchronous.IJobDataAccess Microsoft.Crm.Asynchronous.IJobDataAccessFactory::CreateInstance(class Microsoft.Crm.Asynchronous.JobManager jobManager)
0x44aa  stloc.2
0x44ab  ldstr    aJobprocessingS// "[JOBPROCESSING] Starting RetrieveAndQue"...
0x44b0  ldc.i4.1
0x44b1  newarr   [mscorlib]System.Object
0x44b6  dup
0x44b7  ldc.i4.0
0x44b8  ldloc.1
0x44b9  box      [mscorlib]System.DateTime
0x44be  stelem.ref
0x44bf  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x44c4  br       loc_4578
0x44c9  ldloc.2
0x44ca  ldloc.1
0x44cb  ldloc.0
0x44cc  callvirt instance class Microsoft.Crm.Asynchronous.AsyncJob[] Microsoft.Crm.Asynchronous.IJobDataAccess::SelectJobs(valuetype [mscorlib]System.DateTime startCycleTime, int32 maxJobsToRetrieve)
0x44d1  stloc.3
0x44d2  ldloc.3
0x44d3  brfalse.s loc_44D9
0x44d5  ldloc.3
0x44d6  ldlen
0x44d7  brtrue.s loc_44F7
0x44d9  ldstr    aJobprocessingC// "[JOBPROCESSING] Completed RetrieveAndQu"...
0x44de  ldc.i4.1
0x44df  newarr   [mscorlib]System.Object
0x44e4  dup
0x44e5  ldc.i4.0
0x44e6  ldloc.1
0x44e7  box      [mscorlib]System.DateTime
0x44ec  stelem.ref
0x44ed  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x44f2  leave    loc_459A
0x44f7  ldloc.3
0x44f8  stloc.s  4
0x44fa  ldc.i4.0
0x44fb  stloc.s  5
0x44fd  br.s     loc_4570
0x44ff  ldloc.s  4
0x4501  ldloc.s  5
0x4503  ldelem.ref
0x4504  stloc.s  6
0x4506  ldarg.0
0x4507  ldloc.s  6
0x4509  call     instance void Microsoft.Crm.Asynchronous.JobManager::JobHandler(class Microsoft.Crm.Asynchronous.AsyncJob asyncJob)
0x450e  leave.s  loc_456A
0x4510  stloc.s  7
0x4512  ldloc.s  7
0x4514  isinst   [mscorlib]System.NullReferenceException
0x4519  ldloc.s  7
0x451b  isinst   [mscorlib]System.ArgumentNullException
0x4520  stloc.s  8
0x4522  ldloc.s  7
0x4524  isinst   [mscorlib]System.InvalidOperationException
0x4529  stloc.s  9
0x452b  ldloc.s  7
0x452d  isinst   [System.Data]System.Data.SqlClient.SqlException
0x4532  stloc.s  0xA
0x4534  brtrue.s loc_4568
0x4536  ldloc.s  8
0x4538  brtrue.s loc_4568
0x453a  ldloc.s  9
0x453c  brtrue.s loc_4568
0x453e  ldloc.s  0xA
0x4540  brtrue.s loc_4568
0x4542  ldarg.0
0x4543  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_EventLog()
0x4548  ldc.i4.1
0x4549  ldc.i4   0xC0004410
0x454e  conv.u8
0x454f  ldc.i4.2
0x4550  newarr   [mscorlib]System.Object
0x4555  dup
0x4556  ldc.i4.0
0x4557  ldarg.0
0x4558  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x455d  stelem.ref
0x455e  dup
0x455f  ldc.i4.1
0x4560  ldloc.s  7
0x4562  stelem.ref
0x4563  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventLogHelper::LogEvent(class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x4568  leave.s  loc_456A
0x456a  ldloc.s  5
0x456c  ldc.i4.1
0x456d  add
0x456e  stloc.s  5
0x4570  ldloc.s  5
0x4572  ldloc.s  4
0x4574  ldlen
0x4575  conv.i4
0x4576  blt.s    loc_44FF
0x4578  ldarg.0
0x4579  call     instance bool [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_ShuttingDown()
0x457e  brtrue.s loc_458B
0x4580  ldarg.0
0x4581  call     instance bool Microsoft.Crm.Asynchronous.JobManager::get_IsScaleGroupEnabled()
0x4586  brtrue   loc_44C9
0x458b  leave.s  loc_459A
0x458d  ldarg.0
0x458e  ldflda   int32 Microsoft.Crm.Asynchronous.JobManager::_isRetrievingJobs
0x4593  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x4598  pop
0x4599  endfinally
0x459a  ret
```
