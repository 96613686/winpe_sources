# Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_FetchXml

- ea: `0x15b00`
- end: `0x15b12`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::set_FetchXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15e10`

## string_xrefs

- `0x15b06`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x15b00  ldarg.0
0x15b01  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x15b06  ldstr    aFetchxml// "FetchXml"
0x15b0b  ldarg.1
0x15b0c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x15b11  ret
```
