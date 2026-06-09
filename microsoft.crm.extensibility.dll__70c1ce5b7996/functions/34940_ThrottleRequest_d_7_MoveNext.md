# <ThrottleRequest>d__7::MoveNext

- ea: `0x34940`
- end: `0x34bb1`
- name: `<ThrottleRequest>d__7::MoveNext`
- size: `625`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0xeaa0`
- `0xeac0`
- `0xf550`
- `0x2ab30`
- `0x2ac10`
- `0x2b000`
- `0x2b020`
- `0x2b720`
- `0x2bc10`
- `0x2bd20`
- `0x2bd40`
- `0x2bd60`
- `0x2bd80`
- `0x34940`

## pseudocode

```c

```

## disassembly

```asm
0x34940  ldarg.0
0x34941  ldfld    int32 <ThrottleRequest>d__7::<>1__state
0x34946  stloc.0
0x34947  ldarg.0
0x34948  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler <ThrottleRequest>d__7::<>4__this
0x3494d  stloc.1
0x3494e  ldloc.0
0x3494f  brfalse  loc_34A7C
0x34954  ldarg.0
0x34955  ldarg.0
0x34956  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext <ThrottleRequest>d__7::context
0x3495b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext::get_UserId()
0x34960  stloc.s  4
0x34962  ldloca.s 4
0x34964  constrained. [mscorlib]System.Guid
0x3496a  callvirt instance string [mscorlib]System.Object::ToString()
0x3496f  stfld    string <ThrottleRequest>d__7::<throttlingKey>5__2
0x34974  ldloc.1
0x34975  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.IThrottlingConfigurationFactory Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::throttlingConfigurationFactory
0x3497a  ldarg.0
0x3497b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext <ThrottleRequest>d__7::context
0x34980  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x34985  callvirt instance class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration Microsoft.Crm.Extensibility.ODataV4.Throttling.IThrottlingConfigurationFactory::GetConfiguration(valuetype [mscorlib]System.Guid organizationId)
0x3498a  stloc.3
0x3498b  ldsfld   class Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::RequestThrottlingEngine
0x34990  ldarg.0
0x34991  ldfld    string <ThrottleRequest>d__7::<throttlingKey>5__2
0x34996  ldarg.0
0x34997  ldflda   class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequest>d__7::<throttlingState>5__3
0x3499c  ldloc.3
0x3499d  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine::ThrottleRequestsTimeUsage(string throttlingKey, [out] class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState& throttlingState, class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration config)
0x349a2  brfalse  loc_34A71
0x349a7  call     class Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource::get_Instance()
0x349ac  ldarg.0
0x349ad  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext <ThrottleRequest>d__7::context
0x349b2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x349b7  ldarg.0
0x349b8  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext <ThrottleRequest>d__7::context
0x349bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext::get_UserId()
0x349c2  ldstr    aOdata_1// "OData"
0x349c7  ldstr    aTimeusage// "TimeUsage"
0x349cc  ldarg.0
0x349cd  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <ThrottleRequest>d__7::request
0x349d2  dup
0x349d3  brtrue.s loc_349D9
0x349d5  pop
0x349d6  ldnull
0x349d7  br.s     loc_349EA
0x349d9  call     instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x349de  dup
0x349df  brtrue.s loc_349E5
0x349e1  pop
0x349e2  ldnull
0x349e3  br.s     loc_349EA
0x349e5  call     instance string [System]System.Uri::get_AbsolutePath()
0x349ea  dup
0x349eb  brtrue.s loc_349F3
0x349ed  pop
0x349ee  ldsfld   string [mscorlib]System.String::Empty
0x349f3  ldarg.0
0x349f4  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequest>d__7::<throttlingState>5__3
0x349f9  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Attempted()
0x349fe  stloc.s  5
0x34a00  ldloca.s 5
0x34a02  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x34a07  brtrue.s loc_34A0D
0x34a09  ldc.i4.0
0x34a0a  conv.i8
0x34a0b  br.s     loc_34A14
0x34a0d  ldloca.s 5
0x34a0f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0x34a14  ldarg.0
0x34a15  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequest>d__7::<throttlingState>5__3
0x34a1a  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Passed()
0x34a1f  ldarg.0
0x34a20  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequest>d__7::<throttlingState>5__3
0x34a25  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Threshold()
0x34a2a  ldc.r8   0.0
0x34a33  ldloc.3
0x34a34  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::get_ThrowTimeError()
0x34a39  callvirt instance void Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource::LogExecution(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, string endpointType, string throttleType, string path, int64 attempted, int64 passed, int64 threshold, float64 retryAfter, [opt] bool enabled)
0x34a3e  ldloc.3
0x34a3f  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::get_ThrowTimeError()
0x34a44  brfalse.s loc_34A71
0x34a46  ldarg.0
0x34a47  ldfld    string <ThrottleRequest>d__7::<throttlingKey>5__2
0x34a4c  ldarg.0
0x34a4d  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequest>d__7::<throttlingState>5__3
0x34a52  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Threshold()
0x34a57  ldarg.0
0x34a58  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequest>d__7::<throttlingState>5__3
0x34a5d  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Window()
0x34a62  stloc.s  6
0x34a64  ldloca.s 6
0x34a66  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x34a6b  newobj   instance void Microsoft.Crm.Extensibility.Throttling.ThrottlingTimeExceededException::.ctor(string throttleKey, int64 threshold, float64 windowInSecs)
0x34a70  throw
0x34a71  ldarg.0
0x34a72  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x34a77  stfld    class [System]System.Diagnostics.Stopwatch <ThrottleRequest>d__7::<sw>5__4
0x34a7c  nop
0x34a7d  ldloc.0
0x34a7e  brfalse.s loc_34ADD
0x34a80  ldloc.1
0x34a81  ldarg.0
0x34a82  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <ThrottleRequest>d__7::request
0x34a87  ldarg.0
0x34a88  ldfld    string <ThrottleRequest>d__7::<throttlingKey>5__2
0x34a8d  ldarg.0
0x34a8e  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext <ThrottleRequest>d__7::context
0x34a93  ldloc.3
0x34a94  ldarg.0
0x34a95  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ThrottleRequest>d__7::cancellationToken
0x34a9a  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::ThrottleRequests(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, string key, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext context, class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration config, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x34a9f  ldc.i4.0
0x34aa0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::ConfigureAwait(!!T0)
0x34aa5  stloc.s  9
0x34aa7  ldloca.s 9
0x34aa9  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x34aae  stloc.s  8
0x34ab0  ldloca.s 8
0x34ab2  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0x34ab7  brtrue.s loc_34AFA
0x34ab9  ldarg.0
0x34aba  ldc.i4.0
0x34abb  dup
0x34abc  stloc.0
0x34abd  stfld    int32 <ThrottleRequest>d__7::<>1__state
0x34ac2  ldarg.0
0x34ac3  ldloc.s  8
0x34ac5  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequest>d__7::<>u__1
0x34aca  ldarg.0
0x34acb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequest>d__7::<>t__builder
0x34ad0  ldloca.s 8
0x34ad2  ldarg.0
0x34ad3  call     T0x2B000145
0x34ad8  leave    loc_34BB0
0x34add  ldarg.0
0x34ade  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequest>d__7::<>u__1
0x34ae3  stloc.s  8
0x34ae5  ldarg.0
0x34ae6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequest>d__7::<>u__1
0x34aeb  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x34af1  ldarg.0
0x34af2  ldc.i4.m1
0x34af3  dup
0x34af4  stloc.0
0x34af5  stfld    int32 <ThrottleRequest>d__7::<>1__state
0x34afa  ldloca.s 8
0x34afc  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x34b01  ldarg.0
0x34b02  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequest>d__7::<throttlingState>5__3
0x34b07  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Threshold()
0x34b0c  ldarg.0
0x34b0d  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequest>d__7::<throttlingState>5__3
0x34b12  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Passed()
0x34b17  sub
0x34b18  ldarg.0
0x34b19  ldfld    class [System]System.Diagnostics.Stopwatch <ThrottleRequest>d__7::<sw>5__4
0x34b1e  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x34b23  sub
0x34b24  conv.r8
0x34b25  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x34b2a  stloc.s  7
0x34b2c  dup
0x34b2d  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x34b32  ldsfld   string Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottleConstants::RequestsTimeLimitRateHeader
0x34b37  ldstr    a0N2// "{0:N2}"
0x34b3c  ldloca.s 7
0x34b3e  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x34b43  ldc.r8   0.0
0x34b4c  call     float64 [mscorlib]System.Math::Max(float64, float64)
0x34b51  box      [mscorlib]System.Double
0x34b56  call     string [mscorlib]System.String::Format(string, object)
0x34b5b  call     void Microsoft.Crm.Extensibility.ODataV4.Throttling.HttpHeadersExtensions::AddNonStandardHeader(class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders headers, string headerName, string value)
0x34b60  stloc.2
0x34b61  leave.s  loc_34B9C
0x34b63  ldloc.0
0x34b64  ldc.i4.0
0x34b65  bge.s    loc_34B82
0x34b67  ldsfld   class Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::RequestThrottlingEngine
0x34b6c  ldarg.0
0x34b6d  ldfld    string <ThrottleRequest>d__7::<throttlingKey>5__2
0x34b72  ldarg.0
0x34b73  ldfld    class [System]System.Diagnostics.Stopwatch <ThrottleRequest>d__7::<sw>5__4
0x34b78  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x34b7d  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine::RecordRequestsTimeUsage(string throttlingKey, int64 elapsedMilliseconds)
0x34b82  endfinally
0x34b83  stloc.s  0xA
0x34b85  ldarg.0
0x34b86  ldc.i4.s 0xFE
0x34b88  stfld    int32 <ThrottleRequest>d__7::<>1__state
0x34b8d  ldarg.0
0x34b8e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequest>d__7::<>t__builder
0x34b93  ldloc.s  0xA
0x34b95  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0x34b9a  leave.s  loc_34BB0
0x34b9c  ldarg.0
0x34b9d  ldc.i4.s 0xFE
0x34b9f  stfld    int32 <ThrottleRequest>d__7::<>1__state
0x34ba4  ldarg.0
0x34ba5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequest>d__7::<>t__builder
0x34baa  ldloc.2
0x34bab  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0x34bb0  ret
```
