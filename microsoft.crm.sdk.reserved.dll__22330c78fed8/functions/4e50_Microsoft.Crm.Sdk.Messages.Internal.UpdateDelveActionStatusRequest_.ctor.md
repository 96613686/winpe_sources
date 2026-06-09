# Microsoft.Crm.Sdk.Messages.Internal.UpdateDelveActionStatusRequest::.ctor

- ea: `0x4e50`
- end: `0x4e77`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateDelveActionStatusRequest::.ctor`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4d90`
- `0x4de0`
- `0x4e30`

## string_xrefs

- `0x4e57`: `UpdateDelveActionStatus`

## pseudocode

```c

```

## disassembly

```asm
0x4e50  ldarg.0
0x4e51  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x4e56  ldarg.0
0x4e57  ldstr    aUpdatedelveact// "UpdateDelveActionStatus"
0x4e5c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x4e61  ldarg.0
0x4e62  ldnull
0x4e63  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateDelveActionStatusRequest::set_MessageId(string value)
0x4e68  ldarg.0
0x4e69  ldc.i4.0
0x4e6a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateDelveActionStatusRequest::set_ActionState(int32 value)
0x4e6f  ldarg.0
0x4e70  ldnull
0x4e71  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateDelveActionStatusRequest::set_RecordId(string value)
0x4e76  ret
```
