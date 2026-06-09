# Microsoft.Xrm.Sdk.Messages.DeleteOptionValueRequest::.ctor

- ea: `0xf4b0`
- end: `0xf4c9`
- name: `Microsoft.Xrm.Sdk.Messages.DeleteOptionValueRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xf440`

## string_xrefs

- `0xf4b7`: `DeleteOptionValue`

## pseudocode

```c

```

## disassembly

```asm
0xf4b0  ldarg.0
0xf4b1  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xf4b6  ldarg.0
0xf4b7  ldstr    aDeleteoptionva// "DeleteOptionValue"
0xf4bc  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xf4c1  ldarg.0
0xf4c2  ldc.i4.0
0xf4c3  call     instance void Microsoft.Xrm.Sdk.Messages.DeleteOptionValueRequest::set_Value(int32 value)
0xf4c8  ret
```
