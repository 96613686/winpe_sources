# <PostAsync>d__22::MoveNext

- ea: `0x6c10`
- end: `0x6f74`
- name: `<PostAsync>d__22::MoveNext`
- size: `868`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x1c50`
- `0x1cf0`
- `0x1d10`
- `0x1d20`
- `0x1d30`
- `0x1d50`
- `0x2820`
- `0x5e90`
- `0x60b0`
- `0x6100`
- `0x6330`
- `0x6350`
- `0x63c0`
- `0x63e0`
- `0x65e0`
- `0x6c10`

## string_xrefs

- `0x6d80`: `Unexpected AuthType:{0} for webhook contract for ServiceEndpoint: {1} [{2}]`
- `0x6eaa`: `Exception occurred when sending message to webhook serviceEndpointId: {0}, name: {1}, exception:{2}`
- `0x6eee`: `Received unknown exception during PostAsync for OrgId:{0}, serviceEndpointId: {1}, name: {2}, exception:{3}`

## pseudocode

```c

```

## disassembly

```asm
0x6c10  ldarg.0
0x6c11  ldfld    int32 <PostAsync>d__22::<>1__state
0x6c16  stloc.0
0x6c17  ldarg.0
0x6c18  ldfld    class Microsoft.Crm.ServiceBus.WebhookClient <PostAsync>d__22::<>4__this
0x6c1d  stloc.1
0x6c1e  ldloc.0
0x6c1f  pop
0x6c20  nop
0x6c21  ldloc.0
0x6c22  brfalse  loc_6E6D
0x6c27  ldarg.0
0x6c28  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6c2d  ldarg.0
0x6c2e  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6c33  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Url()
0x6c38  callvirt instance string [mscorlib]System.String::Trim()
0x6c3d  ldc.i4.1
0x6c3e  newarr   [mscorlib]System.Char
0x6c43  dup
0x6c44  ldc.i4.0
0x6c45  ldc.i4.s 0x2F
0x6c47  stelem.i2
0x6c48  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x6c4d  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_Url(string value)
0x6c52  ldarg.0
0x6c53  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6c58  callvirt instance valuetype AuthenticationType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AuthType()
0x6c5d  stloc.s  5
0x6c5f  ldloc.s  5
0x6c61  ldc.i4.4
0x6c62  sub
0x6c63  switch   loc_6CCB, loc_6D2D, loc_6C79
0x6c74  br       loc_6D80
0x6c79  ldloc.1
0x6c7a  ldarg.0
0x6c7b  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6c80  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Url()
0x6c85  ldarg.0
0x6c86  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext <PostAsync>d__22::context
0x6c8b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x6c90  ldarg.0
0x6c91  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6c96  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ServiceEndpointId()
0x6c9b  ldarg.0
0x6c9c  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6ca1  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Name()
0x6ca6  ldarg.0
0x6ca7  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6cac  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AuthValue()
0x6cb1  callvirt instance string [mscorlib]System.String::Trim()
0x6cb6  call     instance class [System]System.Uri Microsoft.Crm.ServiceBus.WebhookClient::GetUriWithQueryParams(string url, valuetype [mscorlib]System.Guid organizationId, string serviceEndpointId, string serviceEndpointName, string queryParamsXml)
0x6cbb  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x6cc0  castclass [System]System.Net.HttpWebRequest
0x6cc5  stloc.3
0x6cc6  br       loc_6DC0
0x6ccb  ldloc.1
0x6ccc  ldarg.0
0x6ccd  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6cd2  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Url()
0x6cd7  ldarg.0
0x6cd8  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext <PostAsync>d__22::context
0x6cdd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x6ce2  ldarg.0
0x6ce3  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6ce8  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ServiceEndpointId()
0x6ced  ldarg.0
0x6cee  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6cf3  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Name()
0x6cf8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x6cfd  dup
0x6cfe  ldstr    aCode// "code"
0x6d03  ldarg.0
0x6d04  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6d09  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AuthValue()
0x6d0e  callvirt instance string [mscorlib]System.String::Trim()
0x6d13  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6d18  call     instance class [System]System.Uri Microsoft.Crm.ServiceBus.WebhookClient::GetUriWithQueryParams(string url, valuetype [mscorlib]System.Guid organizationId, string serviceEndpointId, string serviceEndpointName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParams)
0x6d1d  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x6d22  castclass [System]System.Net.HttpWebRequest
0x6d27  stloc.3
0x6d28  br       loc_6DC0
0x6d2d  ldloc.1
0x6d2e  ldarg.0
0x6d2f  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6d34  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Url()
0x6d39  ldarg.0
0x6d3a  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext <PostAsync>d__22::context
0x6d3f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x6d44  ldarg.0
0x6d45  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6d4a  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ServiceEndpointId()
0x6d4f  ldarg.0
0x6d50  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6d55  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Name()
0x6d5a  ldnull
0x6d5b  call     instance class [System]System.Uri Microsoft.Crm.ServiceBus.WebhookClient::GetUriWithQueryParams(string url, valuetype [mscorlib]System.Guid organizationId, string serviceEndpointId, string serviceEndpointName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParams)
0x6d60  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x6d65  castclass [System]System.Net.HttpWebRequest
0x6d6a  stloc.3
0x6d6b  ldloc.1
0x6d6c  ldloc.3
0x6d6d  ldarg.0
0x6d6e  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6d73  ldarg.0
0x6d74  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext <PostAsync>d__22::context
0x6d79  call     instance void Microsoft.Crm.ServiceBus.WebhookClient::AddCustomHttpHeaders(class [System]System.Net.HttpWebRequest httpRequest, class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context)
0x6d7e  br.s     loc_6DC0
0x6d80  ldstr    aUnexpectedAuth// "Unexpected AuthType:{0} for webhook con"...
0x6d85  ldarg.0
0x6d86  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6d8b  callvirt instance valuetype AuthenticationType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AuthType()
0x6d90  stloc.s  5
0x6d92  ldloca.s 5
0x6d94  constrained. AuthenticationType
0x6d9a  callvirt instance string [mscorlib]System.Object::ToString()
0x6d9f  ldarg.0
0x6da0  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6da5  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Name()
0x6daa  ldarg.0
0x6dab  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6db0  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ServiceEndpointId()
0x6db5  call     string [mscorlib]System.String::Format(string, object, object, object)
0x6dba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x6dbf  throw
0x6dc0  ldloc.1
0x6dc1  ldloc.3
0x6dc2  ldarg.0
0x6dc3  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6dc8  ldarg.0
0x6dc9  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext <PostAsync>d__22::context
0x6dce  call     instance void Microsoft.Crm.ServiceBus.WebhookClient::AddMandatoryHttpHeaders(class [System]System.Net.HttpWebRequest httpRequest, class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context)
0x6dd3  ldarg.0
0x6dd4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext <PostAsync>d__22::context
0x6dd9  ldc.i4   0x40000
0x6dde  conv.i8
0x6ddf  ldarg.0
0x6de0  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6de5  ldloca.s 4
0x6de7  call     bool Microsoft.Crm.ServiceBus.ServiceBusUtility::TryHandleMaxMessageSize(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context, int64 maxMessageSize, class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo, [out] string& serializedContext)
0x6dec  brfalse.s loc_6DF5
0x6dee  ldloc.1
0x6def  ldloc.3
0x6df0  call     instance void Microsoft.Crm.ServiceBus.WebhookClient::AddSizeExceededHttpHeader(class [System]System.Net.HttpWebRequest httpRequest)
0x6df5  ldloc.1
0x6df6  ldloc.3
0x6df7  ldarg.0
0x6df8  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext <PostAsync>d__22::context
0x6dfd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x6e02  call     class Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::GetHttpConfig(valuetype [mscorlib]System.Guid orgId)
0x6e07  ldloc.s  4
0x6e09  ldarg.0
0x6e0a  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6e0f  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ServiceEndpointId()
0x6e14  ldarg.0
0x6e15  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6e1a  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Name()
0x6e1f  ldarg.0
0x6e20  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext <PostAsync>d__22::context
0x6e25  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x6e2a  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Crm.ServiceBus.WebhookClient::SendAsync(class [System]System.Net.HttpWebRequest baseHttpRequest, class Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig httpConfig, string jsonPayload, string serviceEndpointId, string serviceEndpointName, valuetype [mscorlib]System.Guid organizationId)
0x6e2f  ldc.i4.0
0x6e30  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::ConfigureAwait(!!T0)
0x6e35  stloc.s  7
0x6e37  ldloca.s 7
0x6e39  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<string>::GetAwaiter()
0x6e3e  stloc.s  6
0x6e40  ldloca.s 6
0x6e42  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string>::get_IsCompleted()
0x6e47  brtrue.s loc_6E8A
0x6e49  ldarg.0
0x6e4a  ldc.i4.0
0x6e4b  dup
0x6e4c  stloc.0
0x6e4d  stfld    int32 <PostAsync>d__22::<>1__state
0x6e52  ldarg.0
0x6e53  ldloc.s  6
0x6e55  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string> <PostAsync>d__22::<>u__1
0x6e5a  ldarg.0
0x6e5b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <PostAsync>d__22::<>t__builder
0x6e60  ldloca.s 6
0x6e62  ldarg.0
0x6e63  call     T0x2B00000C
0x6e68  leave    loc_6F73
0x6e6d  ldarg.0
0x6e6e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string> <PostAsync>d__22::<>u__1
0x6e73  stloc.s  6
0x6e75  ldarg.0
0x6e76  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string> <PostAsync>d__22::<>u__1
0x6e7b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string>
0x6e81  ldarg.0
0x6e82  ldc.i4.m1
0x6e83  dup
0x6e84  stloc.0
0x6e85  stfld    int32 <PostAsync>d__22::<>1__state
0x6e8a  ldloca.s 6
0x6e8c  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string>::GetResult()
0x6e91  pop
0x6e92  ldnull
0x6e93  stloc.2
0x6e94  leave    loc_6F5F
0x6e99  stloc.s  8
0x6e9b  ldloc.s  8
0x6e9d  ldarg.0
0x6e9e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext <PostAsync>d__22::context
0x6ea3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x6ea8  ldc.i4.s 0x40
0x6eaa  ldstr    aExceptionOccur_1// "Exception occurred when sending message"...
0x6eaf  ldc.i4.3
0x6eb0  newarr   [mscorlib]System.Object
0x6eb5  dup
0x6eb6  ldc.i4.0
0x6eb7  ldarg.0
0x6eb8  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6ebd  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ServiceEndpointId()
0x6ec2  stelem.ref
0x6ec3  dup
0x6ec4  ldc.i4.1
0x6ec5  ldarg.0
0x6ec6  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6ecb  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Name()
0x6ed0  stelem.ref
0x6ed1  dup
0x6ed2  ldc.i4.2
0x6ed3  ldloc.s  8
0x6ed5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x6eda  stelem.ref
0x6edb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6ee0  ldloc.s  8
0x6ee2  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x6ee7  stloc.s  9
0x6ee9  ldloc.s  9
0x6eeb  brtrue.s loc_6F43
0x6eed  ldloc.1
0x6eee  ldstr    aReceivedUnknow// "Received unknown exception during PostA"...
0x6ef3  ldc.i4.4
0x6ef4  newarr   [mscorlib]System.Object
0x6ef9  dup
0x6efa  ldc.i4.0
0x6efb  ldarg.0
0x6efc  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext <PostAsync>d__22::context
0x6f01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x6f06  box      [mscorlib]System.Guid
0x6f0b  stelem.ref
0x6f0c  dup
0x6f0d  ldc.i4.1
0x6f0e  ldarg.0
0x6f0f  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6f14  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ServiceEndpointId()
0x6f19  stelem.ref
0x6f1a  dup
0x6f1b  ldc.i4.2
0x6f1c  ldarg.0
0x6f1d  ldfld    class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation <PostAsync>d__22::endpointInfo
0x6f22  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Name()
0x6f27  stelem.ref
0x6f28  dup
0x6f29  ldc.i4.3
0x6f2a  ldloc.s  8
0x6f2c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x6f31  stelem.ref
0x6f32  call     string [mscorlib]System.String::Format(string, object[])
0x6f37  ldc.i4   0x80050205
0x6f3c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.ServiceBus.WebhookClient::GetCrmExceptionWithInnerException(string message, int32 errorCode)
0x6f41  stloc.s  9
0x6f43  ldloc.s  9
0x6f45  throw
0x6f46  stloc.s  0xA
0x6f48  ldarg.0
0x6f49  ldc.i4.s 0xFE
0x6f4b  stfld    int32 <PostAsync>d__22::<>1__state
0x6f50  ldarg.0
0x6f51  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <PostAsync>d__22::<>t__builder
0x6f56  ldloc.s  0xA
0x6f58  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x6f5d  leave.s  loc_6F73
0x6f5f  ldarg.0
0x6f60  ldc.i4.s 0xFE
0x6f62  stfld    int32 <PostAsync>d__22::<>1__state
0x6f67  ldarg.0
0x6f68  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <PostAsync>d__22::<>t__builder
0x6f6d  ldloc.2
0x6f6e  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x6f73  ret
```
