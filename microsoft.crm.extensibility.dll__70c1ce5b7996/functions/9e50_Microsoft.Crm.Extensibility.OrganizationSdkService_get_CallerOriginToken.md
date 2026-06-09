# Microsoft.Crm.Extensibility.OrganizationSdkService::get_CallerOriginToken

- ea: `0x9e50`
- end: `0x9ea4`
- name: `Microsoft.Crm.Extensibility.OrganizationSdkService::get_CallerOriginToken`
- size: `84`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4f00`
- `0x9ee0`
- `0xa030`
- `0xa0c0`
- `0xa210`
- `0xa250`
- `0xa270`
- `0xa290`
- `0xa2b0`
- `0x24aa0`

## callees

- `0x9e50`

## string_xrefs

- `0x9e66`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x9e82`: `http://schemas.microsoft.com/xrm/2011/Contracts`

## pseudocode

```c

```

## disassembly

```asm
0x9e50  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x9e55  brfalse.s loc_9E9E
0x9e57  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x9e5c  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageHeaders()
0x9e61  ldstr    aIsofflineplayb// "IsOfflinePlayback"
0x9e66  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x9e6b  callvirt instance int32 [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::FindHeader(string, string)
0x9e70  ldc.i4.0
0x9e71  blt.s    loc_9E9E
0x9e73  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x9e78  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageHeaders()
0x9e7d  ldstr    aIsofflineplayb// "IsOfflinePlayback"
0x9e82  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x9e87  callvirt T0x2B00003D
0x9e8c  brfalse.s loc_9E9E
0x9e8e  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_Now()
0x9e93  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OfflineOrigin::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0x9e98  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0x9e9d  ret
0x9e9e  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::get_WebServiceApi()
0x9ea3  ret
```
