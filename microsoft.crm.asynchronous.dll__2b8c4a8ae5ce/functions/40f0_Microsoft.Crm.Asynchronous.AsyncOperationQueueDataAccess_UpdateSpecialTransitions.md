# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::UpdateSpecialTransitions

- ea: `0x40f0`
- end: `0x4236`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::UpdateSpecialTransitions`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2730`
- `0x2790`
- `0xa830`
- `0xd5a0`
- `0xd8e0`
- `0xe180`
- `0x156a0`
- `0x157c0`
- `0x15810`
- `0x17220`

## string_xrefs

- `0x4103`: `select\n					AsyncOperationId,\n					StatusCode\n				from AsyncOperationBase WITH (READPAST,READCOMMITTEDLOCK,UPDLOCK)\n				where\n						StateCode = @lockedState\n					and HostId = @hostId\n					and StatusCode in (@pausingStatus, @cancelingStatus)`

## pseudocode

```c

```

## disassembly

```asm
0x40f0  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x40f5  stloc.0
0x40f6  ldloc.0
0x40f7  ldarg.0
0x40f8  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass18_0::<>4__this
0x40fd  ldarg.0
0x40fe  ldsfld   string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_asyncServiceAppLock
0x4103  ldstr    aSelectAsyncope_0// "select\r\n\t\t\t\t\tAsyncOperationId,\r"...
0x4108  call     instance string Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string applicationLockName, string query)
0x410d  stloc.1
0x410e  ldloc.0
0x410f  ldloc.1
0x4110  ldc.i4.1
0x4111  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x4116  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass18_0::selectCommand
0x411b  ldloc.0
0x411c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass18_0::selectCommand
0x4121  ldstr    aLockedstate// "@lockedState"
0x4126  ldc.i4.2
0x4127  box      [mscorlib]System.Int32
0x412c  ldloca.s 3
0x412e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4134  ldloc.3
0x4135  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x413a  ldloc.0
0x413b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass18_0::selectCommand
0x4140  ldstr    aHostid// "@hostId"
0x4145  ldarg.0
0x4146  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x414b  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x4150  ldloca.s 3
0x4152  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4158  ldloc.3
0x4159  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x415e  ldloc.0
0x415f  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass18_0::selectCommand
0x4164  ldstr    aPausingstatus// "@pausingStatus"
0x4169  ldc.i4.s 0x15
0x416b  box      [mscorlib]System.Int32
0x4170  ldloca.s 3
0x4172  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4178  ldloc.3
0x4179  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x417e  ldloc.0
0x417f  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass18_0::selectCommand
0x4184  ldstr    aCancelingstatu// "@cancelingStatus"
0x4189  ldc.i4.s 0x16
0x418b  box      [mscorlib]System.Int32
0x4190  ldloca.s 3
0x4192  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4198  ldloc.3
0x4199  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x419e  ldloc.0
0x419f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest>::.ctor()
0x41a4  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest> <>c__DisplayClass18_0::specialTransitions
0x41a9  ldarg.0
0x41aa  ldfld    class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_operationsFactory
0x41af  ldstr    aSelectevents// "SelectEvents"
0x41b4  ldarg.0
0x41b5  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x41ba  ldloc.0
0x41bb  ldftn    instance void <>c__DisplayClass18_0::<UpdateSpecialTransitions>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x41c1  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x41c6  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction)
0x41cb  stloc.2
0x41cc  ldarg.0
0x41cd  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x41d2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x41d7  ldc.i4.s 0x15
0x41d9  ldstr    a01Selected2Ope// "{0}-{1}: Selected {2} operations that r"...
0x41de  ldc.i4.3
0x41df  newarr   [mscorlib]System.Object
0x41e4  dup
0x41e5  ldc.i4.0
0x41e6  ldarg.0
0x41e7  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x41ec  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x41f1  stelem.ref
0x41f2  dup
0x41f3  ldc.i4.1
0x41f4  ldarg.0
0x41f5  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x41fa  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x41ff  stelem.ref
0x4200  dup
0x4201  ldc.i4.2
0x4202  ldloc.0
0x4203  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest> <>c__DisplayClass18_0::specialTransitions
0x4208  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest>::get_Count()
0x420d  box      [mscorlib]System.Int32
0x4212  stelem.ref
0x4213  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4218  ldloc.2
0x4219  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x421e  ldarg.0
0x421f  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x4224  ldarg.0
0x4225  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x422a  ldloc.0
0x422b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest> <>c__DisplayClass18_0::specialTransitions
0x4230  callvirt instance void Microsoft.Crm.Asynchronous.QueueManager::SetSpecialTransitions(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest> specialTransitions)
0x4235  ret
```
