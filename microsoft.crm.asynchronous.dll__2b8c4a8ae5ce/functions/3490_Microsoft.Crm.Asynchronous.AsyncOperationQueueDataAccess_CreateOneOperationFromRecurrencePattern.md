# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::CreateOneOperationFromRecurrencePattern

- ea: `0x3490`
- end: `0x36af`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::CreateOneOperationFromRecurrencePattern`
- size: `543`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2730`
- `0x2790`
- `0x2e40`
- `0x5f30`
- `0x5f40`
- `0xd5a0`
- `0xd8e0`
- `0xd990`
- `0x156a0`
- `0x157c0`
- `0x15810`
- `0x16fe0`

## string_xrefs

- `0x34e5`: `@readyState`
- `0x34a3`: `update AsyncOperationBase\nset StateCode = @readyState, StatusCode = @waitingStatus, RetryCount = 0, PostponeUntil = @postponeUntil\nwhere CorrelationId = @correlationId\n	and OperationType = @operationType\n	and Statecode = @waitingState\n	and RecurrencePattern is NULL\n;\nif not exists (select * \n	from AsyncOperationBase \n	where CorrelationId = @correlationId\n		and OperationType = @operationType\n		and StateCode != @completedState\n		and RecurrencePattern is NULL\n	) 	\n	begin`
- `0x358f`: `@completedState`
- `0x3662`: `{0}-{1}: Operation {2} has been created as state {3}, status {4}.`

## pseudocode

```c

```

## disassembly

```asm
0x3490  newobj   instance void <>c__DisplayClass7_0::.ctor()
0x3495  stloc.0
0x3496  ldloc.0
0x3497  ldarg.0
0x3498  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass7_0::<>4__this
0x349d  ldarg.0
0x349e  ldsfld   string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_asyncServiceAppLock
0x34a3  ldstr    aUpdateAsyncope_0// "update AsyncOperationBase\r\nset StateC"...
0x34a8  call     instance string Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string applicationLockName, string query)
0x34ad  stloc.1
0x34ae  ldloc.0
0x34af  ldloc.1
0x34b0  ldc.i4.1
0x34b1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x34b6  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x34bb  ldloc.0
0x34bc  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x34c1  ldstr    aId// "@id"
0x34c6  ldarg.1
0x34c7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x34cc  box      [mscorlib]System.Guid
0x34d1  ldloca.s 2
0x34d3  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x34d9  ldloc.2
0x34da  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x34df  ldloc.0
0x34e0  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x34e5  ldstr    aReadystate// "@readyState"
0x34ea  ldc.i4.0
0x34eb  box      [mscorlib]System.Int32
0x34f0  ldloca.s 2
0x34f2  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x34f8  ldloc.2
0x34f9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x34fe  ldloc.0
0x34ff  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x3504  ldstr    aWaitingstatus// "@waitingStatus"
0x3509  ldc.i4.0
0x350a  box      [mscorlib]System.Int32
0x350f  ldloca.s 2
0x3511  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3517  ldloc.2
0x3518  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x351d  ldloc.0
0x351e  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x3523  ldstr    aCorrelationid// "@correlationId"
0x3528  ldarg.1
0x3529  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Asynchronous.AsyncEvent::get_CorrelationToken()
0x352e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::get_CorrelationId()
0x3533  box      [mscorlib]System.Guid
0x3538  ldloca.s 2
0x353a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3540  ldloc.2
0x3541  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3546  ldloc.0
0x3547  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x354c  ldstr    aOperationtype// "@operationType"
0x3551  ldarg.1
0x3552  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x3557  box      [mscorlib]System.Int32
0x355c  ldloca.s 2
0x355e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3564  ldloc.2
0x3565  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x356a  ldloc.0
0x356b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x3570  ldstr    aWaitingstate// "@waitingState"
0x3575  ldc.i4.1
0x3576  box      [mscorlib]System.Int32
0x357b  ldloca.s 2
0x357d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3583  ldloc.2
0x3584  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3589  ldloc.0
0x358a  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x358f  ldstr    aCompletedstate// "@completedState"
0x3594  ldc.i4.3
0x3595  box      [mscorlib]System.Int32
0x359a  ldloca.s 2
0x359c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x35a2  ldloc.2
0x35a3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x35a8  ldloc.0
0x35a9  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x35ae  ldstr    aPostponeuntil// "@postponeUntil"
0x35b3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x35b8  box      [mscorlib]System.DateTime
0x35bd  ldloca.s 2
0x35bf  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x35c5  ldloc.2
0x35c6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x35cb  ldloc.0
0x35cc  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x35d1  ldstr    aModifiedon// "@modifiedOn"
0x35d6  ldarg.0
0x35d7  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x35dc  box      [mscorlib]System.DateTime
0x35e1  ldloca.s 2
0x35e3  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x35e9  ldloc.2
0x35ea  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x35ef  ldloc.0
0x35f0  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x35f5  ldstr    aSuspendedstate// "@suspendedState"
0x35fa  ldc.i4.1
0x35fb  box      [mscorlib]System.Int32
0x3600  ldloca.s 2
0x3602  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3608  ldloc.2
0x3609  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x360e  ldloc.0
0x360f  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::seedCommand
0x3614  ldstr    aPausedstatus// "@pausedStatus"
0x3619  ldc.i4.s 0xA
0x361b  box      [mscorlib]System.Int32
0x3620  ldloca.s 2
0x3622  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3628  ldloc.2
0x3629  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x362e  ldarg.0
0x362f  ldfld    class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_operationsFactory
0x3634  ldstr    aSelectevents// "SelectEvents"
0x3639  ldarg.0
0x363a  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x363f  ldloc.0
0x3640  ldftn    instance void <>c__DisplayClass7_0::<CreateOneOperationFromRecurrencePattern>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x3646  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x364b  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction)
0x3650  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x3655  ldarg.0
0x3656  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x365b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x3660  ldc.i4.s 0x15
0x3662  ldstr    a01Operation2Ha// "{0}-{1}: Operation {2} has been created"...
0x3667  ldc.i4.5
0x3668  newarr   [mscorlib]System.Object
0x366d  dup
0x366e  ldc.i4.0
0x366f  ldarg.0
0x3670  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x3675  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x367a  stelem.ref
0x367b  dup
0x367c  ldc.i4.1
0x367d  ldarg.0
0x367e  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x3683  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x3688  stelem.ref
0x3689  dup
0x368a  ldc.i4.2
0x368b  ldarg.1
0x368c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x3691  box      [mscorlib]System.Guid
0x3696  stelem.ref
0x3697  dup
0x3698  ldc.i4.3
0x3699  ldc.i4.0
0x369a  box      [mscorlib]System.Int32
0x369f  stelem.ref
0x36a0  dup
0x36a1  ldc.i4.4
0x36a2  ldc.i4.0
0x36a3  box      [mscorlib]System.Int32
0x36a8  stelem.ref
0x36a9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x36ae  ret
```
