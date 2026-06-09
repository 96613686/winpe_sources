# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::ReturnLockedToReadyOnStart

- ea: `0x3dc0`
- end: `0x3f6d`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::ReturnLockedToReadyOnStart`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x27a0`
- `0x3dc0`
- `0x58d0`
- `0xd5a0`
- `0xd990`
- `0x156a0`
- `0x157c0`
- `0x15810`
- `0x17120`

## string_xrefs

- `0x3e57`: `@readyState`
- `0x3e3e`: `update AsyncOperationBase\nset\n	StateCode = @readyState,\n	StatusCode = @waitingStatus,\n	ModifiedOn = @modifiedOn,\n	ModifiedBy = CreatedBy\nwhere AsyncOperationId IN (\n         select AsyncOperationId\n         from AsyncOperationBase with (nolock)\n         where StateCode = @lockedState\n         and HostId like @instanceName\n         and HostId <> @asyncQueueHostId\n         and HostId <> @priorityQueueHostId)`
- `0x3f4b`: `ReturnLockedToReadyOnStart`

## pseudocode

```c

```

## disassembly

```asm
0x3dc0  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x3dc5  stloc.0
0x3dc6  ldloc.0
0x3dc7  ldarg.0
0x3dc8  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass15_0::<>4__this
0x3dcd  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccessFactory::get_InstanceNameDictionary()
0x3dd2  brfalse.s loc_3DE3
0x3dd4  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccessFactory::get_InstanceNameDictionary()
0x3dd9  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x3dde  ldc.i4.2
0x3ddf  ceq
0x3de1  br.s     loc_3DE4
0x3de3  ldc.i4.0
0x3de4  ldstr    aAsyncOperation// "Async Operation Queue Host Id, Priority"...
0x3de9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x3dee  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccessFactory::get_InstanceNameDictionary()
0x3df3  ldstr    aAsyncoperation// "AsyncOperationQueue"
0x3df8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x3dfd  brtrue.s loc_3E06
0x3dff  ldsfld   string [mscorlib]System.String::Empty
0x3e04  br.s     loc_3E15
0x3e06  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccessFactory::get_InstanceNameDictionary()
0x3e0b  ldstr    aAsyncoperation// "AsyncOperationQueue"
0x3e10  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x3e15  stloc.1
0x3e16  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccessFactory::get_InstanceNameDictionary()
0x3e1b  ldstr    aPriorityasynco// "PriorityAsyncOperationQueue"
0x3e20  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x3e25  brtrue.s loc_3E2E
0x3e27  ldsfld   string [mscorlib]System.String::Empty
0x3e2c  br.s     loc_3E3D
0x3e2e  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccessFactory::get_InstanceNameDictionary()
0x3e33  ldstr    aPriorityasynco// "PriorityAsyncOperationQueue"
0x3e38  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x3e3d  stloc.2
0x3e3e  ldstr    aUpdateAsyncope_3// "update AsyncOperationBase\r\nset\r\n\tS"...
0x3e43  stloc.3
0x3e44  ldloc.0
0x3e45  ldloc.3
0x3e46  ldc.i4.1
0x3e47  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x3e4c  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::commandUpdate
0x3e51  ldloc.0
0x3e52  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::commandUpdate
0x3e57  ldstr    aReadystate// "@readyState"
0x3e5c  ldc.i4.0
0x3e5d  box      [mscorlib]System.Int32
0x3e62  ldloca.s 4
0x3e64  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3e6a  ldloc.s  4
0x3e6c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3e71  ldloc.0
0x3e72  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::commandUpdate
0x3e77  ldstr    aWaitingstatus// "@waitingStatus"
0x3e7c  ldc.i4.0
0x3e7d  box      [mscorlib]System.Int32
0x3e82  ldloca.s 4
0x3e84  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3e8a  ldloc.s  4
0x3e8c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3e91  ldloc.0
0x3e92  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::commandUpdate
0x3e97  ldstr    aLockedstate// "@lockedState"
0x3e9c  ldc.i4.2
0x3e9d  box      [mscorlib]System.Int32
0x3ea2  ldloca.s 4
0x3ea4  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3eaa  ldloc.s  4
0x3eac  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3eb1  ldloc.0
0x3eb2  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::commandUpdate
0x3eb7  ldstr    aAsyncqueuehost// "@asyncQueueHostId"
0x3ebc  ldloc.1
0x3ebd  ldloca.s 4
0x3ebf  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3ec5  ldloc.s  4
0x3ec7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3ecc  ldloc.0
0x3ecd  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::commandUpdate
0x3ed2  ldstr    aPriorityqueueh// "@priorityQueueHostId"
0x3ed7  ldloc.2
0x3ed8  ldloca.s 4
0x3eda  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3ee0  ldloc.s  4
0x3ee2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3ee7  ldloc.0
0x3ee8  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::commandUpdate
0x3eed  ldstr    aModifiedon// "@modifiedOn"
0x3ef2  ldarg.0
0x3ef3  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x3ef8  box      [mscorlib]System.DateTime
0x3efd  ldloca.s 4
0x3eff  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3f05  ldloc.s  4
0x3f07  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3f0c  ldloc.0
0x3f0d  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::commandUpdate
0x3f12  ldstr    aInstancename// "@instanceName"
0x3f17  call     string [mscorlib]System.Environment::get_MachineName()
0x3f1c  ldstr    asc_22BF0// "."
0x3f21  ldarg.0
0x3f22  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x3f27  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_RawInstanceName()
0x3f2c  ldstr    asc_25DCA// "%"
0x3f31  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x3f36  ldloca.s 4
0x3f38  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3f3e  ldloc.s  4
0x3f40  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3f45  ldarg.0
0x3f46  ldfld    class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_operationsFactory
0x3f4b  ldstr    aReturnlockedto// "ReturnLockedToReadyOnStart"
0x3f50  ldarg.0
0x3f51  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x3f56  ldloc.0
0x3f57  ldftn    instance void <>c__DisplayClass15_0::<ReturnLockedToReadyOnStart>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x3f5d  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x3f62  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction)
0x3f67  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x3f6c  ret
```
