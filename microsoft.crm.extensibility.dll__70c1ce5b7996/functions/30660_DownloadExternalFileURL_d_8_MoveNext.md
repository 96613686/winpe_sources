# <DownloadExternalFileURL>d__8::MoveNext

- ea: `0x30660`
- end: `0x30771`
- name: `<DownloadExternalFileURL>d__8::MoveNext`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xd000`
- `0xd040`
- `0x30660`

## string_xrefs

- `0x30704`: `Unable to retrieve download link for external file.`

## pseudocode

```c

```

## disassembly

```asm
0x30660  ldarg.0
0x30661  ldfld    int32 <DownloadExternalFileURL>d__8::<>1__state
0x30666  stloc.0
0x30667  ldarg.0
0x30668  ldfld    class Microsoft.Crm.Extensibility.StorageService.StorageController <DownloadExternalFileURL>d__8::<>4__this
0x3066d  stloc.1
0x3066e  ldloc.0
0x3066f  brfalse.s loc_30687
0x30671  ldloc.1
0x30672  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x30677  ldc.i4   0x1F5
0x3067c  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Net.Http.Formatting]System.Net.Http.HttpRequestMessageExtensions::CreateResponse(class [System.Net.Http]System.Net.Http.HttpRequestMessage, valuetype [System]System.Net.HttpStatusCode)
0x30681  stloc.2
0x30682  leave    loc_3075C
0x30687  nop
0x30688  ldloc.0
0x30689  brfalse.s loc_306D1
0x3068b  ldloc.1
0x3068c  ldarg.0
0x3068d  ldfld    string <DownloadExternalFileURL>d__8::api_version
0x30692  ldarg.0
0x30693  ldfld    class Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata <DownloadExternalFileURL>d__8::metadata
0x30698  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Crm.Extensibility.StorageService.StorageController::GetExternalFileDownloadURL(string api_version, class Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata metadata)
0x3069d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x306a2  stloc.s  4
0x306a4  ldloca.s 4
0x306a6  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x306ab  brtrue.s loc_306EE
0x306ad  ldarg.0
0x306ae  ldc.i4.0
0x306af  dup
0x306b0  stloc.0
0x306b1  stfld    int32 <DownloadExternalFileURL>d__8::<>1__state
0x306b6  ldarg.0
0x306b7  ldloc.s  4
0x306b9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadExternalFileURL>d__8::<>u__1
0x306be  ldarg.0
0x306bf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <DownloadExternalFileURL>d__8::<>t__builder
0x306c4  ldloca.s 4
0x306c6  ldarg.0
0x306c7  call     T0x2B000119
0x306cc  leave    loc_30770
0x306d1  ldarg.0
0x306d2  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadExternalFileURL>d__8::<>u__1
0x306d7  stloc.s  4
0x306d9  ldarg.0
0x306da  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadExternalFileURL>d__8::<>u__1
0x306df  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x306e5  ldarg.0
0x306e6  ldc.i4.m1
0x306e7  dup
0x306e8  stloc.0
0x306e9  stfld    int32 <DownloadExternalFileURL>d__8::<>1__state
0x306ee  ldloca.s 4
0x306f0  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x306f5  stloc.3
0x306f6  ldloc.3
0x306f7  brtrue.s loc_30711
0x306f9  ldloc.1
0x306fa  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x306ff  ldc.i4   0x1F4
0x30704  ldstr    aUnableToRetrie// "Unable to retrieve download link for ex"...
0x30709  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::CreateErrorResponse(class [System.Net.Http]System.Net.Http.HttpRequestMessage, valuetype [System]System.Net.HttpStatusCode, string)
0x3070e  stloc.2
0x3070f  leave.s  loc_3075C
0x30711  ldc.i4   0xC8
0x30716  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x3071b  dup
0x3071c  ldloc.1
0x3071d  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x30722  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_RequestMessage(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x30727  dup
0x30728  ldloc.3
0x30729  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0x3072e  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x30733  stloc.2
0x30734  leave.s  loc_3075C
0x30736  stloc.s  5
0x30738  ldloc.1
0x30739  ldloc.s  5
0x3073b  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.Crm.Extensibility.StorageService.StorageController::HandleException(class [mscorlib]System.Exception e)
0x30740  stloc.2
0x30741  leave.s  loc_3075C
0x30743  stloc.s  6
0x30745  ldarg.0
0x30746  ldc.i4.s 0xFE
0x30748  stfld    int32 <DownloadExternalFileURL>d__8::<>1__state
0x3074d  ldarg.0
0x3074e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <DownloadExternalFileURL>d__8::<>t__builder
0x30753  ldloc.s  6
0x30755  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0x3075a  leave.s  loc_30770
0x3075c  ldarg.0
0x3075d  ldc.i4.s 0xFE
0x3075f  stfld    int32 <DownloadExternalFileURL>d__8::<>1__state
0x30764  ldarg.0
0x30765  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <DownloadExternalFileURL>d__8::<>t__builder
0x3076a  ldloc.2
0x3076b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0x30770  ret
```
