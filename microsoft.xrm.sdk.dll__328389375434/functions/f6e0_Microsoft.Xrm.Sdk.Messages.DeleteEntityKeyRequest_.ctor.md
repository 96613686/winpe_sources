# Microsoft.Xrm.Sdk.Messages.DeleteEntityKeyRequest::.ctor

- ea: `0xf6e0`
- end: `0xf700`
- name: `Microsoft.Xrm.Sdk.Messages.DeleteEntityKeyRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xf670`
- `0xf6c0`

## string_xrefs

- `0xf6e7`: `DeleteEntityKey`

## pseudocode

```c

```

## disassembly

```asm
0xf6e0  ldarg.0
0xf6e1  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xf6e6  ldarg.0
0xf6e7  ldstr    aDeleteentityke// "DeleteEntityKey"
0xf6ec  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xf6f1  ldarg.0
0xf6f2  ldnull
0xf6f3  call     instance void Microsoft.Xrm.Sdk.Messages.DeleteEntityKeyRequest::set_Name(string value)
0xf6f8  ldarg.0
0xf6f9  ldnull
0xf6fa  call     instance void Microsoft.Xrm.Sdk.Messages.DeleteEntityKeyRequest::set_EntityLogicalName(string value)
0xf6ff  ret
```
