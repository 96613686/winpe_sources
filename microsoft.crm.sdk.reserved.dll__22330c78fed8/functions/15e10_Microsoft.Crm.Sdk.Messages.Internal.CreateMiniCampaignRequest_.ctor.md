# Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::.ctor

- ea: `0x15e10`
- end: `0x15e8d`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::.ctor`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x159b0`
- `0x15a10`
- `0x15a60`
- `0x15ab0`
- `0x15b00`
- `0x15b50`
- `0x15ba0`
- `0x15bf0`
- `0x15c40`
- `0x15c90`
- `0x15cf0`
- `0x15d40`
- `0x15d90`

## string_xrefs

- `0x15e17`: `CreateMiniCampaign`

## pseudocode

```c

```

## disassembly

```asm
0x15e10  ldarg.0
0x15e11  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x15e16  ldarg.0
0x15e17  ldstr    aCreateminicamp// "CreateMiniCampaign"
0x15e1c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x15e21  ldarg.0
0x15e22  ldc.i4.0
0x15e23  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_MiniCampaignForTypeCode(int32 value)
0x15e28  ldarg.0
0x15e29  ldloca.s 0
0x15e2b  initobj  [mscorlib]System.Guid
0x15e31  ldloc.0
0x15e32  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_TemplateId(valuetype [mscorlib]System.Guid value)
0x15e37  ldarg.0
0x15e38  ldc.i4.0
0x15e39  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_TargetOption(int32 value)
0x15e3e  ldarg.0
0x15e3f  ldnull
0x15e40  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_TargetIds(string value)
0x15e45  ldarg.0
0x15e46  ldnull
0x15e47  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_FetchXml(string value)
0x15e4c  ldarg.0
0x15e4d  ldnull
0x15e4e  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_MiniCampaignType(string value)
0x15e53  ldarg.0
0x15e54  ldc.i4.0
0x15e55  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_ActivitiesOwnerOption(int32 value)
0x15e5a  ldarg.0
0x15e5b  ldnull
0x15e5c  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_ActivityXml(string value)
0x15e61  ldarg.0
0x15e62  ldnull
0x15e63  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_MiniCampaignName(string value)
0x15e68  ldarg.0
0x15e69  ldc.i4.0
0x15e6a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_PostWorkflowEvent(bool value)
0x15e6f  ldarg.0
0x15e70  ldloca.s 0
0x15e72  initobj  [mscorlib]System.Guid
0x15e78  ldloc.0
0x15e79  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_OwnerId(valuetype [mscorlib]System.Guid value)
0x15e7e  ldarg.0
0x15e7f  ldc.i4.0
0x15e80  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_OwnerTypeCode(int32 value)
0x15e85  ldarg.0
0x15e86  ldc.i4.0
0x15e87  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_sendEmail(bool value)
0x15e8c  ret
```
