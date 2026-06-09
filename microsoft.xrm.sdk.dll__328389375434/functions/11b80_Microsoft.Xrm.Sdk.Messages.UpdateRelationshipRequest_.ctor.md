# Microsoft.Xrm.Sdk.Messages.UpdateRelationshipRequest::.ctor

- ea: `0x11b80`
- end: `0x11ba0`
- name: `Microsoft.Xrm.Sdk.Messages.UpdateRelationshipRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0x11ac0`
- `0x11b10`

## string_xrefs

- `0x11b87`: `UpdateRelationship`

## pseudocode

```c

```

## disassembly

```asm
0x11b80  ldarg.0
0x11b81  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x11b86  ldarg.0
0x11b87  ldstr    aUpdaterelation// "UpdateRelationship"
0x11b8c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0x11b91  ldarg.0
0x11b92  ldnull
0x11b93  call     instance void Microsoft.Xrm.Sdk.Messages.UpdateRelationshipRequest::set_Relationship(class Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase value)
0x11b98  ldarg.0
0x11b99  ldc.i4.0
0x11b9a  call     instance void Microsoft.Xrm.Sdk.Messages.UpdateRelationshipRequest::set_MergeLabels(bool value)
0x11b9f  ret
```
