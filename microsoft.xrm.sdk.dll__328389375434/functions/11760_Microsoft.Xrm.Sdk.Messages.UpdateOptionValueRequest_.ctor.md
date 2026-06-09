# Microsoft.Xrm.Sdk.Messages.UpdateOptionValueRequest::.ctor

- ea: `0x11760`
- end: `0x11780`
- name: `Microsoft.Xrm.Sdk.Messages.UpdateOptionValueRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0x115b0`
- `0x116a0`

## string_xrefs

- `0x11767`: `UpdateOptionValue`

## pseudocode

```c

```

## disassembly

```asm
0x11760  ldarg.0
0x11761  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x11766  ldarg.0
0x11767  ldstr    aUpdateoptionva// "UpdateOptionValue"
0x1176c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0x11771  ldarg.0
0x11772  ldc.i4.0
0x11773  call     instance void Microsoft.Xrm.Sdk.Messages.UpdateOptionValueRequest::set_Value(int32 value)
0x11778  ldarg.0
0x11779  ldc.i4.0
0x1177a  call     instance void Microsoft.Xrm.Sdk.Messages.UpdateOptionValueRequest::set_MergeLabels(bool value)
0x1177f  ret
```
