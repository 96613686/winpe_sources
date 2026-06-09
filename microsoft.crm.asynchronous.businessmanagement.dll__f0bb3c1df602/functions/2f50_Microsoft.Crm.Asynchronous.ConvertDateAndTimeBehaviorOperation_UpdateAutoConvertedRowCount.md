# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateAutoConvertedRowCount

- ea: `0x2f50`
- end: `0x2f6c`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateAutoConvertedRowCount`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2ed0`

## callees

- `0x13b40`
- `0x13b50`

## pseudocode

```c

```

## disassembly

```asm
0x2f50  ldarg.0
0x2f51  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo> Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::jobSummaryItems
0x2f56  ldarg.1
0x2f57  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo>::get_Item(void)
0x2f5c  dup
0x2f5d  callvirt instance int32 RowLevelInfo::get_AutoConvertedRows()
0x2f62  stloc.0
0x2f63  ldloc.0
0x2f64  ldc.i4.1
0x2f65  add
0x2f66  callvirt instance void RowLevelInfo::set_AutoConvertedRows(int32 value)
0x2f6b  ret
```
