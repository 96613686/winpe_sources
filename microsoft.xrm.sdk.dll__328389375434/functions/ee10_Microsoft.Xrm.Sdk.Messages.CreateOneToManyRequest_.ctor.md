# Microsoft.Xrm.Sdk.Messages.CreateOneToManyRequest::.ctor

- ea: `0xee10`
- end: `0xee30`
- name: `Microsoft.Xrm.Sdk.Messages.CreateOneToManyRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xed50`
- `0xeda0`

## string_xrefs

- `0xee17`: `CreateOneToMany`

## pseudocode

```c

```

## disassembly

```asm
0xee10  ldarg.0
0xee11  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xee16  ldarg.0
0xee17  ldstr    aCreateonetoman// "CreateOneToMany"
0xee1c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xee21  ldarg.0
0xee22  ldnull
0xee23  call     instance void Microsoft.Xrm.Sdk.Messages.CreateOneToManyRequest::set_Lookup(class Microsoft.Xrm.Sdk.Metadata.LookupAttributeMetadata value)
0xee28  ldarg.0
0xee29  ldnull
0xee2a  call     instance void Microsoft.Xrm.Sdk.Messages.CreateOneToManyRequest::set_OneToManyRelationship(class Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata value)
0xee2f  ret
```
