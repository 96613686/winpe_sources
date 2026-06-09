# <SendAsync>d__3::MoveNext

- ea: `0x13800`
- end: `0x139cb`
- name: `<SendAsync>d__3::MoveNext`
- size: `459`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x12f0`
- `0x1400`
- `0x13800`

## string_xrefs

- `0x1382a`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x13800  ldarg.0
0x13801  ldfld    int32 <SendAsync>d__3::<>1__state
0x13806  stloc.0
0x13807  ldloc.0
0x13808  brfalse  loc_138B8
0x1380d  ldarg.0
0x1380e  ldfld    class [System]System.Uri <SendAsync>d__3::url
0x13813  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x13818  castclass [System]System.Net.HttpWebRequest
0x1381d  stloc.2
0x1381e  ldloc.2
0x1381f  ldstr    aPost_0// "POST"
0x13824  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0x13829  ldloc.2
0x1382a  ldstr    aApplicationJso// "application/json"
0x1382f  callvirt instance void [System]System.Net.WebRequest::set_ContentType(string)
0x13834  ldloc.2
0x13835  ldc.i4.1
0x13836  callvirt instance void [System]System.Net.HttpWebRequest::set_KeepAlive(bool)
0x1383b  ldloc.2
0x1383c  ldc.i4.1
0x1383d  callvirt instance void [System]System.Net.HttpWebRequest::set_Pipelined(bool)
0x13842  ldloc.2
0x13843  ldarg.0
0x13844  ldfld    class Microsoft.Crm.Asynchronous.FlowHttpRequestConfig <SendAsync>d__3::httpConfig
0x13849  callvirt instance int32 Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::get_HttpRequestTimeoutInMilliSeconds()
0x1384e  callvirt instance void [System]System.Net.WebRequest::set_Timeout(int32)
0x13853  ldloc.2
0x13854  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebRequest::GetRequestStream()
0x13859  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0x1385e  stloc.3
0x1385f  ldloc.3
0x13860  ldarg.0
0x13861  ldfld    string <SendAsync>d__3::jsonPayload
0x13866  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1386b  leave.s  loc_1387B
0x1386d  ldloc.0
0x1386e  ldc.i4.0
0x1386f  bge.s    loc_1387A
0x13871  ldloc.3
0x13872  brfalse.s loc_1387A
0x13874  ldloc.3
0x13875  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1387a  endfinally
0x1387b  ldloc.2
0x1387c  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x13881  ldstr    aXMsCorrelation// "x-ms-correlation-request-id"
0x13886  ldarg.0
0x13887  ldfld    string <SendAsync>d__3::requestId
0x1388c  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x13891  ldloc.2
0x13892  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x13897  ldstr    aXMsClientReque// "x-ms-client-request-id"
0x1389c  ldarg.0
0x1389d  ldfld    string <SendAsync>d__3::requestId
0x138a2  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x138a7  ldarg.0
0x138a8  ldfld    class [System]System.Uri <SendAsync>d__3::url
0x138ad  ldarg.0
0x138ae  ldfld    class Microsoft.Crm.Asynchronous.FlowHttpRequestConfig <SendAsync>d__3::httpConfig
0x138b3  call     void Microsoft.Crm.Asynchronous.WebApiClient::SetServicePointLimits(class [System]System.Uri webhookUri, class Microsoft.Crm.Asynchronous.FlowHttpRequestConfig httpConfig)
0x138b8  nop
0x138b9  ldloc.0
0x138ba  brfalse.s loc_13900
0x138bc  ldloc.2
0x138bd  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System]System.Net.WebResponse> [System]System.Net.WebRequest::GetResponseAsync()
0x138c2  ldc.i4.0
0x138c3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System]System.Net.WebResponse>::ConfigureAwait(!!T0)
0x138c8  stloc.s  6
0x138ca  ldloca.s 6
0x138cc  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [System]System.Net.WebResponse>::GetAwaiter()
0x138d1  stloc.s  5
0x138d3  ldloca.s 5
0x138d5  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse>::get_IsCompleted()
0x138da  brtrue.s loc_1391D
0x138dc  ldarg.0
0x138dd  ldc.i4.0
0x138de  dup
0x138df  stloc.0
0x138e0  stfld    int32 <SendAsync>d__3::<>1__state
0x138e5  ldarg.0
0x138e6  ldloc.s  5
0x138e8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse> <SendAsync>d__3::<>u__1
0x138ed  ldarg.0
0x138ee  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype [System]System.Net.HttpStatusCode> <SendAsync>d__3::<>t__builder
0x138f3  ldloca.s 5
0x138f5  ldarg.0
0x138f6  call     T0x2B00002D
0x138fb  leave    loc_139CA
0x13900  ldarg.0
0x13901  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse> <SendAsync>d__3::<>u__1
0x13906  stloc.s  5
0x13908  ldarg.0
0x13909  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse> <SendAsync>d__3::<>u__1
0x1390e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse>
0x13914  ldarg.0
0x13915  ldc.i4.m1
0x13916  dup
0x13917  stloc.0
0x13918  stfld    int32 <SendAsync>d__3::<>1__state
0x1391d  ldloca.s 5
0x1391f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse>::GetResult()
0x13924  ldloca.s 5
0x13926  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse>
0x1392c  castclass [System]System.Net.HttpWebResponse
0x13931  stloc.s  4
0x13933  ldarg.0
0x13934  ldloc.s  4
0x13936  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x1393b  stfld    valuetype [System]System.Net.HttpStatusCode <SendAsync>d__3::<resultStatusCode>5__1
0x13940  leave.s  loc_13952
0x13942  ldloc.0
0x13943  ldc.i4.0
0x13944  bge.s    loc_13951
0x13946  ldloc.s  4
0x13948  brfalse.s loc_13951
0x1394a  ldloc.s  4
0x1394c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13951  endfinally
0x13952  leave.s  loc_13994
0x13954  stloc.s  7
0x13956  ldloc.s  7
0x13958  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0x1395d  ldc.i4.s 0xE
0x1395f  bne.un.s loc_1396E
0x13961  ldarg.0
0x13962  ldc.i4   0x198
0x13967  stfld    valuetype [System]System.Net.HttpStatusCode <SendAsync>d__3::<resultStatusCode>5__1
0x1396c  br.s     loc_13992
0x1396e  ldloc.s  7
0x13970  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x13975  brfalse.s loc_13990
0x13977  ldarg.0
0x13978  ldloc.s  7
0x1397a  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x1397f  castclass [System]System.Net.HttpWebResponse
0x13984  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x13989  stfld    valuetype [System]System.Net.HttpStatusCode <SendAsync>d__3::<resultStatusCode>5__1
0x1398e  br.s     loc_13992
0x13990  rethrow
0x13992  leave.s  loc_13994
0x13994  ldarg.0
0x13995  ldfld    valuetype [System]System.Net.HttpStatusCode <SendAsync>d__3::<resultStatusCode>5__1
0x1399a  stloc.1
0x1399b  leave.s  loc_139B6
0x1399d  stloc.s  8
0x1399f  ldarg.0
0x139a0  ldc.i4.s 0xFE
0x139a2  stfld    int32 <SendAsync>d__3::<>1__state
0x139a7  ldarg.0
0x139a8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype [System]System.Net.HttpStatusCode> <SendAsync>d__3::<>t__builder
0x139ad  ldloc.s  8
0x139af  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype [System]System.Net.HttpStatusCode>::SetException(class [mscorlib]System.Exception)
0x139b4  leave.s  loc_139CA
0x139b6  ldarg.0
0x139b7  ldc.i4.s 0xFE
0x139b9  stfld    int32 <SendAsync>d__3::<>1__state
0x139be  ldarg.0
0x139bf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype [System]System.Net.HttpStatusCode> <SendAsync>d__3::<>t__builder
0x139c4  ldloc.1
0x139c5  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype [System]System.Net.HttpStatusCode>::SetResult(var<u1>)
0x139ca  ret
```
