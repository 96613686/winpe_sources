# Microsoft.Xrm.Sdk.Messages.CreateCustomerRelationshipsRequest::.ctor

- ea: `0x13010`
- end: `0x13030`
- name: `Microsoft.Xrm.Sdk.Messages.CreateCustomerRelationshipsRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0x12f50`
- `0x12fa0`

## string_xrefs

- `0x13017`: `CreateCustomerRelationships`

## pseudocode

```c

```

## disassembly

```asm
0x13010  ldarg.0
0x13011  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x13016  ldarg.0
0x13017  ldstr    aCreatecustomer// "CreateCustomerRelationships"
0x1301c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0x13021  ldarg.0
0x13022  ldnull
0x13023  call     instance void Microsoft.Xrm.Sdk.Messages.CreateCustomerRelationshipsRequest::set_Lookup(class Microsoft.Xrm.Sdk.Metadata.LookupAttributeMetadata value)
0x13028  ldarg.0
0x13029  ldnull
0x1302a  call     instance void Microsoft.Xrm.Sdk.Messages.CreateCustomerRelationshipsRequest::set_OneToManyRelationships(class Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata[] value)
0x1302f  ret
```
