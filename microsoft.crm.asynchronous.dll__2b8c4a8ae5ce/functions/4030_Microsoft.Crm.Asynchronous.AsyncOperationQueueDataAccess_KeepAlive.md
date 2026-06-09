# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::KeepAlive

- ea: `0x4030`
- end: `0x40ea`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::KeepAlive`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2790`
- `0xd5a0`
- `0xd8e0`
- `0xd990`
- `0x156a0`
- `0x157c0`
- `0x15810`
- `0x171d0`

## string_xrefs

- `0x4043`: `update AsyncOperationBase WITH  (READPAST,READCOMMITTEDLOCK,UPDLOCK)\nset\n	ModifiedOn = @modifiedOn,\n	ModifiedBy = CreatedBy\nwhere \n		StateCode = @lockedState\n	and HostId = @hostId`

## pseudocode

```c

```

## disassembly

```asm
0x4030  newobj   instance void <>c__DisplayClass17_0::.ctor()
0x4035  stloc.0
0x4036  ldloc.0
0x4037  ldarg.0
0x4038  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass17_0::<>4__this
0x403d  ldarg.0
0x403e  ldsfld   string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_asyncServiceAppLock
0x4043  ldstr    aUpdateAsyncope_4// "update AsyncOperationBase WITH  (READPA"...
0x4048  call     instance string Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string applicationLockName, string query)
0x404d  stloc.1
0x404e  ldloc.0
0x404f  ldloc.1
0x4050  ldc.i4.1
0x4051  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x4056  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass17_0::keepAliveCommand
0x405b  ldloc.0
0x405c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass17_0::keepAliveCommand
0x4061  ldstr    aLockedstate// "@lockedState"
0x4066  ldc.i4.2
0x4067  box      [mscorlib]System.Int32
0x406c  ldloca.s 2
0x406e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4074  ldloc.2
0x4075  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x407a  ldloc.0
0x407b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass17_0::keepAliveCommand
0x4080  ldstr    aHostid// "@hostId"
0x4085  ldarg.0
0x4086  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x408b  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x4090  ldloca.s 2
0x4092  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4098  ldloc.2
0x4099  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x409e  ldloc.0
0x409f  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass17_0::keepAliveCommand
0x40a4  ldstr    aModifiedon// "@modifiedOn"
0x40a9  ldarg.0
0x40aa  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x40af  box      [mscorlib]System.DateTime
0x40b4  ldloca.s 2
0x40b6  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x40bc  ldloc.2
0x40bd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x40c2  ldarg.0
0x40c3  ldfld    class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_operationsFactory
0x40c8  ldstr    aSelectevents// "SelectEvents"
0x40cd  ldarg.0
0x40ce  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x40d3  ldloc.0
0x40d4  ldftn    instance void <>c__DisplayClass17_0::<KeepAlive>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x40da  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x40df  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction)
0x40e4  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x40e9  ret
```
