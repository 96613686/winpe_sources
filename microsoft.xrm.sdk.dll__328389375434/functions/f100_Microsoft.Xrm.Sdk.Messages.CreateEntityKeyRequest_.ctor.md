# Microsoft.Xrm.Sdk.Messages.CreateEntityKeyRequest::.ctor

- ea: `0xf100`
- end: `0xf120`
- name: `Microsoft.Xrm.Sdk.Messages.CreateEntityKeyRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xf040`
- `0xf090`

## string_xrefs

- `0xf107`: `CreateEntityKey`

## pseudocode

```c

```

## disassembly

```asm
0xf100  ldarg.0
0xf101  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xf106  ldarg.0
0xf107  ldstr    aCreateentityke// "CreateEntityKey"
0xf10c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xf111  ldarg.0
0xf112  ldnull
0xf113  call     instance void Microsoft.Xrm.Sdk.Messages.CreateEntityKeyRequest::set_EntityKey(class Microsoft.Xrm.Sdk.Metadata.EntityKeyMetadata value)
0xf118  ldarg.0
0xf119  ldnull
0xf11a  call     instance void Microsoft.Xrm.Sdk.Messages.CreateEntityKeyRequest::set_EntityName(string value)
0xf11f  ret
```
