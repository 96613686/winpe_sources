# Microsoft.Xrm.Sdk.Messages.DeleteRequest::.ctor

- ea: `0x127f0`
- end: `0x12809`
- name: `Microsoft.Xrm.Sdk.Messages.DeleteRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x141d0`

## callees

- `0x3670`
- `0x36a0`
- `0x12780`

## string_xrefs

- `0x127f7`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x127f0  ldarg.0
0x127f1  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x127f6  ldarg.0
0x127f7  ldstr    aDelete// "Delete"
0x127fc  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0x12801  ldarg.0
0x12802  ldnull
0x12803  call     instance void Microsoft.Xrm.Sdk.Messages.DeleteRequest::set_Target(class Microsoft.Xrm.Sdk.EntityReference value)
0x12808  ret
```
