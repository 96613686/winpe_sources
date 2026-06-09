# Microsoft.Xrm.Sdk.Messages.DeleteRelationshipRequest::.ctor

- ea: `0xf550`
- end: `0xf569`
- name: `Microsoft.Xrm.Sdk.Messages.DeleteRelationshipRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xf530`

## string_xrefs

- `0xf557`: `DeleteRelationship`

## pseudocode

```c

```

## disassembly

```asm
0xf550  ldarg.0
0xf551  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xf556  ldarg.0
0xf557  ldstr    aDeleterelation// "DeleteRelationship"
0xf55c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xf561  ldarg.0
0xf562  ldnull
0xf563  call     instance void Microsoft.Xrm.Sdk.Messages.DeleteRelationshipRequest::set_Name(string value)
0xf568  ret
```
