# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::ReturnLockedToReady

- ea: `0x3cc0`
- end: `0x3db8`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::ReturnLockedToReady`
- size: `248`
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
- `0x170d0`

## string_xrefs

- `0x3cf1`: `@readyState`
- `0x3cd3`: `update AsyncOperationBase\nset\n	StateCode = @readyState,\n	StatusCode = @waitingStatus,\n	ModifiedOn = @modifiedOn,\n	ModifiedBy = CreatedBy\nwhere\n		StateCode = @lockedState\n	and HostId = @hostId`

## pseudocode

```c

```

## disassembly

```asm
0x3cc0  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x3cc5  stloc.0
0x3cc6  ldloc.0
0x3cc7  ldarg.0
0x3cc8  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass14_0::<>4__this
0x3ccd  ldarg.0
0x3cce  ldsfld   string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_asyncServiceAppLock
0x3cd3  ldstr    aUpdateAsyncope_2// "update AsyncOperationBase\r\nset\r\n\tS"...
0x3cd8  call     instance string Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string applicationLockName, string query)
0x3cdd  stloc.1
0x3cde  ldloc.0
0x3cdf  ldloc.1
0x3ce0  ldc.i4.1
0x3ce1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x3ce6  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass14_0::unlockCommand
0x3ceb  ldloc.0
0x3cec  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass14_0::unlockCommand
0x3cf1  ldstr    aReadystate// "@readyState"
0x3cf6  ldc.i4.0
0x3cf7  box      [mscorlib]System.Int32
0x3cfc  ldloca.s 2
0x3cfe  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3d04  ldloc.2
0x3d05  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3d0a  ldloc.0
0x3d0b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass14_0::unlockCommand
0x3d10  ldstr    aWaitingstatus// "@waitingStatus"
0x3d15  ldc.i4.0
0x3d16  box      [mscorlib]System.Int32
0x3d1b  ldloca.s 2
0x3d1d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3d23  ldloc.2
0x3d24  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3d29  ldloc.0
0x3d2a  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass14_0::unlockCommand
0x3d2f  ldstr    aLockedstate// "@lockedState"
0x3d34  ldc.i4.2
0x3d35  box      [mscorlib]System.Int32
0x3d3a  ldloca.s 2
0x3d3c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3d42  ldloc.2
0x3d43  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3d48  ldloc.0
0x3d49  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass14_0::unlockCommand
0x3d4e  ldstr    aHostid// "@hostId"
0x3d53  ldarg.0
0x3d54  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x3d59  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x3d5e  ldloca.s 2
0x3d60  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3d66  ldloc.2
0x3d67  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3d6c  ldloc.0
0x3d6d  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass14_0::unlockCommand
0x3d72  ldstr    aModifiedon// "@modifiedOn"
0x3d77  ldarg.0
0x3d78  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x3d7d  box      [mscorlib]System.DateTime
0x3d82  ldloca.s 2
0x3d84  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3d8a  ldloc.2
0x3d8b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3d90  ldarg.0
0x3d91  ldfld    class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_operationsFactory
0x3d96  ldstr    aSelectevents// "SelectEvents"
0x3d9b  ldarg.0
0x3d9c  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x3da1  ldloc.0
0x3da2  ldftn    instance void <>c__DisplayClass14_0::<ReturnLockedToReady>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x3da8  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x3dad  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction)
0x3db2  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x3db7  ret
```
