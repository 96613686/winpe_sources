# Microsoft.Xrm.Sdk.Messages.DeleteOptionSetRequest::.ctor

- ea: `0xf5f0`
- end: `0xf609`
- name: `Microsoft.Xrm.Sdk.Messages.DeleteOptionSetRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xf5d0`

## string_xrefs

- `0xf5f7`: `DeleteOptionSet`

## pseudocode

```c

```

## disassembly

```asm
0xf5f0  ldarg.0
0xf5f1  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xf5f6  ldarg.0
0xf5f7  ldstr    aDeleteoptionse// "DeleteOptionSet"
0xf5fc  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xf601  ldarg.0
0xf602  ldnull
0xf603  call     instance void Microsoft.Xrm.Sdk.Messages.DeleteOptionSetRequest::set_Name(string value)
0xf608  ret
```
