# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateNotConvertedRowsCount

- ea: `0x2f90`
- end: `0x2fac`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateNotConvertedRowsCount`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2ed0`
- `0x3060`

## callees

- `0x13b80`
- `0x13b90`

## pseudocode

```c

```

## disassembly

```asm
0x2f90  ldarg.0
0x2f91  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo> Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::jobSummaryItems
0x2f96  ldarg.1
0x2f97  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo>::get_Item(void)
0x2f9c  dup
0x2f9d  callvirt instance int32 RowLevelInfo::get_NotConvertedRows()
0x2fa2  stloc.0
0x2fa3  ldloc.0
0x2fa4  ldc.i4.1
0x2fa5  add
0x2fa6  callvirt instance void RowLevelInfo::set_NotConvertedRows(int32 value)
0x2fab  ret
```
