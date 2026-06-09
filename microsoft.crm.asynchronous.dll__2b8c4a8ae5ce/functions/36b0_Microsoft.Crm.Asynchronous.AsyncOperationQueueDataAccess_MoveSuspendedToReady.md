# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::MoveSuspendedToReady

- ea: `0x36b0`
- end: `0x37d1`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::MoveSuspendedToReady`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0xb370`
- `0xd5a0`
- `0xd8e0`
- `0xd990`
- `0x13620`
- `0x156a0`
- `0x157c0`
- `0x15810`
- `0x17030`

## string_xrefs

- `0x36e1`: `@readyState`
- `0x36c3`: `With TopSuspendedAsyncOperations(AsyncOperationId)\nAS\n(\nSelect Top(@numberOfSuspendedOperationsToSelect) AsyncOperationId\nfrom AsyncOperationBase o1\nwhere\n	StateCode = @suspendedState\nand	((PostponeUntil is NULL) or (PostponeUntil <= @modifiedOn))\nand ((DependencyToken is NULL) or (not exists (\n	select AsyncOperationId\n	from AsyncOperationBase o2\n	where\n		o2.Sequence < o1.Sequence\n	and	o2.DependencyToken = o1.DependencyToken\n	and o2.RecurrencePattern is null\n	and o2`

## pseudocode

```c

```

## disassembly

```asm
0x36b0  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x36b5  stloc.0
0x36b6  ldloc.0
0x36b7  ldarg.0
0x36b8  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass8_0::<>4__this
0x36bd  ldarg.0
0x36be  ldsfld   string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_asyncServiceAppLock
0x36c3  ldstr    aWithTopsuspend// "With TopSuspendedAsyncOperations(AsyncO"...
0x36c8  call     instance string Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string applicationLockName, string query)
0x36cd  stloc.1
0x36ce  ldloc.0
0x36cf  ldloc.1
0x36d0  ldc.i4.1
0x36d1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x36d6  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass8_0::moveCommand
0x36db  ldloc.0
0x36dc  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass8_0::moveCommand
0x36e1  ldstr    aReadystate// "@readyState"
0x36e6  ldc.i4.0
0x36e7  box      [mscorlib]System.Int32
0x36ec  ldloca.s 2
0x36ee  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x36f4  ldloc.2
0x36f5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x36fa  ldloc.0
0x36fb  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass8_0::moveCommand
0x3700  ldstr    aLockedstate// "@lockedState"
0x3705  ldc.i4.2
0x3706  box      [mscorlib]System.Int32
0x370b  ldloca.s 2
0x370d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3713  ldloc.2
0x3714  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3719  ldloc.0
0x371a  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass8_0::moveCommand
0x371f  ldstr    aSuspendedstate// "@suspendedState"
0x3724  ldc.i4.1
0x3725  box      [mscorlib]System.Int32
0x372a  ldloca.s 2
0x372c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3732  ldloc.2
0x3733  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3738  ldloc.0
0x3739  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass8_0::moveCommand
0x373e  ldstr    aWaitingstatus// "@waitingStatus"
0x3743  ldc.i4.0
0x3744  box      [mscorlib]System.Int32
0x3749  ldloca.s 2
0x374b  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3751  ldloc.2
0x3752  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3757  ldloc.0
0x3758  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass8_0::moveCommand
0x375d  ldstr    aNumberofsuspen// "@numberOfSuspendedOperationsToSelect"
0x3762  ldarg.0
0x3763  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x3768  callvirt instance class Microsoft.Crm.Asynchronous.IQueueConfiguration Microsoft.Crm.Asynchronous.QueueManager::get_Configuration()
0x376d  callvirt instance int32 Microsoft.Crm.Asynchronous.IQueueConfiguration::get_ItemsInMemoryHigh()
0x3772  box      [mscorlib]System.Int32
0x3777  ldloca.s 2
0x3779  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x377f  ldloc.2
0x3780  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3785  ldloc.0
0x3786  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass8_0::moveCommand
0x378b  ldstr    aModifiedon// "@modifiedOn"
0x3790  ldarg.0
0x3791  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x3796  box      [mscorlib]System.DateTime
0x379b  ldloca.s 2
0x379d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x37a3  ldloc.2
0x37a4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x37a9  ldarg.0
0x37aa  ldfld    class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_operationsFactory
0x37af  ldstr    aSelectevents// "SelectEvents"
0x37b4  ldarg.0
0x37b5  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x37ba  ldloc.0
0x37bb  ldftn    instance void <>c__DisplayClass8_0::<MoveSuspendedToReady>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x37c1  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x37c6  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction)
0x37cb  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x37d0  ret
```
