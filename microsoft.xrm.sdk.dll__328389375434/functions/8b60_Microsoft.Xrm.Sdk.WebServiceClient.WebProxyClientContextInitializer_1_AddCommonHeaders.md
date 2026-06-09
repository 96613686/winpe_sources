# Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1::AddCommonHeaders

- ea: `0x8b60`
- end: `0x8c46`
- name: `Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1::AddCommonHeaders`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8b60`

## string_xrefs

- `0x8b81`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x8bbc`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x8bf7`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x8c35`: `http://schemas.microsoft.com/xrm/2011/Contracts`

## pseudocode

```c

```

## disassembly

```asm
0x8b60  ldarg.0
0x8b61  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>> class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1<var<u1>>::get_ServiceProxy()
0x8b66  callvirt instance string class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>>::get_ClientAppName()
0x8b6b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8b70  brtrue.s loc_8B9B
0x8b72  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x8b77  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x8b7c  ldstr    aClientappname// "ClientAppName"
0x8b81  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x8b86  ldarg.0
0x8b87  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>> class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1<var<u1>>::get_ServiceProxy()
0x8b8c  callvirt instance string class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>>::get_ClientAppName()
0x8b91  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x8b96  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x8b9b  ldarg.0
0x8b9c  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>> class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1<var<u1>>::get_ServiceProxy()
0x8ba1  callvirt instance string class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>>::get_ClientAppVersion()
0x8ba6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8bab  brtrue.s loc_8BD6
0x8bad  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x8bb2  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x8bb7  ldstr    aClientappversi// "ClientAppVersion"
0x8bbc  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x8bc1  ldarg.0
0x8bc2  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>> class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1<var<u1>>::get_ServiceProxy()
0x8bc7  callvirt instance string class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>>::get_ClientAppVersion()
0x8bcc  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x8bd1  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x8bd6  ldarg.0
0x8bd7  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>> class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1<var<u1>>::get_ServiceProxy()
0x8bdc  callvirt instance string class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>>::get_SdkClientVersion()
0x8be1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8be6  brtrue.s loc_8C12
0x8be8  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x8bed  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x8bf2  ldstr    aSdkclientversi// "SdkClientVersion"
0x8bf7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x8bfc  ldarg.0
0x8bfd  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>> class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1<var<u1>>::get_ServiceProxy()
0x8c02  callvirt instance string class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>>::get_SdkClientVersion()
0x8c07  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x8c0c  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x8c11  ret
0x8c12  ldarg.0
0x8c13  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>> class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1<var<u1>>::get_ServiceProxy()
0x8c18  callvirt instance string class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>>::GetXrmSdkAssemblyFileVersion()
0x8c1d  stloc.0
0x8c1e  ldloc.0
0x8c1f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8c24  brtrue.s loc_8C45
0x8c26  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x8c2b  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x8c30  ldstr    aSdkclientversi// "SdkClientVersion"
0x8c35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x8c3a  ldloc.0
0x8c3b  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x8c40  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x8c45  ret
```
