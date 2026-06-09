# Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::ThrottleRequestCount

- ea: `0xf2b0`
- end: `0xf358`
- name: `Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::ThrottleRequestCount`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0xf190`

## callees

- `0xc850`
- `0xeaa0`
- `0xeac0`
- `0xf2b0`
- `0xf5e0`
- `0x2afd0`
- `0x2b040`
- `0x2b700`
- `0x2bd20`
- `0x2bd40`
- `0x2bd60`
- `0x2bd80`
- `0x31550`
- `0x31570`

## string_xrefs

- `0xf2e3`: `SdkService`

## pseudocode

```c

```

## disassembly

```asm
0xf2b0  ldarg.0
0xf2b1  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::throttlingEngine
0xf2b6  ldarg.2
0xf2b7  ldloca.s 0
0xf2b9  ldarg.3
0xf2ba  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine::ThrottleDirectApiBurstRequest(string key, [out] class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState& throttlingState, class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration config)
0xf2bf  brfalse  loc_F357
0xf2c4  ldarg.0
0xf2c5  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::throttlingEngine
0xf2ca  ldloc.0
0xf2cb  ldarg.3
0xf2cc  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine::GetRetryAfterInterval(class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState throttlingState, class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration config)
0xf2d1  stloc.1
0xf2d2  call     class Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource::get_Instance()
0xf2d7  ldarg.1
0xf2d8  callvirt instance valuetype [mscorlib]System.Guid ThrottleRequestContext::get_OrgId()
0xf2dd  ldarg.1
0xf2de  callvirt instance valuetype [mscorlib]System.Guid ThrottleRequestContext::get_UserId()
0xf2e3  ldstr    aSdkservice// "SdkService"
0xf2e8  ldstr    aApiburst// "ApiBurst"
0xf2ed  ldarg.s  4
0xf2ef  ldloc.0
0xf2f0  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Attempted()
0xf2f5  stloc.2
0xf2f6  ldloca.s 2
0xf2f8  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xf2fd  brtrue.s loc_F303
0xf2ff  ldc.i4.0
0xf300  conv.i8
0xf301  br.s     loc_F30A
0xf303  ldloca.s 2
0xf305  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0xf30a  ldloc.0
0xf30b  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Passed()
0xf310  ldloc.0
0xf311  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Threshold()
0xf316  ldloca.s 1
0xf318  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xf31d  ldarg.3
0xf31e  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::get_ThrowBurstError()
0xf323  callvirt instance void Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource::LogExecution(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, string endpointType, string throttleType, string path, int64 attempted, int64 passed, int64 threshold, float64 retryAfter, [opt] bool enabled)
0xf328  ldarg.3
0xf329  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::get_ThrowBurstError()
0xf32e  brfalse.s loc_F357
0xf330  ldarg.0
0xf331  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::servicePlatformLogger
0xf336  ldarg.2
0xf337  ldloc.1
0xf338  ldloc.0
0xf339  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Threshold()
0xf33e  ldloc.0
0xf33f  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Window()
0xf344  stloc.3
0xf345  ldloca.s 3
0xf347  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xf34c  newobj   instance void Microsoft.Crm.Extensibility.Throttling.ThrottlingRateLimitExceededException::.ctor(string throttleKey, valuetype [mscorlib]System.TimeSpan retryAfter, int64 threshold, float64 windowInSecs)
0xf351  call     class [mscorlib]System.Exception Microsoft.Crm.Extensibility.OdataTelemetryUtil::EnsureTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger, class [mscorlib]System.Exception exception)
0xf356  throw
0xf357  ret
```
