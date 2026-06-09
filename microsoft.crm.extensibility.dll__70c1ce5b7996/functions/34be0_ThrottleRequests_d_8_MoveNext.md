# <ThrottleRequests>d__8::MoveNext

- ea: `0x34be0`
- end: `0x34ddb`
- name: `<ThrottleRequests>d__8::MoveNext`
- size: `507`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0xeaa0`
- `0xeac0`
- `0xf5e0`
- `0x2ab30`
- `0x2afd0`
- `0x2b040`
- `0x2b700`
- `0x2bd00`
- `0x2bd20`
- `0x2bd40`
- `0x2bd60`
- `0x2bd80`
- `0x34be0`

## pseudocode

```c

```

## disassembly

```asm
0x34be0  ldarg.0
0x34be1  ldfld    int32 <ThrottleRequests>d__8::<>1__state
0x34be6  stloc.0
0x34be7  ldarg.0
0x34be8  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler <ThrottleRequests>d__8::<>4__this
0x34bed  stloc.1
0x34bee  ldloc.0
0x34bef  brfalse  loc_34D4F
0x34bf4  ldsfld   class Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::RequestThrottlingEngine
0x34bf9  ldarg.0
0x34bfa  ldfld    string <ThrottleRequests>d__8::key
0x34bff  ldarg.0
0x34c00  ldflda   class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequests>d__8::<throttlingState>5__2
0x34c05  ldarg.0
0x34c06  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration <ThrottleRequests>d__8::config
0x34c0b  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine::ThrottleDirectApiBurstRequest(string key, [out] class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState& throttlingState, class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration config)
0x34c10  brfalse  loc_34CFF
0x34c15  ldsfld   class Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::RequestThrottlingEngine
0x34c1a  ldarg.0
0x34c1b  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequests>d__8::<throttlingState>5__2
0x34c20  ldarg.0
0x34c21  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration <ThrottleRequests>d__8::config
0x34c26  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine::GetRetryAfterInterval(class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState throttlingState, class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration config)
0x34c2b  stloc.3
0x34c2c  call     class Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource::get_Instance()
0x34c31  ldarg.0
0x34c32  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext <ThrottleRequests>d__8::context
0x34c37  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x34c3c  ldarg.0
0x34c3d  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext <ThrottleRequests>d__8::context
0x34c42  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext::get_UserId()
0x34c47  ldstr    aOdata_1// "OData"
0x34c4c  ldstr    aApiburst// "ApiBurst"
0x34c51  ldarg.0
0x34c52  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <ThrottleRequests>d__8::request
0x34c57  dup
0x34c58  brtrue.s loc_34C5E
0x34c5a  pop
0x34c5b  ldnull
0x34c5c  br.s     loc_34C6F
0x34c5e  call     instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x34c63  dup
0x34c64  brtrue.s loc_34C6A
0x34c66  pop
0x34c67  ldnull
0x34c68  br.s     loc_34C6F
0x34c6a  call     instance string [System]System.Uri::get_AbsolutePath()
0x34c6f  dup
0x34c70  brtrue.s loc_34C78
0x34c72  pop
0x34c73  ldsfld   string [mscorlib]System.String::Empty
0x34c78  ldarg.0
0x34c79  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequests>d__8::<throttlingState>5__2
0x34c7e  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Attempted()
0x34c83  stloc.s  4
0x34c85  ldloca.s 4
0x34c87  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x34c8c  brtrue.s loc_34C92
0x34c8e  ldc.i4.0
0x34c8f  conv.i8
0x34c90  br.s     loc_34C99
0x34c92  ldloca.s 4
0x34c94  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0x34c99  ldarg.0
0x34c9a  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequests>d__8::<throttlingState>5__2
0x34c9f  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Passed()
0x34ca4  ldarg.0
0x34ca5  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequests>d__8::<throttlingState>5__2
0x34caa  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Threshold()
0x34caf  ldloca.s 3
0x34cb1  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x34cb6  ldarg.0
0x34cb7  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration <ThrottleRequests>d__8::config
0x34cbc  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::get_ThrowBurstError()
0x34cc1  callvirt instance void Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource::LogExecution(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, string endpointType, string throttleType, string path, int64 attempted, int64 passed, int64 threshold, float64 retryAfter, [opt] bool enabled)
0x34cc6  ldarg.0
0x34cc7  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration <ThrottleRequests>d__8::config
0x34ccc  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::get_ThrowBurstError()
0x34cd1  brfalse.s loc_34CFF
0x34cd3  ldarg.0
0x34cd4  ldfld    string <ThrottleRequests>d__8::key
0x34cd9  ldloc.3
0x34cda  ldarg.0
0x34cdb  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequests>d__8::<throttlingState>5__2
0x34ce0  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Threshold()
0x34ce5  ldarg.0
0x34ce6  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequests>d__8::<throttlingState>5__2
0x34ceb  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Window()
0x34cf0  stloc.s  5
0x34cf2  ldloca.s 5
0x34cf4  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x34cf9  newobj   instance void Microsoft.Crm.Extensibility.Throttling.ThrottlingRateLimitExceededException::.ctor(string throttleKey, valuetype [mscorlib]System.TimeSpan retryAfter, int64 threshold, float64 windowInSecs)
0x34cfe  throw
0x34cff  ldloc.1
0x34d00  ldarg.0
0x34d01  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <ThrottleRequests>d__8::request
0x34d06  ldarg.0
0x34d07  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ThrottleRequests>d__8::cancellationToken
0x34d0c  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::<>n__0(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x34d11  ldc.i4.0
0x34d12  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::ConfigureAwait(!!T0)
0x34d17  stloc.s  7
0x34d19  ldloca.s 7
0x34d1b  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x34d20  stloc.s  6
0x34d22  ldloca.s 6
0x34d24  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0x34d29  brtrue.s loc_34D6C
0x34d2b  ldarg.0
0x34d2c  ldc.i4.0
0x34d2d  dup
0x34d2e  stloc.0
0x34d2f  stfld    int32 <ThrottleRequests>d__8::<>1__state
0x34d34  ldarg.0
0x34d35  ldloc.s  6
0x34d37  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequests>d__8::<>u__1
0x34d3c  ldarg.0
0x34d3d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequests>d__8::<>t__builder
0x34d42  ldloca.s 6
0x34d44  ldarg.0
0x34d45  call     T0x2B000146
0x34d4a  leave    loc_34DDA
0x34d4f  ldarg.0
0x34d50  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequests>d__8::<>u__1
0x34d55  stloc.s  6
0x34d57  ldarg.0
0x34d58  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequests>d__8::<>u__1
0x34d5d  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x34d63  ldarg.0
0x34d64  ldc.i4.m1
0x34d65  dup
0x34d66  stloc.0
0x34d67  stfld    int32 <ThrottleRequests>d__8::<>1__state
0x34d6c  ldloca.s 6
0x34d6e  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x34d73  dup
0x34d74  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x34d79  ldsfld   string Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottleConstants::RateLimitBurstRequestsHeader
0x34d7e  ldarg.0
0x34d7f  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequests>d__8::<throttlingState>5__2
0x34d84  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Threshold()
0x34d89  ldarg.0
0x34d8a  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState <ThrottleRequests>d__8::<throttlingState>5__2
0x34d8f  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::get_Passed()
0x34d94  sub
0x34d95  ldc.i4.0
0x34d96  conv.i8
0x34d97  call     int64 [mscorlib]System.Math::Max(int64, int64)
0x34d9c  stloc.s  8
0x34d9e  ldloca.s 8
0x34da0  call     instance string [mscorlib]System.Int64::ToString()
0x34da5  call     void Microsoft.Crm.Extensibility.ODataV4.Throttling.HttpHeadersExtensions::AddNonStandardHeader(class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders headers, string headerName, string value)
0x34daa  stloc.2
0x34dab  leave.s  loc_34DC6
0x34dad  stloc.s  9
0x34daf  ldarg.0
0x34db0  ldc.i4.s 0xFE
0x34db2  stfld    int32 <ThrottleRequests>d__8::<>1__state
0x34db7  ldarg.0
0x34db8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequests>d__8::<>t__builder
0x34dbd  ldloc.s  9
0x34dbf  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0x34dc4  leave.s  loc_34DDA
0x34dc6  ldarg.0
0x34dc7  ldc.i4.s 0xFE
0x34dc9  stfld    int32 <ThrottleRequests>d__8::<>1__state
0x34dce  ldarg.0
0x34dcf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <ThrottleRequests>d__8::<>t__builder
0x34dd4  ldloc.2
0x34dd5  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0x34dda  ret
```
