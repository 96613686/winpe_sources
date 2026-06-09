# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::UpdateEventState

- ea: `0x50a0`
- end: `0x53a8`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::UpdateEventState`
- size: `776`
- prototype: ``
- caller_count: `1`
- callee_count: `47`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3130`

## callees

- `0x2650`
- `0x2cd0`
- `0x2da0`
- `0x2e60`
- `0x2f20`
- `0x2f40`
- `0x2f60`
- `0x2f80`
- `0x2fa0`
- `0x2fc0`
- `0x2fe0`
- `0x3000`
- `0x3020`
- `0x3040`
- `0x3060`
- `0x3080`
- `0x30a0`
- `0x30b0`
- `0x30c0`
- `0x30d0`
- `0x4bd0`
- `0x5080`
- `0x50a0`
- `0x54e0`
- `0x5500`
- `0x5520`
- `0x59e0`
- `0x5f00`
- `0x5f20`
- `0x5f30`
- `0x5f40`
- `0x5f50`
- `0x7890`
- `0xa7a0`
- `0xa950`
- `0x10900`
- `0x10ea0`
- `0x12330`
- `0x12360`
- `0x12ba0`
- `0x12ce0`
- `0x12f00`
- `0x12f10`
- `0x12f20`
- `0x12fa0`
- `0x12fb0`
- `0x12fd0`

## pseudocode

```c

```

## disassembly

```asm
0x50a0  ldarg.0
0x50a1  ldarg.1
0x50a2  ldarg.2
0x50a3  call     instance bool Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::IsUpdateEventStateNeeded(class Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, class Microsoft.Crm.Asynchronous.AsyncHandlerResult result)
0x50a8  brtrue.s loc_50AB
0x50aa  ret
0x50ab  ldarg.0
0x50ac  ldarg.1
0x50ad  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration()
0x50b2  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess>::GetQueueDataAccess(!!T0)
0x50b7  stloc.0
0x50b8  ldarg.2
0x50b9  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncHandlerResult::get_ResultCode()
0x50be  stloc.1
0x50bf  ldc.i4.3
0x50c0  stloc.2
0x50c1  ldc.i4.0
0x50c2  stloc.3
0x50c3  ldnull
0x50c4  stloc.s  4
0x50c6  ldnull
0x50c7  stloc.s  5
0x50c9  ldc.i4.0
0x50ca  stloc.s  6
0x50cc  ldarg.2
0x50cd  isinst   Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError
0x50d2  stloc.s  7
0x50d4  ldloc.s  7
0x50d6  brfalse.s loc_50F4
0x50d8  ldloc.s  7
0x50da  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::get_ErrorCode()
0x50df  stloc.3
0x50e0  ldloc.s  7
0x50e2  callvirt instance string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::get_ErrorMessage()
0x50e7  stloc.s  4
0x50e9  ldloc.s  7
0x50eb  callvirt instance string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::get_FriendlyMessage()
0x50f0  stloc.s  5
0x50f2  br.s     loc_5112
0x50f4  ldarg.2
0x50f5  isinst   Microsoft.Crm.Asynchronous.AsyncHandlerResultWithMessage
0x50fa  stloc.s  0xC
0x50fc  ldloc.s  0xC
0x50fe  brfalse.s loc_5112
0x5100  ldloc.s  0xC
0x5102  callvirt instance string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithMessage::get_Message()
0x5107  stloc.s  5
0x5109  ldloc.s  0xC
0x510b  callvirt instance string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithMessage::get_FullMessage()
0x5110  stloc.s  4
0x5112  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5117  stloc.s  8
0x5119  ldarg.2
0x511a  isinst   Microsoft.Crm.Asynchronous.AsyncRetryResult
0x511f  brfalse  loc_51AD
0x5124  ldarg.1
0x5125  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x512a  ldarg.0
0x512b  call     instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x5130  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_MaximumRetries()
0x5135  blt.s    loc_513F
0x5137  ldloc.3
0x5138  ldc.i4   0x8004A001
0x513d  bne.un.s loc_5144
0x513f  ldc.i4.1
0x5140  stloc.s  6
0x5142  br.s     loc_51AD
0x5144  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MaxValue()
0x5149  stloc.s  8
0x514b  ldarg.1
0x514c  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration()
0x5151  stloc.s  0xD
0x5153  ldarg.0
0x5154  ldc.i4.1
0x5155  ldc.i4   0xC0004411
0x515a  conv.u8
0x515b  ldc.i4.6
0x515c  newarr   [mscorlib]System.Object
0x5161  dup
0x5162  ldc.i4.0
0x5163  call     string [mscorlib]System.Environment::get_MachineName()
0x5168  stelem.ref
0x5169  dup
0x516a  ldc.i4.1
0x516b  ldarg.1
0x516c  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x5171  box      [mscorlib]System.Int32
0x5176  stelem.ref
0x5177  dup
0x5178  ldc.i4.2
0x5179  ldarg.1
0x517a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x517f  box      [mscorlib]System.Guid
0x5184  stelem.ref
0x5185  dup
0x5186  ldc.i4.3
0x5187  ldloc.s  0xD
0x5189  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationName()
0x518e  stelem.ref
0x518f  dup
0x5190  ldc.i4.4
0x5191  ldloca.s 3
0x5193  ldstr    aX// "x"
0x5198  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x519d  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x51a2  stelem.ref
0x51a3  dup
0x51a4  ldc.i4.5
0x51a5  ldloc.s  4
0x51a7  stelem.ref
0x51a8  call     instance void Microsoft.Crm.Asynchronous.AsyncManagerBase::LogEvent(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] parameters)
0x51ad  ldarg.2
0x51ae  isinst   Microsoft.Crm.Asynchronous.AsyncPausedResult
0x51b3  stloc.s  9
0x51b5  ldloc.s  9
0x51b7  brfalse.s loc_51D5
0x51b9  ldloc.s  9
0x51bb  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncPausedResult::get_PostponeUntil()
0x51c0  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x51c5  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x51ca  brfalse.s loc_51D5
0x51cc  ldloc.s  9
0x51ce  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncPausedResult::get_PostponeUntil()
0x51d3  stloc.s  8
0x51d5  ldarg.2
0x51d6  isinst   Microsoft.Crm.Asynchronous.AsyncRetryResultWithPostponeUntil
0x51db  stloc.s  0xA
0x51dd  ldloc.s  0xA
0x51df  brfalse.s loc_51FD
0x51e1  ldloc.s  0xA
0x51e3  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncRetryResultWithPostponeUntil::get_PostponeUntil()
0x51e8  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x51ed  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x51f2  brfalse.s loc_51FD
0x51f4  ldloc.s  0xA
0x51f6  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncRetryResultWithPostponeUntil::get_PostponeUntil()
0x51fb  stloc.s  8
0x51fd  ldloc.1
0x51fe  ldc.i4.s 0xA
0x5200  bgt.s    loc_520C
0x5202  ldloc.1
0x5203  brfalse.s loc_5248
0x5205  ldloc.1
0x5206  ldc.i4.s 0xA
0x5208  beq.s    loc_522D
0x520a  br.s     loc_5264
0x520c  ldloc.1
0x520d  ldc.i4.s 0x14
0x520f  sub
0x5210  switch   loc_5247, loc_522D, loc_5226
0x5221  ldloc.1
0x5222  ldc.i4.s 0x20
0x5224  bne.un.s loc_5264
0x5226  ldc.i4.3
0x5227  stloc.2
0x5228  ldc.i4.s 0x20
0x522a  stloc.1
0x522b  br.s     loc_5264
0x522d  ldloc.s  6
0x522f  brfalse.s loc_5240
0x5231  ldarg.0
0x5232  ldarg.1
0x5233  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncEventBase::get_ExecutionManager()
0x5238  callvirt instance class Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.QueueManager::HandleSpecialTransition(class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager asyncEventManager)
0x523d  brfalse.s loc_5240
0x523f  ret
0x5240  ldc.i4.1
0x5241  stloc.2
0x5242  ldc.i4.s 0xA
0x5244  stloc.1
0x5245  br.s     loc_5264
0x5247  ret
0x5248  ldc.i4.0
0x5249  ldstr    aUnexpectedStat// "Unexpected status: "
0x524e  ldloca.s 1
0x5250  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5255  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x525a  call     string [mscorlib]System.String::Concat(string, string)
0x525f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5264  ldarg.2
0x5265  isinst   Microsoft.Crm.Asynchronous.AsyncSystemPausedResult
0x526a  brfalse.s loc_5273
0x526c  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MaxValue()
0x5271  stloc.s  8
0x5273  ldarg.1
0x5274  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncEvent::get_IsRecurrenceEvent()
0x5279  brfalse.s loc_529A
0x527b  ldarg.1
0x527c  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::NextOccurrence(class Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x5281  stloc.s  8
0x5283  ldloc.s  8
0x5285  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x528a  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x528f  brfalse.s loc_5295
0x5291  ldc.i4.3
0x5292  stloc.2
0x5293  br.s     loc_529A
0x5295  ldc.i4.1
0x5296  stloc.2
0x5297  ldc.i4.s 0xA
0x5299  stloc.1
0x529a  ldloc.2
0x529b  ldc.i4.1
0x529c  bne.un.s loc_52C9
0x529e  ldloc.1
0x529f  ldc.i4.s 0xA
0x52a1  bne.un.s loc_52C9
0x52a3  ldarg.1
0x52a4  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncEventBase::get_ExecutionManager()
0x52a9  callvirt instance bool Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AutoResumeFromPause()
0x52ae  brfalse.s loc_52C9
0x52b0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x52b5  stloc.s  0xE
0x52b7  ldloca.s 0xE
0x52b9  ldc.r8   1.0
0x52c2  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x52c7  stloc.s  8
0x52c9  newobj   instance void Microsoft.Crm.Asynchronous.AsyncEventState::.ctor()
0x52ce  dup
0x52cf  ldarg.1
0x52d0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x52d5  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_EventId(valuetype [mscorlib]System.Guid value)
0x52da  dup
0x52db  ldloc.2
0x52dc  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_NewState(int32 value)
0x52e1  dup
0x52e2  ldloc.1
0x52e3  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_NewStatus(int32 value)
0x52e8  dup
0x52e9  ldloc.s  8
0x52eb  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_NextOccurrence(valuetype [mscorlib]System.DateTime value)
0x52f0  dup
0x52f1  ldloc.s  6
0x52f3  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_RetryOperation(bool value)
0x52f8  dup
0x52f9  ldarg.1
0x52fa  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x52ff  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_CurrentRetryCount(int32 value)
0x5304  dup
0x5305  ldloc.3
0x5306  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_ErrorCode(int32 value)
0x530b  dup
0x530c  ldloc.s  4
0x530e  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_ErrorMessage(string value)
0x5313  dup
0x5314  ldloc.s  5
0x5316  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_FriendlyMessage(string value)
0x531b  dup
0x531c  ldarg.0
0x531d  ldloc.2
0x531e  ldarg.1
0x531f  call     instance bool Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CanClearData(int32 newState, class Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x5324  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_ClearData(bool value)
0x5329  dup
0x532a  ldarg.1
0x532b  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncEventBase::get_ExecutionManager()
0x5330  callvirt instance float64 Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_ExecutionTimeSeconds()
0x5335  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_ExecutionTime(float64 value)
0x533a  dup
0x533b  ldarg.0
0x533c  ldarg.1
0x533d  ldarg.2
0x533e  call     instance bool Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CanRemoveEvent(class Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, class Microsoft.Crm.Asynchronous.AsyncHandlerResult result)
0x5343  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_CanRemoveEvent(bool value)
0x5348  dup
0x5349  ldarg.2
0x534a  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_HandlerResult(class Microsoft.Crm.Asynchronous.AsyncHandlerResult value)
0x534f  dup
0x5350  ldarg.1
0x5351  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventBase::get_TelemetryActivityId()
0x5356  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_TelemetryActivityId(valuetype [mscorlib]System.Guid value)
0x535b  stloc.s  0xB
0x535d  ldloc.0
0x535e  ldloc.s  0xB
0x5360  ldarg.1
0x5361  callvirt instance void Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess::UpdateStateAndStatus(class Microsoft.Crm.Asynchronous.AsyncEventState newEventState, class Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x5366  ldarg.0
0x5367  ldarg.1
0x5368  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x536d  ldarg.1
0x536e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x5373  call     instance void Microsoft.Crm.Asynchronous.QueueManager::RemoveSpecialTransition(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid eventId)
0x5378  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x537d  ldloc.s  0xB
0x537f  ldarg.2
0x5380  ldarg.1
0x5381  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogStateChangeData(class Microsoft.Crm.Asynchronous.AsyncEventState newState, class Microsoft.Crm.Asynchronous.AsyncHandlerResult result, class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x5386  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager::get_Instance()
0x538b  ldloc.s  0xB
0x538d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventState::get_TelemetryActivityId()
0x5392  newobj   instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventData::.ctor()
0x5397  dup
0x5398  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x539d  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_StartTime(valuetype [mscorlib]System.DateTime)
0x53a2  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryManager::FinishActivity(valuetype [mscorlib]System.Guid, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventData)
0x53a7  ret
```
