# Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::TryRetrieveMetadata

- ea: `0x19960`
- end: `0x19985`
- name: `Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::TryRetrieveMetadata`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x196a0`

## callees

- `0x176b0`
- `0x19960`
- `0x19c50`
- `0x19c70`

## pseudocode

```c

```

## disassembly

```asm
0x19960  ldc.i4.1
0x19961  stloc.0
0x19962  ldarg.2
0x19963  ldarg.0
0x19964  ldarg.1
0x19965  ldc.i4.1
0x19966  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.MetadataSet [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClient::GetMetadata(class [System]System.Uri, valuetype [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClientMode)
0x1996b  callvirt instance void Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::set_ServiceMetadata(class [System.ServiceModel]System.ServiceModel.Description.MetadataSet value)
0x19970  ldarg.2
0x19971  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceUrls Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceUrls()
0x19976  ldc.i4.1
0x19977  callvirt instance void Microsoft.Xrm.Sdk.Client.ServiceUrls::set_GeneratedFromAlternate(bool value)
0x1997c  ldc.i4.0
0x1997d  stloc.0
0x1997e  leave.s  loc_19983
0x19980  pop
0x19981  leave.s  loc_19983
0x19983  ldloc.0
0x19984  ret
```
