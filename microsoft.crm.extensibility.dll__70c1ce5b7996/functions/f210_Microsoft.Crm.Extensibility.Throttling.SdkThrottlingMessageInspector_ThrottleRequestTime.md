# Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::ThrottleRequestTime

- ea: `0xf210`
- end: `0xf2ab`
- name: `Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::ThrottleRequestTime`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0xf190`

## callees

- `0xc850`
- `0xeaa0`
- `0xeac0`
- `0xf210`
- `0xf550`
- `0x2b000`
- `0x2b720`
- `0x2bd20`
- `0x2bd40`
- `0x2bd60`
- `0x2bd80`
- `0x31550`
- `0x31570`

## string_xrefs

- `0xf235`: `SdkService`

## pseudocode

```c

```

## disassembly

```asm
0xf210  ldarg.0
0xf211  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::throttlingEngine
0xf216  ldarg.2
0xf217  ldloca.s 0
0xf219  ldarg.3
0xf21a  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine::ThrottleRequestsTimeUsage(string throttlingKey, [out] class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState& throttlingState, class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration config)
0xf21f  brfalse  loc_F2AA
0xf224  call     class Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource::get_Instance()
0xf229  ldarg.1
0xf22a  callvirt instance valuetype [mscorlib]System.Guid ThrottleRequestContext::get_OrgId()
0xf22f  ldarg.1
0xf230  callvirt instance valuetype [mscorlib]System.Guid ThrottleRequestContext::get_UserId()
0xf235  ldstr    aSdkservice// "SdkService"
0xf23a  ldstr    aTimeusage// "TimeUsage"
0xf23f  ldarg.s  4
0xf241  ldloc.0
0xf242  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Attempted()
0xf247  stloc.1
0xf248  ldloca.s 1
0xf24a  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xf24f  brtrue.s loc_F255
0xf251  ldc.i4.0
0xf252  conv.i8
0xf253  br.s     loc_F25C
0xf255  ldloca.s 1
0xf257  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0xf25c  ldloc.0
0xf25d  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Passed()
0xf262  ldloc.0
0xf263  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Threshold()
0xf268  ldc.r8   0.0
0xf271  ldarg.3
0xf272  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::get_ThrowTimeError()
0xf277  callvirt instance void Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource::LogExecution(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, string endpointType, string throttleType, string path, int64 attempted, int64 passed, int64 threshold, float64 retryAfter, [opt] bool enabled)
0xf27c  ldarg.3
0xf27d  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::get_ThrowTimeError()
0xf282  brfalse.s loc_F2AA
0xf284  ldarg.0
0xf285  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::servicePlatformLogger
0xf28a  ldarg.2
0xf28b  ldloc.0
0xf28c  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Threshold()
0xf291  ldloc.0
0xf292  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Window()
0xf297  stloc.2
0xf298  ldloca.s 2
0xf29a  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xf29f  newobj   instance void Microsoft.Crm.Extensibility.Throttling.ThrottlingTimeExceededException::.ctor(string throttleKey, int64 threshold, float64 windowInSecs)
0xf2a4  call     class [mscorlib]System.Exception Microsoft.Crm.Extensibility.OdataTelemetryUtil::EnsureTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger, class [mscorlib]System.Exception exception)
0xf2a9  throw
0xf2aa  ret
```
