# Microsoft.Xrm.Sdk.Messages.CreateRequest::.ctor

- ea: `0x126c0`
- end: `0x126d9`
- name: `Microsoft.Xrm.Sdk.Messages.CreateRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14640`

## callees

- `0x3670`
- `0x36a0`
- `0x126a0`

## string_xrefs

- `0x126c7`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x126c0  ldarg.0
0x126c1  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x126c6  ldarg.0
0x126c7  ldstr    aCreate// "Create"
0x126cc  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0x126d1  ldarg.0
0x126d2  ldnull
0x126d3  call     instance void Microsoft.Xrm.Sdk.Messages.CreateRequest::set_Target(class Microsoft.Xrm.Sdk.Entity value)
0x126d8  ret
```
