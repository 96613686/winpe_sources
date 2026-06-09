# Microsoft.Crm.Sdk.Messages.Internal.GetFieldAndPropertiesXmlRequest::.ctor

- ea: `0x144b0`
- end: `0x144d0`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetFieldAndPropertiesXmlRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14440`
- `0x14490`

## string_xrefs

- `0x144b7`: `GetFieldAndPropertiesXml`

## pseudocode

```c

```

## disassembly

```asm
0x144b0  ldarg.0
0x144b1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x144b6  ldarg.0
0x144b7  ldstr    aGetfieldandpro// "GetFieldAndPropertiesXml"
0x144bc  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x144c1  ldarg.0
0x144c2  ldc.i4.0
0x144c3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetFieldAndPropertiesXmlRequest::set_EntityTypeCode(int32 value)
0x144c8  ldarg.0
0x144c9  ldnull
0x144ca  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetFieldAndPropertiesXmlRequest::set_FetchXml(string value)
0x144cf  ret
```
