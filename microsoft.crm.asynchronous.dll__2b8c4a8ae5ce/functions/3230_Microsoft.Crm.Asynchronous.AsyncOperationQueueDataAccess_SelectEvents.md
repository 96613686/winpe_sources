# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::SelectEvents

- ea: `0x3230`
- end: `0x3395`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::SelectEvents`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x2790`
- `0x3230`
- `0x33d0`
- `0x33e0`
- `0xd5a0`
- `0xd8e0`
- `0xd990`
- `0x15320`
- `0x156a0`
- `0x157c0`
- `0x15810`
- `0x169d0`

## string_xrefs

- `0x32c8`: `@readyState`

## pseudocode

```c

```

## disassembly

```asm
0x3230  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x3235  stloc.0
0x3236  ldloc.0
0x3237  ldarg.0
0x3238  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x323d  ldloc.0
0x323e  ldarg.1
0x323f  stfld    int32 <>c__DisplayClass2_0::numberOfEvents
0x3244  ldloc.0
0x3245  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::.ctor()
0x324a  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager> <>c__DisplayClass2_0::asyncEventManagers
0x324f  ldloc.0
0x3250  ldarg.0
0x3251  call     instance bool Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::get_IsSelectingPriorityJobs()
0x3256  stfld    bool <>c__DisplayClass2_0::selectPriorityJob
0x325b  ldarg.0
0x325c  ldsfld   string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_asyncServiceAppLock
0x3261  ldarg.0
0x3262  call     instance string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetSelectEventSQL()
0x3267  call     instance string Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string applicationLockName, string query)
0x326c  stloc.1
0x326d  ldloc.0
0x326e  ldloc.1
0x326f  ldc.i4.1
0x3270  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x3275  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x327a  ldloc.0
0x327b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x3280  ldstr    aRecordstoselec// "@recordsToSelect"
0x3285  ldloc.0
0x3286  ldfld    int32 <>c__DisplayClass2_0::numberOfEvents
0x328b  box      [mscorlib]System.Int32
0x3290  ldloca.s 3
0x3292  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3298  ldloc.3
0x3299  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x329e  ldloc.0
0x329f  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x32a4  ldstr    aHostid// "@hostId"
0x32a9  ldarg.0
0x32aa  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x32af  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x32b4  ldloca.s 3
0x32b6  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x32bc  ldloc.3
0x32bd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x32c2  ldloc.0
0x32c3  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x32c8  ldstr    aReadystate// "@readyState"
0x32cd  ldc.i4.0
0x32ce  box      [mscorlib]System.Int32
0x32d3  ldloca.s 3
0x32d5  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x32db  ldloc.3
0x32dc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x32e1  ldloc.0
0x32e2  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x32e7  ldstr    aLockedstate// "@lockedState"
0x32ec  ldc.i4.2
0x32ed  box      [mscorlib]System.Int32
0x32f2  ldloca.s 3
0x32f4  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x32fa  ldloc.3
0x32fb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3300  ldloc.0
0x3301  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x3306  ldstr    aInprogressstat// "@inProgressStatus"
0x330b  ldc.i4.s 0x14
0x330d  box      [mscorlib]System.Int32
0x3312  ldloca.s 3
0x3314  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x331a  ldloc.3
0x331b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3320  ldloc.0
0x3321  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x3326  ldstr    aModifiedon// "@modifiedOn"
0x332b  ldarg.0
0x332c  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x3331  box      [mscorlib]System.DateTime
0x3336  ldloca.s 3
0x3338  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x333e  ldloc.3
0x333f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3344  ldarg.0
0x3345  ldfld    class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_operationsFactory
0x334a  ldstr    aSelectevents// "SelectEvents"
0x334f  ldarg.0
0x3350  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x3355  ldloc.0
0x3356  ldftn    instance void <>c__DisplayClass2_0::<SelectEvents>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x335c  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x3361  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction)
0x3366  dup
0x3367  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x336c  isinst   Microsoft.Crm.Asynchronous.Operations.OrganizationOperation
0x3371  stloc.2
0x3372  ldloc.2
0x3373  brfalse.s loc_338E
0x3375  ldstr    aSucceeded// "Succeeded"
0x337a  ldloc.2
0x337b  callvirt instance bool Microsoft.Crm.Asynchronous.Operations.OrganizationOperation::get_Succeeded()
0x3380  stloc.s  4
0x3382  ldloca.s 4
0x3384  call     instance string [mscorlib]System.Boolean::ToString()
0x3389  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0x338e  ldloc.0
0x338f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager> <>c__DisplayClass2_0::asyncEventManagers
0x3394  ret
```
