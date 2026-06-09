# Microsoft.Xrm.Sdk.Messages.CreateManyToManyRequest::.ctor

- ea: `0xec90`
- end: `0xecb0`
- name: `Microsoft.Xrm.Sdk.Messages.CreateManyToManyRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xebd0`
- `0xec20`

## string_xrefs

- `0xec97`: `CreateManyToMany`

## pseudocode

```c

```

## disassembly

```asm
0xec90  ldarg.0
0xec91  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xec96  ldarg.0
0xec97  ldstr    aCreatemanytoma// "CreateManyToMany"
0xec9c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xeca1  ldarg.0
0xeca2  ldnull
0xeca3  call     instance void Microsoft.Xrm.Sdk.Messages.CreateManyToManyRequest::set_IntersectEntitySchemaName(string value)
0xeca8  ldarg.0
0xeca9  ldnull
0xecaa  call     instance void Microsoft.Xrm.Sdk.Messages.CreateManyToManyRequest::set_ManyToManyRelationship(class Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata value)
0xecaf  ret
```
