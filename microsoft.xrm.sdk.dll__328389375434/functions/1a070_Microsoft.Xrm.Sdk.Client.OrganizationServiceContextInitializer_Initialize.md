# Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::Initialize

- ea: `0x1a070`
- end: `0x1a2b6`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::Initialize`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a050`

## callees

- `0x1a060`
- `0x1a070`
- `0x1a300`
- `0x1a320`
- `0x1a340`
- `0x1a360`
- `0x1a380`
- `0x1a3a0`
- `0x1a3c0`
- `0x1a3e0`
- `0x1a400`
- `0x1a4f0`

## string_xrefs

- `0x1a097`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1a0d2`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1a117`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1a152`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1a18d`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1a1c8`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1a203`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1a23e`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1a277`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1a296`: `http://schemas.microsoft.com/xrm/2011/Contracts`

## pseudocode

```c

```

## disassembly

```asm
0x1a070  ldarg.0
0x1a071  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a076  brfalse  loc_1A2B5
0x1a07b  ldarg.0
0x1a07c  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a081  callvirt instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_OfflinePlayback()
0x1a086  brfalse.s loc_1A0AC
0x1a088  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x1a08d  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x1a092  ldstr    aIsofflineplayb// "IsOfflinePlayback"
0x1a097  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1a09c  ldc.i4.1
0x1a09d  box      [mscorlib]System.Boolean
0x1a0a2  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x1a0a7  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x1a0ac  ldarg.0
0x1a0ad  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a0b2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_CallerId()
0x1a0b7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a0bc  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a0c1  brfalse.s loc_1A0F1
0x1a0c3  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x1a0c8  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x1a0cd  ldstr    aCallerid// "CallerId"
0x1a0d2  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1a0d7  ldarg.0
0x1a0d8  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a0dd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_CallerId()
0x1a0e2  box      [mscorlib]System.Guid
0x1a0e7  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x1a0ec  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x1a0f1  ldarg.0
0x1a0f2  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a0f7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_CallerRegardingObjectId()
0x1a0fc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a101  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a106  brfalse.s loc_1A136
0x1a108  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x1a10d  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x1a112  ldstr    aCallerregardin// "CallerRegardingObjectId"
0x1a117  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1a11c  ldarg.0
0x1a11d  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a122  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_CallerRegardingObjectId()
0x1a127  box      [mscorlib]System.Guid
0x1a12c  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x1a131  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x1a136  ldarg.0
0x1a137  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a13c  callvirt instance int32 Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_LanguageCodeOverride()
0x1a141  brfalse.s loc_1A171
0x1a143  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x1a148  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x1a14d  ldstr    aLanguagecodeov// "LanguageCodeOverride"
0x1a152  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1a157  ldarg.0
0x1a158  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a15d  callvirt instance int32 Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_LanguageCodeOverride()
0x1a162  box      [mscorlib]System.Int32
0x1a167  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x1a16c  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x1a171  ldarg.0
0x1a172  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a177  callvirt instance string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_SyncOperationType()
0x1a17c  brfalse.s loc_1A1A7
0x1a17e  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x1a183  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x1a188  ldstr    aOutlooksyncope// "OutlookSyncOperationType"
0x1a18d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1a192  ldarg.0
0x1a193  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a198  callvirt instance string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_SyncOperationType()
0x1a19d  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x1a1a2  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x1a1a7  ldarg.0
0x1a1a8  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a1ad  callvirt instance string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_ClientAppName()
0x1a1b2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a1b7  brtrue.s loc_1A1E2
0x1a1b9  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x1a1be  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x1a1c3  ldstr    aClientappname// "ClientAppName"
0x1a1c8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1a1cd  ldarg.0
0x1a1ce  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a1d3  callvirt instance string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_ClientAppName()
0x1a1d8  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x1a1dd  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x1a1e2  ldarg.0
0x1a1e3  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a1e8  callvirt instance string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_ClientAppVersion()
0x1a1ed  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a1f2  brtrue.s loc_1A21D
0x1a1f4  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x1a1f9  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x1a1fe  ldstr    aClientappversi// "ClientAppVersion"
0x1a203  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1a208  ldarg.0
0x1a209  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a20e  callvirt instance string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_ClientAppVersion()
0x1a213  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x1a218  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x1a21d  ldarg.0
0x1a21e  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a223  callvirt instance string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_SdkClientVersion()
0x1a228  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a22d  brtrue.s loc_1A25A
0x1a22f  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x1a234  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x1a239  ldstr    aSdkclientversi// "SdkClientVersion"
0x1a23e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1a243  ldarg.0
0x1a244  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a249  callvirt instance string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_SdkClientVersion()
0x1a24e  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x1a253  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x1a258  br.s     loc_1A287
0x1a25a  call     string Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::GetXrmSdkAssemblyFileVersion()
0x1a25f  stloc.0
0x1a260  ldloc.0
0x1a261  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a266  brtrue.s loc_1A287
0x1a268  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x1a26d  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x1a272  ldstr    aSdkclientversi// "SdkClientVersion"
0x1a277  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1a27c  ldloc.0
0x1a27d  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x1a282  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x1a287  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x1a28c  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x1a291  ldstr    aUsertype// "UserType"
0x1a296  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1a29b  ldarg.0
0x1a29c  call     instance class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::get_OrganizationServiceProxy()
0x1a2a1  callvirt instance valuetype Microsoft.Xrm.Sdk.Client.UserType Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::get_UserType()
0x1a2a6  box      Microsoft.Xrm.Sdk.Client.UserType
0x1a2ab  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x1a2b0  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x1a2b5  ret
```
