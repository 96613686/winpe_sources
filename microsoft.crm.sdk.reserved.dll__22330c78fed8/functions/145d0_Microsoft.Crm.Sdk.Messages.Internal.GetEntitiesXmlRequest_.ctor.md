# Microsoft.Crm.Sdk.Messages.Internal.GetEntitiesXmlRequest::.ctor

- ea: `0x145d0`
- end: `0x145f0`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetEntitiesXmlRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14560`
- `0x145b0`

## string_xrefs

- `0x145d7`: `GetEntitiesXml`

## pseudocode

```c

```

## disassembly

```asm
0x145d0  ldarg.0
0x145d1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x145d6  ldarg.0
0x145d7  ldstr    aGetentitiesxml// "GetEntitiesXml"
0x145dc  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x145e1  ldarg.0
0x145e2  ldc.i4.0
0x145e3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetEntitiesXmlRequest::set_EntityTypeCode(int32 value)
0x145e8  ldarg.0
0x145e9  ldnull
0x145ea  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetEntitiesXmlRequest::set_FetchXml(string value)
0x145ef  ret
```
