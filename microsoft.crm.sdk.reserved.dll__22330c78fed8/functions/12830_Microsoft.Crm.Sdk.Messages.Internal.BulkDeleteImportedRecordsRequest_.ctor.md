# Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::.ctor

- ea: `0x12830`
- end: `0x12889`
- name: `Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::.ctor`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x12520`
- `0x12570`
- `0x125d0`
- `0x12620`
- `0x12670`
- `0x126c0`
- `0x12710`
- `0x12760`
- `0x127b0`

## string_xrefs

- `0x12837`: `BulkDeleteImportedRecords`

## pseudocode

```c

```

## disassembly

```asm
0x12830  ldarg.0
0x12831  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x12836  ldarg.0
0x12837  ldstr    aBulkdeleteimpo// "BulkDeleteImportedRecords"
0x1283c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x12841  ldarg.0
0x12842  ldnull
0x12843  call     instance void Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::set_TargetEntityName(string value)
0x12848  ldarg.0
0x12849  ldc.i4.0
0x1284a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::set_ImportSequenceNumber(int32 value)
0x1284f  ldarg.0
0x12850  ldloca.s 0
0x12852  initobj  [mscorlib]System.Guid
0x12858  ldloc.0
0x12859  call     instance void Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::set_ImportId(valuetype [mscorlib]System.Guid value)
0x1285e  ldarg.0
0x1285f  ldc.i4.0
0x12860  call     instance void Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::set_DeleteImportHistory(bool value)
0x12865  ldarg.0
0x12866  ldnull
0x12867  call     instance void Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::set_JobName(string value)
0x1286c  ldarg.0
0x1286d  ldc.i4.0
0x1286e  call     instance void Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::set_SendEmailNotification(bool value)
0x12873  ldarg.0
0x12874  ldnull
0x12875  call     instance void Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::set_ToRecipients(string value)
0x1287a  ldarg.0
0x1287b  ldnull
0x1287c  call     instance void Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::set_CCRecipients(string value)
0x12881  ldarg.0
0x12882  ldnull
0x12883  call     instance void Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::set_RecurrencePattern(string value)
0x12888  ret
```
