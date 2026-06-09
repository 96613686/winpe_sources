# Microsoft.Crm.Sdk.Messages.Internal.GetEmailLinkTrackingUrlsRequest::.ctor

- ea: `0x73e0`
- end: `0x741e`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetEmailLinkTrackingUrlsRequest::.ctor`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x72c0`
- `0x7320`
- `0x7370`
- `0x73c0`

## string_xrefs

- `0x73e7`: `GetEmailLinkTrackingUrls`

## pseudocode

```c

```

## disassembly

```asm
0x73e0  ldarg.0
0x73e1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x73e6  ldarg.0
0x73e7  ldstr    aGetemaillinktr// "GetEmailLinkTrackingUrls"
0x73ec  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x73f1  ldarg.0
0x73f2  ldloca.s 0
0x73f4  initobj  [mscorlib]System.Guid
0x73fa  ldloc.0
0x73fb  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetEmailLinkTrackingUrlsRequest::set_TrackingId(valuetype [mscorlib]System.Guid value)
0x7400  ldarg.0
0x7401  ldloca.s 0
0x7403  initobj  [mscorlib]System.Guid
0x7409  ldloc.0
0x740a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetEmailLinkTrackingUrlsRequest::set_ConversationTrackingId(valuetype [mscorlib]System.Guid value)
0x740f  ldarg.0
0x7410  ldnull
0x7411  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetEmailLinkTrackingUrlsRequest::set_ClientType(string value)
0x7416  ldarg.0
0x7417  ldnull
0x7418  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetEmailLinkTrackingUrlsRequest::set_EmailLinkUrls(string[] value)
0x741d  ret
```
