# Microsoft.Crm.Asynchronous.JobManager::OrgDatabaseJobTimeoutTimerEvent

- ea: `0x45d0`
- end: `0x46e2`
- name: `Microsoft.Crm.Asynchronous.JobManager::OrgDatabaseJobTimeoutTimerEvent`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4aa0`

## callees

- `0x9d0`
- `0xa10`
- `0xa50`
- `0x2120`
- `0x2130`
- `0x2140`
- `0x2180`
- `0x4340`
- `0x45d0`
- `0x4a60`

## string_xrefs

- `0x468f`: `[JOBTIMEOUT] Updated NextRunTime of job {0} for org {1} to {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x45d0  ldarg.0
0x45d1  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::_config
0x45d6  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration::get_OrgDatabaseJobMaxExecutionTime()
0x45db  stloc.0
0x45dc  ldc.r8   4.0
0x45e5  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromHours(float64)
0x45ea  stloc.1
0x45eb  ldarg.0
0x45ec  ldfld    class Microsoft.Crm.Asynchronous.IJobDataAccessFactory Microsoft.Crm.Asynchronous.JobManager::_dataAccessFactory
0x45f1  ldarg.0
0x45f2  callvirt instance class Microsoft.Crm.Asynchronous.IJobDataAccess Microsoft.Crm.Asynchronous.IJobDataAccessFactory::CreateInstance(class Microsoft.Crm.Asynchronous.JobManager jobManager)
0x45f7  stloc.2
0x45f8  br       loc_46CE
0x45fd  ldloc.2
0x45fe  ldloc.0
0x45ff  ldc.i4.s 0x2C
0x4601  callvirt instance class Microsoft.Crm.Asynchronous.AsyncJob Microsoft.Crm.Asynchronous.IJobDataAccess::SelectTimedOutJobExcludingType(valuetype [mscorlib]System.TimeSpan jobMaxExecutionTime, int32 excludeJobType)
0x4606  stloc.3
0x4607  ldloc.3
0x4608  brtrue.s loc_461A
0x460a  ldloc.2
0x460b  ldloc.1
0x460c  ldc.i4.s 0x2C
0x460e  callvirt instance class Microsoft.Crm.Asynchronous.AsyncJob Microsoft.Crm.Asynchronous.IJobDataAccess::SelectTimedOutJobForType(valuetype [mscorlib]System.TimeSpan jobMaxExecutionTime, int32 jobType)
0x4613  stloc.3
0x4614  ldloc.3
0x4615  brfalse  loc_46E1
0x461a  ldloc.3
0x461b  ldc.i4.1
0x461c  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.AsyncJob::CreateAsyncEvent(class Microsoft.Crm.Asynchronous.AsyncJob job, bool includeRecurrencePattern)
0x4621  stloc.s  4
0x4623  ldloc.3
0x4624  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncJob::get_OperationType()
0x4629  ldc.i4.s 0x1A
0x462b  bne.un.s loc_464A
0x462d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4632  stloc.s  7
0x4634  ldloca.s 7
0x4636  ldarg.0
0x4637  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::_config
0x463c  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration::get_OrgDatabaseJobMaxExecutionTime()
0x4641  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x4646  stloc.s  5
0x4648  br.s     loc_4653
0x464a  ldloc.s  4
0x464c  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::NextOccurrence(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent)
0x4651  stloc.s  5
0x4653  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::.ctor()
0x4658  dup
0x4659  ldloc.s  4
0x465b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x4660  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_EventId(valuetype [mscorlib]System.Guid)
0x4665  dup
0x4666  ldc.i4.0
0x4667  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_NewState(int32)
0x466c  dup
0x466d  ldc.i4.0
0x466e  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_NewStatus(int32)
0x4673  dup
0x4674  ldloc.s  5
0x4676  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_NextOccurrence(valuetype [mscorlib]System.DateTime)
0x467b  dup
0x467c  ldc.i4.2
0x467d  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_ErrorCode(int32)
0x4682  dup
0x4683  ldstr    aTimeout// "TimeOut"
0x4688  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_ErrorMessage(string)
0x468d  stloc.s  6
0x468f  ldstr    aJobtimeoutUpda// "[JOBTIMEOUT] Updated NextRunTime of job"...
0x4694  ldc.i4.3
0x4695  newarr   [mscorlib]System.Object
0x469a  dup
0x469b  ldc.i4.0
0x469c  ldloc.3
0x469d  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncJob::get_OperationType()
0x46a2  box      [mscorlib]System.Int32
0x46a7  stelem.ref
0x46a8  dup
0x46a9  ldc.i4.1
0x46aa  ldloc.3
0x46ab  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x46b0  box      [mscorlib]System.Guid
0x46b5  stelem.ref
0x46b6  dup
0x46b7  ldc.i4.2
0x46b8  ldloc.s  5
0x46ba  box      [mscorlib]System.DateTime
0x46bf  stelem.ref
0x46c0  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x46c5  ldloc.2
0x46c6  ldnull
0x46c7  ldloc.s  6
0x46c9  callvirt instance void Microsoft.Crm.Asynchronous.IJobDataAccess::UpdateStateAndStatus(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult reschedule, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState newState)
0x46ce  ldarg.0
0x46cf  call     instance bool [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_ShuttingDown()
0x46d4  brtrue.s loc_46E1
0x46d6  ldarg.0
0x46d7  call     instance bool Microsoft.Crm.Asynchronous.JobManager::get_IsScaleGroupEnabled()
0x46dc  brtrue   loc_45FD
0x46e1  ret
```
