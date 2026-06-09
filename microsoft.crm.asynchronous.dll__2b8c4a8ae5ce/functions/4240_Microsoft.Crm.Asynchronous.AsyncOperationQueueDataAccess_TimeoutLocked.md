# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::TimeoutLocked

- ea: `0x4240`
- end: `0x440a`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::TimeoutLocked`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4bd0`
- `0x5a10`
- `0xd5a0`
- `0xd8e0`
- `0xd990`
- `0x156a0`
- `0x157c0`
- `0x15810`
- `0x172c0`

## string_xrefs

- `0x4271`: `@readyState`
- `0x42ce`: `@completedState`
- `0x4253`: `update AsyncOperationBase WITH  (READPAST,READCOMMITTEDLOCK,UPDLOCK)\nset\nStateCode =\n	case StatusCode\n		when @cancelingStatus then @completedState\n		when @pausingStatus then @suspendedState\n		else @readyState\n	end,\nStatusCode = \n	case StatusCode\n		when @cancelingStatus then @canceledStatus\n		when @pausingStatus then @pausedStatus\n		else @waitingStatus\n	end,\nModifiedOn = @utcNow,\nModifiedBy = CreatedBy\nwhere\nModifiedOn < @modifiedOn\nand StateCode = @lockedState`

## pseudocode

```c

```

## disassembly

```asm
0x4240  newobj   instance void <>c__DisplayClass19_0::.ctor()
0x4245  stloc.0
0x4246  ldloc.0
0x4247  ldarg.0
0x4248  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass19_0::<>4__this
0x424d  ldarg.0
0x424e  ldsfld   string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_asyncServiceAppLock
0x4253  ldstr    aUpdateAsyncope_5// "update AsyncOperationBase WITH  (READPA"...
0x4258  call     instance string Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string applicationLockName, string query)
0x425d  stloc.1
0x425e  ldloc.0
0x425f  ldloc.1
0x4260  ldc.i4.1
0x4261  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x4266  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x426b  ldloc.0
0x426c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x4271  ldstr    aReadystate// "@readyState"
0x4276  ldc.i4.0
0x4277  box      [mscorlib]System.Int32
0x427c  ldloca.s 2
0x427e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4284  ldloc.2
0x4285  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x428a  ldloc.0
0x428b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x4290  ldstr    aSuspendedstate// "@suspendedState"
0x4295  ldc.i4.1
0x4296  box      [mscorlib]System.Int32
0x429b  ldloca.s 2
0x429d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x42a3  ldloc.2
0x42a4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x42a9  ldloc.0
0x42aa  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x42af  ldstr    aLockedstate// "@lockedState"
0x42b4  ldc.i4.2
0x42b5  box      [mscorlib]System.Int32
0x42ba  ldloca.s 2
0x42bc  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x42c2  ldloc.2
0x42c3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x42c8  ldloc.0
0x42c9  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x42ce  ldstr    aCompletedstate// "@completedState"
0x42d3  ldc.i4.3
0x42d4  box      [mscorlib]System.Int32
0x42d9  ldloca.s 2
0x42db  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x42e1  ldloc.2
0x42e2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x42e7  ldloc.0
0x42e8  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x42ed  ldstr    aWaitingstatus// "@waitingStatus"
0x42f2  ldc.i4.0
0x42f3  box      [mscorlib]System.Int32
0x42f8  ldloca.s 2
0x42fa  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4300  ldloc.2
0x4301  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x4306  ldloc.0
0x4307  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x430c  ldstr    aPausingstatus// "@pausingStatus"
0x4311  ldc.i4.s 0x15
0x4313  box      [mscorlib]System.Int32
0x4318  ldloca.s 2
0x431a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4320  ldloc.2
0x4321  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x4326  ldloc.0
0x4327  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x432c  ldstr    aCancelingstatu// "@cancelingStatus"
0x4331  ldc.i4.s 0x16
0x4333  box      [mscorlib]System.Int32
0x4338  ldloca.s 2
0x433a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4340  ldloc.2
0x4341  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x4346  ldloc.0
0x4347  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x434c  ldstr    aPausedstatus// "@pausedStatus"
0x4351  ldc.i4.s 0xA
0x4353  box      [mscorlib]System.Int32
0x4358  ldloca.s 2
0x435a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4360  ldloc.2
0x4361  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x4366  ldloc.0
0x4367  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x436c  ldstr    aCanceledstatus// "@canceledStatus"
0x4371  ldc.i4.s 0x20
0x4373  box      [mscorlib]System.Int32
0x4378  ldloca.s 2
0x437a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4380  ldloc.2
0x4381  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x4386  ldloc.0
0x4387  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x438c  ldstr    aModifiedon// "@modifiedOn"
0x4391  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4396  ldarg.0
0x4397  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x439c  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x43a1  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_TimeUntilLockExpires()
0x43a6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x43ab  box      [mscorlib]System.DateTime
0x43b0  ldloca.s 2
0x43b2  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x43b8  ldloc.2
0x43b9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x43be  ldloc.0
0x43bf  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass19_0::timeoutLockedCommand
0x43c4  ldstr    aUtcnow// "@utcNow"
0x43c9  ldarg.0
0x43ca  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x43cf  box      [mscorlib]System.DateTime
0x43d4  ldloca.s 2
0x43d6  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x43dc  ldloc.2
0x43dd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x43e2  ldarg.0
0x43e3  ldfld    class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_operationsFactory
0x43e8  ldstr    aSelectevents// "SelectEvents"
0x43ed  ldarg.0
0x43ee  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x43f3  ldloc.0
0x43f4  ldftn    instance void <>c__DisplayClass19_0::<TimeoutLocked>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x43fa  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x43ff  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction)
0x4404  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x4409  ret
```
