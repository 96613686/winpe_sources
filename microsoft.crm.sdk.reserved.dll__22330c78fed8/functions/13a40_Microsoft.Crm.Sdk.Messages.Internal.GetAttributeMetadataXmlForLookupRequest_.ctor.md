# Microsoft.Crm.Sdk.Messages.Internal.GetAttributeMetadataXmlForLookupRequest::.ctor

- ea: `0x13a40`
- end: `0x13a59`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetAttributeMetadataXmlForLookupRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x13a20`

## string_xrefs

- `0x13a47`: `GetAttributeMetadataXmlForLookup`

## pseudocode

```c

```

## disassembly

```asm
0x13a40  ldarg.0
0x13a41  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x13a46  ldarg.0
0x13a47  ldstr    aGetattributeme// "GetAttributeMetadataXmlForLookup"
0x13a4c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x13a51  ldarg.0
0x13a52  ldnull
0x13a53  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetAttributeMetadataXmlForLookupRequest::set_entityName(string value)
0x13a58  ret
```
