# Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::Initialize

- ea: `0x85b0`
- end: `0x872b`
- name: `Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::Initialize`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x8590`

## callees

- `0x8280`
- `0x82a0`
- `0x82c0`
- `0x82e0`
- `0x8300`
- `0x8320`
- `0x85a0`
- `0x85b0`

## string_xrefs

- `0x85e6`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x8621`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x8666`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x86a1`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x86dc`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x8705`: `http://schemas.microsoft.com/xrm/2011/Contracts`

## pseudocode

```c

```

## disassembly

```asm
0x85b0  ldarg.0
0x85b1  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>> class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceProxy()
0x85b6  brtrue.s loc_85B9
0x85b8  ret
0x85b9  ldarg.0
0x85ba  call     instance void class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1<class Microsoft.Xrm.Sdk.IOrganizationService>::AddTokenToHeaders()
0x85bf  ldarg.0
0x85c0  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClient`1<var<u1>> class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceProxy()
0x85c5  brfalse  loc_872A
0x85ca  ldarg.0
0x85cb  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::get_OrganizationWebProxyClient()
0x85d0  callvirt instance bool Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient::get_OfflinePlayback()
0x85d5  brfalse.s loc_85FB
0x85d7  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x85dc  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x85e1  ldstr    aIsofflineplayb// "IsOfflinePlayback"
0x85e6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x85eb  ldc.i4.1
0x85ec  box      [mscorlib]System.Boolean
0x85f1  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x85f6  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x85fb  ldarg.0
0x85fc  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::get_OrganizationWebProxyClient()
0x8601  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient::get_CallerId()
0x8606  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x860b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8610  brfalse.s loc_8640
0x8612  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x8617  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x861c  ldstr    aCallerid// "CallerId"
0x8621  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x8626  ldarg.0
0x8627  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::get_OrganizationWebProxyClient()
0x862c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient::get_CallerId()
0x8631  box      [mscorlib]System.Guid
0x8636  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x863b  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x8640  ldarg.0
0x8641  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::get_OrganizationWebProxyClient()
0x8646  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient::get_CallerRegardingObjectId()
0x864b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8650  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8655  brfalse.s loc_8685
0x8657  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x865c  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x8661  ldstr    aCallerregardin// "CallerRegardingObjectId"
0x8666  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x866b  ldarg.0
0x866c  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::get_OrganizationWebProxyClient()
0x8671  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient::get_CallerRegardingObjectId()
0x8676  box      [mscorlib]System.Guid
0x867b  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x8680  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x8685  ldarg.0
0x8686  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::get_OrganizationWebProxyClient()
0x868b  callvirt instance int32 Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient::get_LanguageCodeOverride()
0x8690  brfalse.s loc_86C0
0x8692  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x8697  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x869c  ldstr    aLanguagecodeov// "LanguageCodeOverride"
0x86a1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x86a6  ldarg.0
0x86a7  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::get_OrganizationWebProxyClient()
0x86ac  callvirt instance int32 Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient::get_LanguageCodeOverride()
0x86b1  box      [mscorlib]System.Int32
0x86b6  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x86bb  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x86c0  ldarg.0
0x86c1  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::get_OrganizationWebProxyClient()
0x86c6  callvirt instance string Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient::get_SyncOperationType()
0x86cb  brfalse.s loc_86F6
0x86cd  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x86d2  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x86d7  ldstr    aOutlooksyncope// "OutlookSyncOperationType"
0x86dc  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x86e1  ldarg.0
0x86e2  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::get_OrganizationWebProxyClient()
0x86e7  callvirt instance string Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient::get_SyncOperationType()
0x86ec  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x86f1  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x86f6  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x86fb  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x8700  ldstr    aUsertype// "UserType"
0x8705  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x870a  ldarg.0
0x870b  call     instance class Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClientContextInitializer::get_OrganizationWebProxyClient()
0x8710  callvirt instance valuetype Microsoft.Xrm.Sdk.WebServiceClient.UserType Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient::get_userType()
0x8715  box      Microsoft.Xrm.Sdk.WebServiceClient.UserType
0x871a  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x871f  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x8724  ldarg.0
0x8725  call     instance void class Microsoft.Xrm.Sdk.WebServiceClient.WebProxyClientContextInitializer`1<class Microsoft.Xrm.Sdk.IOrganizationService>::AddCommonHeaders()
0x872a  ret
```
