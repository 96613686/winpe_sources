# Microsoft.Crm.Sdk.Messages.Internal.AddMembersByFetchXmlListRequest::set_FetchXml

- ea: `0x15360`
- end: `0x15372`
- name: `Microsoft.Crm.Sdk.Messages.Internal.AddMembersByFetchXmlListRequest::set_FetchXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15380`

## string_xrefs

- `0x15366`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x15360  ldarg.0
0x15361  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x15366  ldstr    aFetchxml// "FetchXml"
0x1536b  ldarg.1
0x1536c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x15371  ret
```
