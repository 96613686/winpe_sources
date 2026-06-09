# Microsoft.Crm.Sdk.Messages.Internal.StatusUpdateBulkOperationRequest::.ctor

- ea: `0x16a80`
- end: `0x16aaf`
- name: `Microsoft.Crm.Sdk.Messages.Internal.StatusUpdateBulkOperationRequest::.ctor`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x169c0`
- `0x16a10`
- `0x16a60`

## string_xrefs

- `0x16a87`: `StatusUpdateBulkOperation`

## pseudocode

```c

```

## disassembly

```asm
0x16a80  ldarg.0
0x16a81  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x16a86  ldarg.0
0x16a87  ldstr    aStatusupdatebu// "StatusUpdateBulkOperation"
0x16a8c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x16a91  ldarg.0
0x16a92  ldloca.s 0
0x16a94  initobj  [mscorlib]System.Guid
0x16a9a  ldloc.0
0x16a9b  call     instance void Microsoft.Crm.Sdk.Messages.Internal.StatusUpdateBulkOperationRequest::set_BulkOperationId(valuetype [mscorlib]System.Guid value)
0x16aa0  ldarg.0
0x16aa1  ldc.i4.0
0x16aa2  call     instance void Microsoft.Crm.Sdk.Messages.Internal.StatusUpdateBulkOperationRequest::set_FailureCount(int32 value)
0x16aa7  ldarg.0
0x16aa8  ldc.i4.0
0x16aa9  call     instance void Microsoft.Crm.Sdk.Messages.Internal.StatusUpdateBulkOperationRequest::set_SuccessCount(int32 value)
0x16aae  ret
```
