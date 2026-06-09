# Microsoft.Crm.Sdk.Messages.Internal.GetLookupValuesXmlRequest::.ctor

- ea: `0x13e80`
- end: `0x13ea0`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetLookupValuesXmlRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x13e10`
- `0x13e60`

## string_xrefs

- `0x13e87`: `GetLookupValuesXml`

## pseudocode

```c

```

## disassembly

```asm
0x13e80  ldarg.0
0x13e81  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x13e86  ldarg.0
0x13e87  ldstr    aGetlookupvalue// "GetLookupValuesXml"
0x13e8c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x13e91  ldarg.0
0x13e92  ldc.i4.0
0x13e93  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetLookupValuesXmlRequest::set_entityTypeCode(int32 value)
0x13e98  ldarg.0
0x13e99  ldnull
0x13e9a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetLookupValuesXmlRequest::set_attributeLogicalName(string value)
0x13e9f  ret
```
