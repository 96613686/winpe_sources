# Microsoft.Crm.Asynchronous.JobManager::EndAsynchronousEventProcessing

- ea: `0x4360`
- end: `0x4468`
- name: `Microsoft.Crm.Asynchronous.JobManager::EndAsynchronousEventProcessing`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4840`

## callees

- `0x9d0`
- `0xa10`
- `0xac0`
- `0xae0`
- `0x2140`
- `0x2180`
- `0x4340`
- `0x4360`

## string_xrefs

- `0x4428`: `[JOBCOMPLETED] Updated NextRunTime of job {0} for org {1} to {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x4360  ldarg.1
0x4361  ldstr    aAsyncevent// "asyncEvent"
0x4366  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x436b  ldarg.2
0x436c  ldstr    aResult// "result"
0x4371  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4376  ldarg.1
0x4377  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::NextOccurrence(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent)
0x437c  stloc.0
0x437d  ldarg.2
0x437e  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult
0x4383  stloc.1
0x4384  ldloc.1
0x4385  brfalse.s loc_43A5
0x4387  ldloc.1
0x4388  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult::get_RecurrencePattern()
0x438d  dup
0x438e  brtrue.s loc_4397
0x4390  pop
0x4391  ldarg.1
0x4392  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RecurrencePattern()
0x4397  ldloc.1
0x4398  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult::get_RecurrenceStartTime()
0x439d  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncOperationControlService::NextOccurrence(string, valuetype [mscorlib]System.DateTime)
0x43a2  stloc.0
0x43a3  br.s     loc_43D5
0x43a5  ldarg.2
0x43a6  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRetryResult
0x43ab  brfalse.s loc_43D5
0x43ad  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x43b2  stloc.s  5
0x43b4  ldloca.s 5
0x43b6  ldarg.0
0x43b7  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::_config
0x43bc  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration::get_OrgDatabaseJobMaxExecutionTime()
0x43c1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x43c6  stloc.s  4
0x43c8  ldloc.s  4
0x43ca  ldloc.0
0x43cb  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x43d0  brfalse.s loc_43D5
0x43d2  ldloc.s  4
0x43d4  stloc.0
0x43d5  ldarg.0
0x43d6  ldfld    class Microsoft.Crm.Asynchronous.IJobDataAccessFactory Microsoft.Crm.Asynchronous.JobManager::_dataAccessFactory
0x43db  ldarg.0
0x43dc  callvirt instance class Microsoft.Crm.Asynchronous.IJobDataAccess Microsoft.Crm.Asynchronous.IJobDataAccessFactory::CreateInstance(class Microsoft.Crm.Asynchronous.JobManager jobManager)
0x43e1  stloc.2
0x43e2  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::.ctor()
0x43e7  dup
0x43e8  ldarg.1
0x43e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x43ee  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_EventId(valuetype [mscorlib]System.Guid)
0x43f3  dup
0x43f4  ldc.i4.0
0x43f5  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_NewState(int32)
0x43fa  dup
0x43fb  ldc.i4.0
0x43fc  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_NewStatus(int32)
0x4401  dup
0x4402  ldloc.0
0x4403  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_NextOccurrence(valuetype [mscorlib]System.DateTime)
0x4408  dup
0x4409  ldarg.2
0x440a  call     int32 Microsoft.Crm.Asynchronous.AsyncJob::AsyncJobResultFromAsyncHandlerResult(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult result)
0x440f  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_ErrorCode(int32)
0x4414  dup
0x4415  ldarg.2
0x4416  call     string Microsoft.Crm.Asynchronous.AsyncJob::AsyncJobMessageFromAsyncHandlerResult(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult result)
0x441b  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_ErrorMessage(string)
0x4420  dup
0x4421  ldarg.3
0x4422  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::set_ExecutionTime(float64)
0x4427  stloc.3
0x4428  ldstr    aJobcompletedUp// "[JOBCOMPLETED] Updated NextRunTime of j"...
0x442d  ldc.i4.3
0x442e  newarr   [mscorlib]System.Object
0x4433  dup
0x4434  ldc.i4.0
0x4435  ldarg.s  4
0x4437  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncJob::get_OperationType()
0x443c  box      [mscorlib]System.Int32
0x4441  stelem.ref
0x4442  dup
0x4443  ldc.i4.1
0x4444  ldarg.s  4
0x4446  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x444b  box      [mscorlib]System.Guid
0x4450  stelem.ref
0x4451  dup
0x4452  ldc.i4.2
0x4453  ldloc.0
0x4454  box      [mscorlib]System.DateTime
0x4459  stelem.ref
0x445a  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x445f  ldloc.2
0x4460  ldloc.1
0x4461  ldloc.3
0x4462  callvirt instance void Microsoft.Crm.Asynchronous.IJobDataAccess::UpdateStateAndStatus(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult reschedule, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState newState)
0x4467  ret
```
