# <SendAsync>d__0::MoveNext

- ea: `0x339d0`
- end: `0x33c50`
- name: `<SendAsync>d__0::MoveNext`
- size: `640`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x19b60`
- `0x1f0a0`
- `0x24840`
- `0x24930`
- `0x24960`
- `0x24990`
- `0x24a50`
- `0x24e60`
- `0x28b60`
- `0x291b0`
- `0x29300`
- `0x339d0`

## string_xrefs

- `0x33a02`: `Request must contain Configuration`
- `0x33b31`: `no-cache`

## pseudocode

```c

```

## disassembly

```asm
0x339d0  ldarg.0
0x339d1  ldfld    int32 <SendAsync>d__0::<>1__state
0x339d6  stloc.0
0x339d7  ldarg.0
0x339d8  ldfld    class Microsoft.Crm.Extensibility.OData.CrmETagMessageHandler <SendAsync>d__0::<>4__this
0x339dd  stloc.1
0x339de  ldloc.0
0x339df  brfalse.s loc_33A52
0x339e1  ldarg.0
0x339e2  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__0::request
0x339e7  ldnull
0x339e8  cgt.un
0x339ea  ldstr    aRequest_0// "request"
0x339ef  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x339f4  ldarg.0
0x339f5  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__0::request
0x339fa  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::GetConfiguration(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x339ff  ldnull
0x33a00  cgt.un
0x33a02  ldstr    aRequestMustCon// "Request must contain Configuration"
0x33a07  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x33a0c  ldloc.1
0x33a0d  ldarg.0
0x33a0e  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__0::request
0x33a13  ldarg.0
0x33a14  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <SendAsync>d__0::cancellationToken
0x33a19  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> Microsoft.Crm.Extensibility.OData.CrmETagMessageHandler::<>n__0(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x33a1e  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x33a23  stloc.s  5
0x33a25  ldloca.s 5
0x33a27  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0x33a2c  brtrue.s loc_33A6F
0x33a2e  ldarg.0
0x33a2f  ldc.i4.0
0x33a30  dup
0x33a31  stloc.0
0x33a32  stfld    int32 <SendAsync>d__0::<>1__state
0x33a37  ldarg.0
0x33a38  ldloc.s  5
0x33a3a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__0::<>u__1
0x33a3f  ldarg.0
0x33a40  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__0::<>t__builder
0x33a45  ldloca.s 5
0x33a47  ldarg.0
0x33a48  call     T0x2B00013A
0x33a4d  leave    loc_33C4F
0x33a52  ldarg.0
0x33a53  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__0::<>u__1
0x33a58  stloc.s  5
0x33a5a  ldarg.0
0x33a5b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__0::<>u__1
0x33a60  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x33a66  ldarg.0
0x33a67  ldc.i4.m1
0x33a68  dup
0x33a69  stloc.0
0x33a6a  stfld    int32 <SendAsync>d__0::<>1__state
0x33a6f  ldloca.s 5
0x33a71  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x33a76  stloc.3
0x33a77  ldloc.3
0x33a78  brfalse.s loc_33A8F
0x33a7a  ldloc.3
0x33a7b  callvirt instance bool [System.Net.Http]System.Net.Http.HttpResponseMessage::get_IsSuccessStatusCode()
0x33a80  brfalse.s loc_33A8F
0x33a82  ldloc.3
0x33a83  callvirt instance valuetype [System]System.Net.HttpStatusCode [System.Net.Http]System.Net.Http.HttpResponseMessage::get_StatusCode()
0x33a88  ldc.i4   0xCC
0x33a8d  bne.un.s loc_33A96
0x33a8f  ldloc.3
0x33a90  stloc.2
0x33a91  leave    loc_33C3B
0x33a96  ldarg.0
0x33a97  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__0::request
0x33a9c  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsDiscoveryODataRequest(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x33aa1  brfalse.s loc_33AAA
0x33aa3  ldloc.3
0x33aa4  stloc.2
0x33aa5  leave    loc_33C3B
0x33aaa  ldarg.0
0x33aab  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__0::request
0x33ab0  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x33ab5  callvirt instance class [System.Web.OData]System.Web.OData.Routing.ODataPath [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::get_Path()
0x33aba  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType Microsoft.Crm.Extensibility.OData.CrmETagMessageHandler::GetSingleEntityEntityType(class [System.Web.OData]System.Web.OData.Routing.ODataPath path)
0x33abf  stloc.s  4
0x33ac1  ldloc.s  4
0x33ac3  brfalse.s loc_33B40
0x33ac5  ldloc.s  4
0x33ac7  brfalse.s loc_33B40
0x33ac9  ldloc.3
0x33aca  call     object Microsoft.Crm.Extensibility.OData.CrmETagMessageHandler::GetSingleEntityObject(class [System.Net.Http]System.Net.Http.HttpResponseMessage response)
0x33acf  stloc.s  6
0x33ad1  ldloc.s  4
0x33ad3  ldc.i4.0
0x33ad4  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::ToEdmTypeReference(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, bool isNullable)
0x33ad9  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityTypeReference
0x33ade  stloc.s  7
0x33ae0  ldloc.s  7
0x33ae2  brfalse.s loc_33B40
0x33ae4  ldloc.s  7
0x33ae6  ldloc.s  6
0x33ae8  call     class [System.Web.OData]System.Web.OData.ResourceContext Microsoft.Crm.Extensibility.OData.CrmETagMessageHandler::CreateInstanceContext(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityTypeReference reference, object value)
0x33aed  call     class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::CreateETag(class [System.Web.OData]System.Web.OData.ResourceContext resourceContext)
0x33af2  stloc.s  8
0x33af4  ldloc.s  8
0x33af6  brfalse.s loc_33B40
0x33af8  ldloc.3
0x33af9  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x33afe  ldloc.s  8
0x33b00  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders::set_ETag(class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue)
0x33b05  ldloc.3
0x33b06  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x33b0b  newobj   instance void [System.Net.Http]System.Net.Http.Headers.CacheControlHeaderValue::.ctor()
0x33b10  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders::set_CacheControl(class [System.Net.Http]System.Net.Http.Headers.CacheControlHeaderValue)
0x33b15  ldloc.3
0x33b16  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x33b1b  callvirt instance class [System.Net.Http]System.Net.Http.Headers.CacheControlHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders::get_CacheControl()
0x33b20  ldc.i4.1
0x33b21  callvirt instance void [System.Net.Http]System.Net.Http.Headers.CacheControlHeaderValue::set_NoCache(bool)
0x33b26  ldloc.3
0x33b27  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x33b2c  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.NameValueHeaderValue> [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders::get_Pragma()
0x33b31  ldstr    aNoCache// "no-cache"
0x33b36  newobj   instance void [System.Net.Http]System.Net.Http.Headers.NameValueHeaderValue::.ctor(string)
0x33b3b  callvirt instance void class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.NameValueHeaderValue>::Add(var<u1>)
0x33b40  ldarg.0
0x33b41  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__0::request
0x33b46  ldloc.3
0x33b47  call     void Microsoft.Crm.Extensibility.OData.CrmETagMessageHandler::UnescapeJsonPropertyNames(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [System.Net.Http]System.Net.Http.HttpResponseMessage response)
0x33b4c  ldloc.3
0x33b4d  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x33b52  isinst   [System.Web.OData]System.Web.OData.Batch.ODataBatchContent
0x33b57  brfalse  loc_33C1E
0x33b5c  ldarg.0
0x33b5d  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__0::request
0x33b62  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x33b67  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x33b6c  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferContinueOnErrorHeaderSpecified()
0x33b71  brtrue   loc_33C1E
0x33b76  ldloc.3
0x33b77  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x33b7c  castclass [System.Web.OData]System.Web.OData.Batch.ODataBatchContent
0x33b81  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem> [System.Web.OData]System.Web.OData.Batch.ODataBatchContent::get_Responses()
0x33b86  call     T0x2B00013B
0x33b8b  stloc.s  9
0x33b8d  ldloc.s  9
0x33b8f  isinst   [System.Web.OData]System.Web.OData.Batch.OperationResponseItem
0x33b94  stloc.s  0xA
0x33b96  ldloc.s  0xA
0x33b98  brfalse.s loc_33BC4
0x33b9a  ldloc.3
0x33b9b  ldloc.s  0xA
0x33b9d  callvirt instance class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Web.OData]System.Web.OData.Batch.OperationResponseItem::get_Response()
0x33ba2  callvirt instance bool [System.Net.Http]System.Net.Http.HttpResponseMessage::get_IsSuccessStatusCode()
0x33ba7  brtrue.s loc_33BB7
0x33ba9  ldloc.s  0xA
0x33bab  callvirt instance class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Web.OData]System.Web.OData.Batch.OperationResponseItem::get_Response()
0x33bb0  callvirt instance valuetype [System]System.Net.HttpStatusCode [System.Net.Http]System.Net.Http.HttpResponseMessage::get_StatusCode()
0x33bb5  br.s     loc_33BBD
0x33bb7  ldloc.3
0x33bb8  callvirt instance valuetype [System]System.Net.HttpStatusCode [System.Net.Http]System.Net.Http.HttpResponseMessage::get_StatusCode()
0x33bbd  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x33bc2  br.s     loc_33C1E
0x33bc4  ldloc.s  9
0x33bc6  isinst   [System.Web.OData]System.Web.OData.Batch.ChangeSetResponseItem
0x33bcb  dup
0x33bcc  stloc.s  0xB
0x33bce  brfalse.s loc_33C1E
0x33bd0  ldloc.s  0xB
0x33bd2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> [System.Web.OData]System.Web.OData.Batch.ChangeSetResponseItem::get_Responses()
0x33bd7  ldsfld   class [mscorlib]System.Func`2<class [System.Net.Http]System.Net.Http.HttpResponseMessage, bool> <>c::<>9__0_0
0x33bdc  dup
0x33bdd  brtrue.s loc_33BF6
0x33bdf  pop
0x33be0  ldsfld   class <>c <>c::<>9
0x33be5  ldftn    instance bool <>c::<SendAsync>b__0_0(class [System.Net.Http]System.Net.Http.HttpResponseMessage r)
0x33beb  newobj   instance void class [mscorlib]System.Func`2<class [System.Net.Http]System.Net.Http.HttpResponseMessage, bool>::.ctor(object, native int)
0x33bf0  dup
0x33bf1  stsfld   class [mscorlib]System.Func`2<class [System.Net.Http]System.Net.Http.HttpResponseMessage, bool> <>c::<>9__0_0
0x33bf6  call     T0x2B00013C
0x33bfb  call     T0x2B00013D
0x33c00  stloc.s  0xC
0x33c02  ldloc.s  0xC
0x33c04  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_Count()
0x33c09  ldc.i4.0
0x33c0a  ble.s    loc_33C1E
0x33c0c  ldloc.3
0x33c0d  ldloc.s  0xC
0x33c0f  call     T0x2B00013E
0x33c14  callvirt instance valuetype [System]System.Net.HttpStatusCode [System.Net.Http]System.Net.Http.HttpResponseMessage::get_StatusCode()
0x33c19  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x33c1e  ldloc.3
0x33c1f  stloc.2
0x33c20  leave.s  loc_33C3B
0x33c22  stloc.s  0xD
0x33c24  ldarg.0
0x33c25  ldc.i4.s 0xFE
0x33c27  stfld    int32 <SendAsync>d__0::<>1__state
0x33c2c  ldarg.0
0x33c2d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__0::<>t__builder
0x33c32  ldloc.s  0xD
0x33c34  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0x33c39  leave.s  loc_33C4F
0x33c3b  ldarg.0
0x33c3c  ldc.i4.s 0xFE
0x33c3e  stfld    int32 <SendAsync>d__0::<>1__state
0x33c43  ldarg.0
0x33c44  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__0::<>t__builder
0x33c49  ldloc.2
0x33c4a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0x33c4f  ret
```
