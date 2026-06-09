# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::DetectLongLockedEvents

- ea: `0x3f70`
- end: `0x4030`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::DetectLongLockedEvents`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x2790`
- `0xd5a0`
- `0xd990`
- `0x156a0`
- `0x157c0`
- `0x15810`
- `0x17170`

## pseudocode

```c

```

## disassembly

```asm
0x3f70  newobj   instance void <>c__DisplayClass16_0::.ctor()
0x3f75  stloc.0
0x3f76  ldloc.0
0x3f77  ldarg.0
0x3f78  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass16_0::<>4__this
0x3f7d  ldstr    aSelectAsyncope// "select\r\n\t\t\t\t\tAsyncOperationId\r"...
0x3f82  stloc.1
0x3f83  ldloc.0
0x3f84  ldloc.1
0x3f85  ldc.i4.1
0x3f86  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x3f8b  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass16_0::longLockedCommand
0x3f90  ldloc.0
0x3f91  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass16_0::longLockedCommand
0x3f96  ldstr    aLockedstate// "@lockedState"
0x3f9b  ldc.i4.2
0x3f9c  box      [mscorlib]System.Int32
0x3fa1  ldloca.s 2
0x3fa3  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3fa9  ldloc.2
0x3faa  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3faf  ldloc.0
0x3fb0  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass16_0::longLockedCommand
0x3fb5  ldstr    aHostid// "@hostId"
0x3fba  ldarg.0
0x3fbb  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x3fc0  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x3fc5  ldloca.s 2
0x3fc7  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3fcd  ldloc.2
0x3fce  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3fd3  ldloc.0
0x3fd4  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass16_0::longLockedCommand
0x3fd9  ldstr    aTwohoursago// "@twoHoursAgo"
0x3fde  ldarg.0
0x3fdf  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x3fe4  stloc.3
0x3fe5  ldloca.s 3
0x3fe7  ldc.r8   -2.0
0x3ff0  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x3ff5  box      [mscorlib]System.DateTime
0x3ffa  ldloca.s 2
0x3ffc  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4002  ldloc.2
0x4003  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x4008  ldarg.0
0x4009  ldfld    class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_operationsFactory
0x400e  ldstr    aDetectlonglock// "DetectLongLockedEvents"
0x4013  ldarg.0
0x4014  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x4019  ldloc.0
0x401a  ldftn    instance void <>c__DisplayClass16_0::<DetectLongLockedEvents>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x4020  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x4025  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction)
0x402a  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x402f  ret
```
