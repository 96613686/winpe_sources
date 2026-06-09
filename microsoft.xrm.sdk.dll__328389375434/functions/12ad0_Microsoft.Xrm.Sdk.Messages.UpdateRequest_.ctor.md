# Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor

- ea: `0x12ad0`
- end: `0x12ae9`
- name: `Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14640`

## callees

- `0x3670`
- `0x36a0`
- `0x12a60`

## string_xrefs

- `0x12ad7`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x12ad0  ldarg.0
0x12ad1  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x12ad6  ldarg.0
0x12ad7  ldstr    aUpdate// "Update"
0x12adc  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0x12ae1  ldarg.0
0x12ae2  ldnull
0x12ae3  call     instance void Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class Microsoft.Xrm.Sdk.Entity value)
0x12ae8  ret
```
