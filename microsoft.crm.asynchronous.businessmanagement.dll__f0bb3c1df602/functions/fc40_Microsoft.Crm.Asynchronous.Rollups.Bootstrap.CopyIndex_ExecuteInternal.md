# Microsoft.Crm.Asynchronous.Rollups.Bootstrap.CopyIndex::ExecuteInternal

- ea: `0xfc40`
- end: `0xfc6c`
- name: `Microsoft.Crm.Asynchronous.Rollups.Bootstrap.CopyIndex::ExecuteInternal`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0xbf80`
- `0xc990`
- `0xf780`
- `0xfc40`
- `0xfc70`
- `0x100e0`
- `0x10170`
- `0x10180`

## pseudocode

```c

```

## disassembly

```asm
0xfc40  ldarg.0
0xfc41  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::get_Process()
0xfc46  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_DataAccess()
0xfc4b  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_BootstrapRollupSelectBatchSize()
0xfc50  ldarg.0
0xfc51  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.IndexCopyType Microsoft.Crm.Asynchronous.Rollups.Bootstrap.CopyIndex::get_CopyType()
0xfc56  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess::CopyIndex(int32 batchSize, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.IndexCopyType copyType)
0xfc5b  ldc.i4.0
0xfc5c  ble.s    loc_FC65
0xfc5e  ldarg.0
0xfc5f  call     instance int32 Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::ExecutionNotFinished()
0xfc64  ret
0xfc65  ldarg.0
0xfc66  call     instance int32 Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::ExecutionFinished()
0xfc6b  ret
```
