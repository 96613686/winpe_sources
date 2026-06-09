# Microsoft.Xrm.Sdk.Messages.UpdateStateValueRequest::.ctor

- ea: `0x11a40`
- end: `0x11a60`
- name: `Microsoft.Xrm.Sdk.Messages.UpdateStateValueRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0x118d0`
- `0x119c0`

## string_xrefs

- `0x11a47`: `UpdateStateValue`

## pseudocode

```c

```

## disassembly

```asm
0x11a40  ldarg.0
0x11a41  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x11a46  ldarg.0
0x11a47  ldstr    aUpdatestateval// "UpdateStateValue"
0x11a4c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0x11a51  ldarg.0
0x11a52  ldc.i4.0
0x11a53  call     instance void Microsoft.Xrm.Sdk.Messages.UpdateStateValueRequest::set_Value(int32 value)
0x11a58  ldarg.0
0x11a59  ldc.i4.0
0x11a5a  call     instance void Microsoft.Xrm.Sdk.Messages.UpdateStateValueRequest::set_MergeLabels(bool value)
0x11a5f  ret
```
