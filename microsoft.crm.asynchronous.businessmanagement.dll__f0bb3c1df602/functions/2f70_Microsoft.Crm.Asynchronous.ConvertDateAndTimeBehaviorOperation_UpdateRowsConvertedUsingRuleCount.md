# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateRowsConvertedUsingRuleCount

- ea: `0x2f70`
- end: `0x2f8c`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateRowsConvertedUsingRuleCount`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2ed0`

## callees

- `0x13b60`
- `0x13b70`

## pseudocode

```c

```

## disassembly

```asm
0x2f70  ldarg.0
0x2f71  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo> Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::jobSummaryItems
0x2f76  ldarg.1
0x2f77  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo>::get_Item(void)
0x2f7c  dup
0x2f7d  callvirt instance int32 RowLevelInfo::get_RowsConvertedUsingRule()
0x2f82  stloc.0
0x2f83  ldloc.0
0x2f84  ldc.i4.1
0x2f85  add
0x2f86  callvirt instance void RowLevelInfo::set_RowsConvertedUsingRule(int32 value)
0x2f8b  ret
```
