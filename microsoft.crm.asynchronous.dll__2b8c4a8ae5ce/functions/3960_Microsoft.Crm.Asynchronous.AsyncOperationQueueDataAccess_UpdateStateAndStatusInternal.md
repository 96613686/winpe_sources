# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::UpdateStateAndStatusInternal

- ea: `0x3960`
- end: `0x3c2d`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::UpdateStateAndStatusInternal`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16870`

## callees

- `0x2730`
- `0x2790`
- `0x2f10`
- `0x2f30`
- `0x2f50`
- `0x2f70`
- `0x2f80`
- `0x2f90`
- `0x2fb0`
- `0x2fd0`
- `0x2ff0`
- `0x3010`
- `0x3030`
- `0x3050`
- `0x30b0`
- `0x3830`
- `0x3960`
- `0x5540`
- `0xd5a0`
- `0xd990`
- `0x156c0`
- `0x157c0`
- `0x15810`
- `0x17080`

## string_xrefs

- `0x3b98`: `UpdateStateAndStatusCommand`
- `0x3bc7`: `{0}-{1}: Operation {2} has been moved to state {3}, status {4}.`

## pseudocode

```c

```

## disassembly

```asm
0x3960  newobj   instance void <>c__DisplayClass12_0::.ctor()
0x3965  stloc.0
0x3966  ldloc.0
0x3967  ldarg.0
0x3968  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass12_0::<>4__this
0x396d  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager::get_Instance()
0x3972  ldarg.1
0x3973  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventState::get_TelemetryActivityId()
0x3978  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryManager::set_CurrentThreadActivityId(valuetype [mscorlib]System.Guid)
0x397d  ldarg.1
0x397e  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncEventState::get_RetryOperation()
0x3983  brfalse.s loc_399C
0x3985  ldarg.1
0x3986  ldarg.0
0x3987  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x398c  ldarg.1
0x398d  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_CurrentRetryCount()
0x3992  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::GetNextRetryTime(int32 currentRetryCount)
0x3997  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_NextOccurrence(valuetype [mscorlib]System.DateTime value)
0x399c  ldloc.0
0x399d  ldarg.0
0x399e  ldarg.1
0x399f  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_NewState()
0x39a4  ldarg.1
0x39a5  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEventState::get_NextOccurrence()
0x39aa  ldarg.1
0x39ab  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncEventState::get_ClearData()
0x39b0  ldarg.1
0x39b1  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_NewStatus()
0x39b6  ldarg.1
0x39b7  callvirt instance string Microsoft.Crm.Asynchronous.AsyncEventState::get_FriendlyMessage()
0x39bc  ldarg.1
0x39bd  callvirt instance float64 Microsoft.Crm.Asynchronous.AsyncEventState::get_ExecutionTime()
0x39c2  ldarg.2
0x39c3  call     instance string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetStatusStateUpdateSql(int32 newState, valuetype [mscorlib]System.DateTime nextOccurrence, bool clearData, int32 newStatus, string friendlyMessage, float64 executionTime, [opt] bool checkForCompletedJob)
0x39c8  ldc.i4.1
0x39c9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x39ce  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x39d3  ldloc.0
0x39d4  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x39d9  ldstr    aNewstate// "@newState"
0x39de  ldarg.1
0x39df  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_NewState()
0x39e4  box      [mscorlib]System.Int32
0x39e9  ldloca.s 1
0x39eb  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x39f1  ldloc.1
0x39f2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x39f7  ldloc.0
0x39f8  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x39fd  ldstr    aNewstatus// "@newStatus"
0x3a02  ldarg.1
0x3a03  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_NewStatus()
0x3a08  box      [mscorlib]System.Int32
0x3a0d  ldloca.s 1
0x3a0f  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3a15  ldloc.1
0x3a16  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3a1b  ldloc.0
0x3a1c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x3a21  ldstr    aModifiedon// "@modifiedOn"
0x3a26  ldarg.0
0x3a27  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x3a2c  box      [mscorlib]System.DateTime
0x3a31  ldloca.s 1
0x3a33  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3a39  ldloc.1
0x3a3a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3a3f  ldarg.1
0x3a40  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorCode()
0x3a45  brtrue.s loc_3A67
0x3a47  ldloc.0
0x3a48  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x3a4d  ldstr    aErrorcode// "@errorCode"
0x3a52  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x3a57  ldloca.s 1
0x3a59  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3a5f  ldloc.1
0x3a60  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3a65  br.s     loc_3A8B
0x3a67  ldloc.0
0x3a68  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x3a6d  ldstr    aErrorcode// "@errorCode"
0x3a72  ldarg.1
0x3a73  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorCode()
0x3a78  box      [mscorlib]System.Int32
0x3a7d  ldloca.s 1
0x3a7f  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3a85  ldloc.1
0x3a86  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3a8b  ldarg.1
0x3a8c  callvirt instance string Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorMessage()
0x3a91  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3a96  brfalse.s loc_3AB8
0x3a98  ldloc.0
0x3a99  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x3a9e  ldstr    aErrormessage// "@errorMessage"
0x3aa3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x3aa8  ldloca.s 1
0x3aaa  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3ab0  ldloc.1
0x3ab1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3ab6  br.s     loc_3AD7
0x3ab8  ldloc.0
0x3ab9  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x3abe  ldstr    aErrormessage// "@errorMessage"
0x3ac3  ldarg.1
0x3ac4  callvirt instance string Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorMessage()
0x3ac9  ldloca.s 1
0x3acb  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3ad1  ldloc.1
0x3ad2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3ad7  ldarg.1
0x3ad8  callvirt instance string Microsoft.Crm.Asynchronous.AsyncEventState::get_FriendlyMessage()
0x3add  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3ae2  brtrue.s loc_3B03
0x3ae4  ldloc.0
0x3ae5  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x3aea  ldstr    aFriendlymessag_1// "@friendlyMessage"
0x3aef  ldarg.1
0x3af0  callvirt instance string Microsoft.Crm.Asynchronous.AsyncEventState::get_FriendlyMessage()
0x3af5  ldloca.s 1
0x3af7  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3afd  ldloc.1
0x3afe  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3b03  ldarg.1
0x3b04  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEventState::get_NextOccurrence()
0x3b09  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x3b0e  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3b13  brfalse.s loc_3B39
0x3b15  ldloc.0
0x3b16  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x3b1b  ldstr    aPostponeuntil// "@postponeUntil"
0x3b20  ldarg.1
0x3b21  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEventState::get_NextOccurrence()
0x3b26  box      [mscorlib]System.DateTime
0x3b2b  ldloca.s 1
0x3b2d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3b33  ldloc.1
0x3b34  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3b39  ldarg.1
0x3b3a  callvirt instance float64 Microsoft.Crm.Asynchronous.AsyncEventState::get_ExecutionTime()
0x3b3f  ldc.r8   0.0
0x3b48  ble.un.s loc_3B6E
0x3b4a  ldloc.0
0x3b4b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x3b50  ldstr    aExecutiontimes_0// "@executionTimeSpan"
0x3b55  ldarg.1
0x3b56  callvirt instance float64 Microsoft.Crm.Asynchronous.AsyncEventState::get_ExecutionTime()
0x3b5b  box      [mscorlib]System.Double
0x3b60  ldloca.s 1
0x3b62  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3b68  ldloc.1
0x3b69  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3b6e  ldloc.0
0x3b6f  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass12_0::updateCommand
0x3b74  ldstr    aId// "@id"
0x3b79  ldarg.1
0x3b7a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventState::get_EventId()
0x3b7f  box      [mscorlib]System.Guid
0x3b84  ldloca.s 1
0x3b86  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3b8c  ldloc.1
0x3b8d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3b92  ldarg.0
0x3b93  ldfld    class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_operationsFactory
0x3b98  ldstr    aUpdatestateand// "UpdateStateAndStatusCommand"
0x3b9d  ldarg.0
0x3b9e  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x3ba3  ldloc.0
0x3ba4  ldftn    instance void <>c__DisplayClass12_0::<UpdateStateAndStatusInternal>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x3baa  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x3baf  ldc.i4.1
0x3bb0  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, bool shouldExposeException)
0x3bb5  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x3bba  ldarg.0
0x3bbb  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x3bc0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x3bc5  ldc.i4.s 0x15
0x3bc7  ldstr    a01Operation2Ha_0// "{0}-{1}: Operation {2} has been moved t"...
0x3bcc  ldc.i4.5
0x3bcd  newarr   [mscorlib]System.Object
0x3bd2  dup
0x3bd3  ldc.i4.0
0x3bd4  ldarg.0
0x3bd5  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x3bda  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x3bdf  stelem.ref
0x3be0  dup
0x3be1  ldc.i4.1
0x3be2  ldarg.0
0x3be3  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x3be8  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x3bed  stelem.ref
0x3bee  dup
0x3bef  ldc.i4.2
0x3bf0  ldarg.1
0x3bf1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventState::get_EventId()
0x3bf6  box      [mscorlib]System.Guid
0x3bfb  stelem.ref
0x3bfc  dup
0x3bfd  ldc.i4.3
0x3bfe  ldarg.1
0x3bff  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_NewState()
0x3c04  box      [mscorlib]System.Int32
0x3c09  stelem.ref
0x3c0a  dup
0x3c0b  ldc.i4.4
0x3c0c  ldarg.1
0x3c0d  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_NewStatus()
0x3c12  box      [mscorlib]System.Int32
0x3c17  stelem.ref
0x3c18  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c1d  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager::get_Instance()
0x3c22  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3c27  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryManager::set_CurrentThreadActivityId(valuetype [mscorlib]System.Guid)
0x3c2c  ret
```
