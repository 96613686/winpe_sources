# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_MainTableName

- ea: `0xe7e0`
- end: `0xe7ed`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_MainTableName`
- size: `13`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf370`
- `0xf3f0`
- `0xf710`

## callees

- `0xe7b0`

## pseudocode

```c

```

## disassembly

```asm
0xe7e0  ldarg.0
0xe7e1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xe7e6  ldc.i4.1
0xe7e7  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetRollupBootstrapTableName(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.BootstrapTable)
0xe7ec  ret
```
