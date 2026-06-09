# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogStateChangeData

- ea: `0x10ea0`
- end: `0x11074`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogStateChangeData`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x50a0`

## callees

- `0x2da0`
- `0x2f30`
- `0x2f50`
- `0x5f00`
- `0x6010`
- `0x10ea0`
- `0x110e0`
- `0x11740`
- `0x118c0`
- `0x118d0`
- `0x11920`
- `0x12330`
- `0x12340`
- `0x12ba0`
- `0x12fd0`

## pseudocode

```c

```

## disassembly

```asm
0x10ea0  ldarg.3
0x10ea1  brfalse.s loc_10EB3
0x10ea3  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::get_Instance()
0x10ea8  ldarg.3
0x10ea9  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::HasFixedId(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x10eae  brtrue.s loc_10EB3
0x10eb0  ldarg.1
0x10eb1  brtrue.s loc_10EB4
0x10eb3  ret
0x10eb4  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::get_Instance()
0x10eb9  ldarg.3
0x10eba  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::IsLoggingAllowedForEvent(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x10ebf  brtrue.s loc_10EC2
0x10ec1  ret
0x10ec2  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::GetPayLoadStructure()
0x10ec7  stloc.0
0x10ec8  ldarg.3
0x10ec9  isinst   Microsoft.Crm.Asynchronous.AsyncEvent
0x10ece  stloc.1
0x10ecf  ldstr    aAsyncstatechan// "AsyncStateChange"
0x10ed4  stloc.2
0x10ed5  ldloc.1
0x10ed6  brtrue.s loc_10EF8
0x10ed8  ldloc.0
0x10ed9  ldstr    aAsynceventtype// "AsyncEventType"
0x10ede  ldarg.3
0x10edf  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10ee4  callvirt instance string [mscorlib]System.Object::ToString()
0x10ee9  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x10eee  call     T0x2B00002A
0x10ef3  br       loc_1104D
0x10ef8  ldloc.0
0x10ef9  ldstr    aAccumulatedexe// "AccumulatedExecutionTimeMs"
0x10efe  ldloc.1
0x10eff  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncEventBase::get_ExecutionManager()
0x10f04  callvirt instance float64 Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_ExecutionTimeSeconds()
0x10f09  ldc.r8   1000.0
0x10f12  mul
0x10f13  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.DoubleJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(float64)
0x10f18  call     T0x2B00002E
0x10f1d  ldloc.1
0x10f1e  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEventBase::get_CreatedOn()
0x10f23  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x10f28  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x10f2d  brfalse.s loc_10F5F
0x10f2f  ldloc.0
0x10f30  ldstr    aTotalelapsedti// "TotalElapsedTimeMs"
0x10f35  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10f3a  ldloc.1
0x10f3b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEventBase::get_CreatedOn()
0x10f40  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x10f45  stloc.s  7
0x10f47  ldloca.s 7
0x10f49  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x10f4e  ldc.i4   0x2710
0x10f53  conv.i8
0x10f54  div
0x10f55  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.LongJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int64)
0x10f5a  call     T0x2B00002D
0x10f5f  ldarg.2
0x10f60  isinst   Microsoft.Crm.Asynchronous.AsyncRetryResult
0x10f65  stloc.3
0x10f66  ldarg.2
0x10f67  isinst   Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError
0x10f6c  ldarg.2
0x10f6d  isinst   Microsoft.Crm.Asynchronous.AsyncPausedResult
0x10f72  stloc.s  4
0x10f74  ldarg.2
0x10f75  isinst   Microsoft.Crm.Asynchronous.AsyncSucceededResult
0x10f7a  stloc.s  5
0x10f7c  ldarg.2
0x10f7d  isinst   Microsoft.Crm.Asynchronous.AsyncRemoveEventResult
0x10f82  stloc.s  6
0x10f84  ldloc.3
0x10f85  brfalse.s loc_10FB9
0x10f87  ldstr    aAsyncstatechan_0// "AsyncStateChangeErrorRetry"
0x10f8c  stloc.2
0x10f8d  ldloc.0
0x10f8e  ldstr    aRetrycount// "RetryCount"
0x10f93  ldloc.1
0x10f94  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x10f99  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x10f9e  call     T0x2B00002C
0x10fa3  ldloc.0
0x10fa4  ldstr    aErrorcode_0// "ErrorCode"
0x10fa9  ldloc.3
0x10faa  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncHandlerResult::get_ResultCode()
0x10faf  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x10fb4  call     T0x2B00002C
0x10fb9  brfalse.s loc_10FD7
0x10fbb  ldstr    aAsyncstatechan_1// "AsyncStateChangeError"
0x10fc0  stloc.2
0x10fc1  ldloc.0
0x10fc2  ldstr    aErrorcode_0// "ErrorCode"
0x10fc7  ldarg.2
0x10fc8  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncHandlerResult::get_ResultCode()
0x10fcd  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x10fd2  call     T0x2B00002C
0x10fd7  ldloc.s  4
0x10fd9  brfalse.s loc_11008
0x10fdb  ldstr    aAsyncstatechan_2// "AsyncStateChangePostpone"
0x10fe0  stloc.2
0x10fe1  ldloc.0
0x10fe2  ldstr    aPostponeduntil// "PostponedUntilMs"
0x10fe7  ldloc.s  4
0x10fe9  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncPausedResult::get_PostponeUntil()
0x10fee  stloc.s  8
0x10ff0  ldloca.s 8
0x10ff2  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x10ff7  ldc.i4   0x2710
0x10ffc  conv.i8
0x10ffd  div
0x10ffe  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.LongJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int64)
0x11003  call     T0x2B00002D
0x11008  ldloc.s  5
0x1100a  brtrue.s loc_1101B
0x1100c  ldloc.s  6
0x1100e  brfalse.s loc_11021
0x11010  ldloc.s  6
0x11012  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncHandlerResult::get_ResultCode()
0x11017  ldc.i4.s 0x1E
0x11019  bne.un.s loc_11021
0x1101b  ldstr    aAsyncstatechan_3// "AsyncStateChangeSuccess"
0x11020  stloc.2
0x11021  ldloc.0
0x11022  ldstr    aNewstate_0// "NewState"
0x11027  ldarg.1
0x11028  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_NewState()
0x1102d  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x11032  call     T0x2B00002C
0x11037  ldloc.0
0x11038  ldstr    aNewstatus_0// "NewStatus"
0x1103d  ldarg.1
0x1103e  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_NewStatus()
0x11043  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x11048  call     T0x2B00002C
0x1104d  ldarg.0
0x1104e  ldarg.3
0x1104f  ldloc.2
0x11050  ldloc.0
0x11051  ldloc.1
0x11052  brtrue.s loc_11058
0x11054  ldc.i4.m1
0x11055  conv.i8
0x11056  br.s     loc_1106E
0x11058  ldloc.1
0x11059  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncEventBase::get_ExecutionManager()
0x1105e  callvirt instance float64 Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_CurrentExecutionTimeSeconds()
0x11063  ldc.r8   1000.0
0x1106c  mul
0x1106d  conv.i8
0x1106e  call     instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::WriteTelemetryEventData(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent, string eventName, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> payload, [opt] int64 executionTimeMs)
0x11073  ret
```
