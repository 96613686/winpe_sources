# Microsoft.Xrm.Sdk.Messages.DeleteEntityRequest::.ctor

- ea: `0xf2d0`
- end: `0xf2e9`
- name: `Microsoft.Xrm.Sdk.Messages.DeleteEntityRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xf2b0`

## string_xrefs

- `0xf2d7`: `DeleteEntity`

## pseudocode

```c

```

## disassembly

```asm
0xf2d0  ldarg.0
0xf2d1  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xf2d6  ldarg.0
0xf2d7  ldstr    aDeleteentity// "DeleteEntity"
0xf2dc  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xf2e1  ldarg.0
0xf2e2  ldnull
0xf2e3  call     instance void Microsoft.Xrm.Sdk.Messages.DeleteEntityRequest::set_LogicalName(string value)
0xf2e8  ret
```
