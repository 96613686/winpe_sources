# <DownloadExternalFile>d__6::MoveNext

- ea: `0x303e0`
- end: `0x30564`
- name: `<DownloadExternalFile>d__6::MoveNext`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xd000`
- `0xd040`
- `0xd110`
- `0x303e0`

## string_xrefs

- `0x30484`: `Unable to get download link.`

## pseudocode

```c

```

## disassembly

```asm
0x303e0  ldarg.0
0x303e1  ldfld    int32 <DownloadExternalFile>d__6::<>1__state
0x303e6  stloc.0
0x303e7  ldarg.0
0x303e8  ldfld    class Microsoft.Crm.Extensibility.StorageService.StorageController <DownloadExternalFile>d__6::<>4__this
0x303ed  stloc.1
0x303ee  ldloc.0
0x303ef  brfalse.s loc_30407
0x303f1  ldloc.1
0x303f2  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x303f7  ldc.i4   0x1F5
0x303fc  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Net.Http.Formatting]System.Net.Http.HttpRequestMessageExtensions::CreateResponse(class [System.Net.Http]System.Net.Http.HttpRequestMessage, valuetype [System]System.Net.HttpStatusCode)
0x30401  stloc.2
0x30402  leave    loc_3054F
0x30407  nop
0x30408  ldloc.0
0x30409  brfalse.s loc_30451
0x3040b  ldloc.1
0x3040c  ldarg.0
0x3040d  ldfld    string <DownloadExternalFile>d__6::api_version
0x30412  ldarg.0
0x30413  ldfld    class Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata <DownloadExternalFile>d__6::metadata
0x30418  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Crm.Extensibility.StorageService.StorageController::GetExternalFileDownloadURL(string api_version, class Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata metadata)
0x3041d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x30422  stloc.s  4
0x30424  ldloca.s 4
0x30426  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x3042b  brtrue.s loc_3046E
0x3042d  ldarg.0
0x3042e  ldc.i4.0
0x3042f  dup
0x30430  stloc.0
0x30431  stfld    int32 <DownloadExternalFile>d__6::<>1__state
0x30436  ldarg.0
0x30437  ldloc.s  4
0x30439  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadExternalFile>d__6::<>u__1
0x3043e  ldarg.0
0x3043f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <DownloadExternalFile>d__6::<>t__builder
0x30444  ldloca.s 4
0x30446  ldarg.0
0x30447  call     T0x2B000117
0x3044c  leave    loc_30563
0x30451  ldarg.0
0x30452  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadExternalFile>d__6::<>u__1
0x30457  stloc.s  4
0x30459  ldarg.0
0x3045a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadExternalFile>d__6::<>u__1
0x3045f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x30465  ldarg.0
0x30466  ldc.i4.m1
0x30467  dup
0x30468  stloc.0
0x30469  stfld    int32 <DownloadExternalFile>d__6::<>1__state
0x3046e  ldloca.s 4
0x30470  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x30475  stloc.3
0x30476  ldloc.3
0x30477  brtrue.s loc_30494
0x30479  ldloc.1
0x3047a  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x3047f  ldc.i4   0x1F4
0x30484  ldstr    aUnableToGetDow// "Unable to get download link."
0x30489  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::CreateErrorResponse(class [System.Net.Http]System.Net.Http.HttpRequestMessage, valuetype [System]System.Net.HttpStatusCode, string)
0x3048e  stloc.2
0x3048f  leave    loc_3054F
0x30494  nop
0x30495  ldloc.3
0x30496  newobj   instance void [System]System.Uri::.ctor(string)
0x3049b  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x304a0  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0x304a5  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0x304aa  stloc.s  5
0x304ac  ldc.i4   0xC8
0x304b1  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x304b6  dup
0x304b7  ldloc.s  5
0x304b9  newobj   instance void [System.Net.Http]System.Net.Http.StreamContent::.ctor(class [mscorlib]System.IO.Stream)
0x304be  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x304c3  dup
0x304c4  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x304c9  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x304ce  ldstr    aApplicationOct// "application/octet-stream"
0x304d3  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x304d8  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x304dd  ldstr    aAttachment// "attachment"
0x304e2  newobj   instance void [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::.ctor(string)
0x304e7  stloc.s  6
0x304e9  ldloc.s  6
0x304eb  ldarg.0
0x304ec  ldfld    class Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata <DownloadExternalFile>d__6::metadata
0x304f1  callvirt instance string Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata::get_FileName()
0x304f6  callvirt instance void [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::set_FileName(string)
0x304fb  dup
0x304fc  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x30501  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x30506  ldloc.s  6
0x30508  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentDisposition(class [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue)
0x3050d  stloc.2
0x3050e  leave.s  loc_3054F
0x30510  pop
0x30511  ldloc.1
0x30512  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x30517  ldc.i4   0x1F4
0x3051c  ldstr    aAnErrorOccurre_0// "An error occurred when trying to downlo"...
0x30521  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::CreateErrorResponse(class [System.Net.Http]System.Net.Http.HttpRequestMessage, valuetype [System]System.Net.HttpStatusCode, string)
0x30526  stloc.2
0x30527  leave.s  loc_3054F
0x30529  stloc.s  7
0x3052b  ldloc.1
0x3052c  ldloc.s  7
0x3052e  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.Crm.Extensibility.StorageService.StorageController::HandleException(class [mscorlib]System.Exception e)
0x30533  stloc.2
0x30534  leave.s  loc_3054F
0x30536  stloc.s  8
0x30538  ldarg.0
0x30539  ldc.i4.s 0xFE
0x3053b  stfld    int32 <DownloadExternalFile>d__6::<>1__state
0x30540  ldarg.0
0x30541  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <DownloadExternalFile>d__6::<>t__builder
0x30546  ldloc.s  8
0x30548  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0x3054d  leave.s  loc_30563
0x3054f  ldarg.0
0x30550  ldc.i4.s 0xFE
0x30552  stfld    int32 <DownloadExternalFile>d__6::<>1__state
0x30557  ldarg.0
0x30558  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <DownloadExternalFile>d__6::<>t__builder
0x3055d  ldloc.2
0x3055e  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0x30563  ret
```
