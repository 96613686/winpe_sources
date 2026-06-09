# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::PerformObjectsCleanup

- ea: `0xf710`
- end: `0xf74d`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::PerformObjectsCleanup`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xedf0`
- `0xf180`

## callees

- `0xe7b0`
- `0xe7d0`
- `0xe7e0`
- `0xe940`

## pseudocode

```c

```

## disassembly

```asm
0xf710  ldarg.0
0xf711  ldarg.0
0xf712  call     instance string Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_MainTableName()
0xf717  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CleanupObjects(string tempTableName)
0xf71c  ldarg.0
0xf71d  ldarg.0
0xf71e  call     instance string Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_SourceTableName()
0xf723  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CleanupObjects(string tempTableName)
0xf728  ldarg.0
0xf729  ldarg.0
0xf72a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf72f  ldc.i4.3
0xf730  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetRollupBootstrapTableName(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.BootstrapTable)
0xf735  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CleanupObjects(string tempTableName)
0xf73a  ldarg.0
0xf73b  ldarg.0
0xf73c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf741  ldc.i4.4
0xf742  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetRollupBootstrapTableName(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.BootstrapTable)
0xf747  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CleanupObjects(string tempTableName)
0xf74c  ret
```
