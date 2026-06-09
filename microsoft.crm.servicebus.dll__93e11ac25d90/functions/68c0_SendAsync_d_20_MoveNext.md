# <SendAsync>d__20::MoveNext

- ea: `0x68c0`
- end: `0x6bf0`
- name: `<SendAsync>d__20::MoveNext`
- size: `816`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x5e70`
- `0x6330`
- `0x6480`
- `0x64f0`
- `0x6590`
- `0x65c0`
- `0x68c0`

## string_xrefs

- `0x6a61`: `Non success http status code: {0} received from server for OrgId:{1}, serviceEndpointId: {2}, name: {3}, retryCount: {4}`
- `0x6aeb`: `Hit retryable exception during webhook http post for serviceEndpointId: {0}, name: {1}, retryCount: {2}, httpErrorcode: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x68c0  ldarg.0
0x68c1  ldfld    int32 <SendAsync>d__20::<>1__state
0x68c6  stloc.0
0x68c7  ldarg.0
0x68c8  ldfld    class Microsoft.Crm.ServiceBus.WebhookClient <SendAsync>d__20::<>4__this
0x68cd  stloc.1
0x68ce  ldloc.0
0x68cf  brfalse.s loc_691F
0x68d1  ldarg.0
0x68d2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException>::.ctor()
0x68d7  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException> <SendAsync>d__20::<exceptionList>5__2
0x68dc  ldarg.0
0x68dd  ldc.i4.0
0x68de  stfld    int32 <SendAsync>d__20::<maxRetryCount>5__3
0x68e3  ldloc.1
0x68e4  ldfld    bool Microsoft.Crm.ServiceBus.WebhookClient::_retryTransientHttpErrors
0x68e9  brfalse.s loc_68FC
0x68eb  ldarg.0
0x68ec  ldarg.0
0x68ed  ldfld    class Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig <SendAsync>d__20::httpConfig
0x68f2  callvirt instance int32 Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::get_RetryCountForTransientHttpErrors()
0x68f7  stfld    int32 <SendAsync>d__20::<maxRetryCount>5__3
0x68fc  ldloc.1
0x68fd  ldarg.0
0x68fe  ldfld    class [System]System.Net.HttpWebRequest <SendAsync>d__20::baseHttpRequest
0x6903  callvirt instance class [System]System.Uri [System]System.Net.WebRequest::get_RequestUri()
0x6908  ldarg.0
0x6909  ldfld    class Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig <SendAsync>d__20::httpConfig
0x690e  call     instance void Microsoft.Crm.ServiceBus.WebhookClient::SetServicePointLimits(class [System]System.Uri webhookUri, class Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig httpConfig)
0x6913  ldarg.0
0x6914  ldc.i4.0
0x6915  stfld    int32 <SendAsync>d__20::<count>5__4
0x691a  br       loc_6BAD
0x691f  nop
0x6920  ldloc.0
0x6921  brfalse.s loc_693C
0x6923  ldloc.1
0x6924  ldarg.0
0x6925  ldfld    class [System]System.Net.HttpWebRequest <SendAsync>d__20::baseHttpRequest
0x692a  ldarg.0
0x692b  ldfld    class Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig <SendAsync>d__20::httpConfig
0x6930  ldarg.0
0x6931  ldfld    string <SendAsync>d__20::jsonPayload
0x6936  call     instance class [System]System.Net.HttpWebRequest Microsoft.Crm.ServiceBus.WebhookClient::PrepareFullHttpRequest(class [System]System.Net.HttpWebRequest baseHttpRequest, class Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig httpConfig, string jsonPayload)
0x693b  stloc.3
0x693c  nop
0x693d  ldloc.0
0x693e  brfalse.s loc_6984
0x6940  ldloc.3
0x6941  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System]System.Net.WebResponse> [System]System.Net.WebRequest::GetResponseAsync()
0x6946  ldc.i4.0
0x6947  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System]System.Net.WebResponse>::ConfigureAwait(!!T0)
0x694c  stloc.s  6
0x694e  ldloca.s 6
0x6950  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [System]System.Net.WebResponse>::GetAwaiter()
0x6955  stloc.s  5
0x6957  ldloca.s 5
0x6959  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse>::get_IsCompleted()
0x695e  brtrue.s loc_69A1
0x6960  ldarg.0
0x6961  ldc.i4.0
0x6962  dup
0x6963  stloc.0
0x6964  stfld    int32 <SendAsync>d__20::<>1__state
0x6969  ldarg.0
0x696a  ldloc.s  5
0x696c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse> <SendAsync>d__20::<>u__1
0x6971  ldarg.0
0x6972  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <SendAsync>d__20::<>t__builder
0x6977  ldloca.s 5
0x6979  ldarg.0
0x697a  call     T0x2B00000B
0x697f  leave    loc_6BEF
0x6984  ldarg.0
0x6985  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse> <SendAsync>d__20::<>u__1
0x698a  stloc.s  5
0x698c  ldarg.0
0x698d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse> <SendAsync>d__20::<>u__1
0x6992  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse>
0x6998  ldarg.0
0x6999  ldc.i4.m1
0x699a  dup
0x699b  stloc.0
0x699c  stfld    int32 <SendAsync>d__20::<>1__state
0x69a1  ldloca.s 5
0x69a3  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Net.WebResponse>::GetResult()
0x69a8  castclass [System]System.Net.HttpWebResponse
0x69ad  stloc.s  4
0x69af  ldloc.1
0x69b0  ldloc.s  4
0x69b2  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x69b7  call     instance bool Microsoft.Crm.ServiceBus.WebhookClient::IsSuccessHttpStatusCode(int32 statusCode)
0x69bc  brtrue.s loc_69E1
0x69be  ldloc.s  4
0x69c0  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x69c5  ldstr    aReceivedNonSuc// "Received non-success http status code: "
0x69ca  ldloc.s  4
0x69cc  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x69d1  box      [System]System.Net.HttpStatusCode
0x69d6  call     string [mscorlib]System.String::Concat(object, object)
0x69db  newobj   instance void [System.Web]System.Web.HttpException::.ctor(int32, string)
0x69e0  throw
0x69e1  leave    loc_6BBE
0x69e6  ldloc.0
0x69e7  ldc.i4.0
0x69e8  bge.s    loc_69F5
0x69ea  ldloc.s  4
0x69ec  brfalse.s loc_69F5
0x69ee  ldloc.s  4
0x69f0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69f5  endfinally
0x69f6  dup
0x69f7  isinst   [System]System.Net.WebException
0x69fc  stloc.s  7
0x69fe  isinst   [System.Web]System.Web.HttpException
0x6a03  stloc.s  8
0x6a05  ldc.i4.0
0x6a06  stloc.s  9
0x6a08  ldloc.s  7
0x6a0a  brfalse.s loc_6A2A
0x6a0c  ldloc.s  7
0x6a0e  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0x6a13  ldc.i4.s 0xE
0x6a15  bne.un.s loc_6A2A
0x6a17  ldloc.1
0x6a18  ldloc.s  7
0x6a1a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x6a1f  ldc.i4   0x80050202
0x6a24  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.ServiceBus.WebhookClient::GetCrmExceptionWithInnerException(string message, int32 errorCode)
0x6a29  throw
0x6a2a  ldloc.s  7
0x6a2c  brfalse.s loc_6A4C
0x6a2e  ldloc.s  7
0x6a30  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x6a35  brfalse.s loc_6A4C
0x6a37  ldloc.s  7
0x6a39  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x6a3e  castclass [System]System.Net.HttpWebResponse
0x6a43  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x6a48  stloc.s  9
0x6a4a  br.s     loc_6A59
0x6a4c  ldloc.s  8
0x6a4e  brfalse.s loc_6A59
0x6a50  ldloc.s  8
0x6a52  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x6a57  stloc.s  9
0x6a59  ldloc.s  9
0x6a5b  brfalse  loc_6B37
0x6a60  ldloc.1
0x6a61  ldstr    aNonSuccessHttp// "Non success http status code: {0} recei"...
0x6a66  ldc.i4.5
0x6a67  newarr   [mscorlib]System.Object
0x6a6c  dup
0x6a6d  ldc.i4.0
0x6a6e  ldloc.s  9
0x6a70  box      [mscorlib]System.Int32
0x6a75  stelem.ref
0x6a76  dup
0x6a77  ldc.i4.1
0x6a78  ldarg.0
0x6a79  ldfld    valuetype [mscorlib]System.Guid <SendAsync>d__20::organizationId
0x6a7e  box      [mscorlib]System.Guid
0x6a83  stelem.ref
0x6a84  dup
0x6a85  ldc.i4.2
0x6a86  ldarg.0
0x6a87  ldfld    string <SendAsync>d__20::serviceEndpointId
0x6a8c  stelem.ref
0x6a8d  dup
0x6a8e  ldc.i4.3
0x6a8f  ldarg.0
0x6a90  ldfld    string <SendAsync>d__20::serviceEndpointName
0x6a95  stelem.ref
0x6a96  dup
0x6a97  ldc.i4.4
0x6a98  ldarg.0
0x6a99  ldfld    int32 <SendAsync>d__20::<count>5__4
0x6a9e  box      [mscorlib]System.Int32
0x6aa3  stelem.ref
0x6aa4  call     string [mscorlib]System.String::Format(string, object[])
0x6aa9  ldc.i4   0x80050201
0x6aae  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.ServiceBus.WebhookClient::GetCrmExceptionWithInnerException(string message, int32 errorCode)
0x6ab3  stloc.s  0xA
0x6ab5  ldarg.0
0x6ab6  ldfld    int32 <SendAsync>d__20::<count>5__4
0x6abb  ldarg.0
0x6abc  ldfld    int32 <SendAsync>d__20::<maxRetryCount>5__3
0x6ac1  bne.un.s loc_6AC6
0x6ac3  ldloc.s  0xA
0x6ac5  throw
0x6ac6  ldloc.s  9
0x6ac8  ldc.i4   0x1F6
0x6acd  beq.s    loc_6AE1
0x6acf  ldloc.s  9
0x6ad1  ldc.i4   0x1F7
0x6ad6  beq.s    loc_6AE1
0x6ad8  ldloc.s  9
0x6ada  ldc.i4   0x1F8
0x6adf  bne.un.s loc_6B34
0x6ae1  ldloc.s  0xA
0x6ae3  ldarg.0
0x6ae4  ldfld    valuetype [mscorlib]System.Guid <SendAsync>d__20::organizationId
0x6ae9  ldc.i4.s 0x40
0x6aeb  ldstr    aHitRetryableEx// "Hit retryable exception during webhook "...
0x6af0  ldc.i4.4
0x6af1  newarr   [mscorlib]System.Object
0x6af6  dup
0x6af7  ldc.i4.0
0x6af8  ldarg.0
0x6af9  ldfld    string <SendAsync>d__20::serviceEndpointId
0x6afe  stelem.ref
0x6aff  dup
0x6b00  ldc.i4.1
0x6b01  ldarg.0
0x6b02  ldfld    string <SendAsync>d__20::serviceEndpointName
0x6b07  stelem.ref
0x6b08  dup
0x6b09  ldc.i4.2
0x6b0a  ldarg.0
0x6b0b  ldfld    int32 <SendAsync>d__20::<count>5__4
0x6b10  box      [mscorlib]System.Int32
0x6b15  stelem.ref
0x6b16  dup
0x6b17  ldc.i4.3
0x6b18  ldloc.s  9
0x6b1a  box      [mscorlib]System.Int32
0x6b1f  stelem.ref
0x6b20  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6b25  ldarg.0
0x6b26  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException> <SendAsync>d__20::<exceptionList>5__2
0x6b2b  ldloc.s  0xA
0x6b2d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException>::Add(var<u1>)
0x6b32  leave.s  loc_6B9B
0x6b34  ldloc.s  0xA
0x6b36  throw
0x6b37  rethrow
0x6b39  stloc.s  0xB
0x6b3b  ldloc.s  0xB
0x6b3d  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x6b42  stloc.s  0xC
0x6b44  ldnull
0x6b45  stloc.s  0xD
0x6b47  ldloc.s  0xC
0x6b49  brfalse.s loc_6B51
0x6b4b  ldloc.s  0xC
0x6b4d  stloc.s  0xD
0x6b4f  br.s     loc_6B65
0x6b51  ldloc.1
0x6b52  ldloc.s  0xB
0x6b54  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x6b59  ldc.i4   0x80050205
0x6b5e  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.ServiceBus.WebhookClient::GetCrmExceptionWithInnerException(string message, int32 errorCode)
0x6b63  stloc.s  0xD
0x6b65  ldarg.0
0x6b66  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException> <SendAsync>d__20::<exceptionList>5__2
0x6b6b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException>::get_Count()
0x6b70  ldc.i4.0
0x6b71  ble.s    loc_6B98
0x6b73  ldarg.0
0x6b74  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException> <SendAsync>d__20::<exceptionList>5__2
0x6b79  ldloc.s  0xD
0x6b7b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException>::Add(var<u1>)
0x6b80  ldloc.1
0x6b81  ldloc.1
0x6b82  ldarg.0
0x6b83  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException> <SendAsync>d__20::<exceptionList>5__2
0x6b88  call     instance string Microsoft.Crm.ServiceBus.WebhookClient::ConvertCrmExceptionListToString(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException> exceptionList)
0x6b8d  ldc.i4   0x80050205
0x6b92  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.ServiceBus.WebhookClient::GetCrmExceptionWithInnerException(string message, int32 errorCode)
0x6b97  throw
0x6b98  ldloc.s  0xD
0x6b9a  throw
0x6b9b  ldarg.0
0x6b9c  ldfld    int32 <SendAsync>d__20::<count>5__4
0x6ba1  stloc.s  0xE
0x6ba3  ldarg.0
0x6ba4  ldloc.s  0xE
0x6ba6  ldc.i4.1
0x6ba7  add
0x6ba8  stfld    int32 <SendAsync>d__20::<count>5__4
0x6bad  ldarg.0
0x6bae  ldfld    int32 <SendAsync>d__20::<count>5__4
0x6bb3  ldarg.0
0x6bb4  ldfld    int32 <SendAsync>d__20::<maxRetryCount>5__3
0x6bb9  ble      loc_691F
0x6bbe  ldnull
0x6bbf  stloc.2
0x6bc0  leave.s  loc_6BDB
0x6bc2  stloc.s  0xF
0x6bc4  ldarg.0
0x6bc5  ldc.i4.s 0xFE
0x6bc7  stfld    int32 <SendAsync>d__20::<>1__state
0x6bcc  ldarg.0
0x6bcd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <SendAsync>d__20::<>t__builder
0x6bd2  ldloc.s  0xF
0x6bd4  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x6bd9  leave.s  loc_6BEF
0x6bdb  ldarg.0
0x6bdc  ldc.i4.s 0xFE
0x6bde  stfld    int32 <SendAsync>d__20::<>1__state
  ... truncated ...
```
