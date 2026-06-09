# Microsoft.Crm.Asynchronous.TransactionLogBackupData::get_LastBackupDateTime

- ea: `0xacf0`
- end: `0xacf7`
- name: `Microsoft.Crm.Asynchronous.TransactionLogBackupData::get_LastBackupDateTime`
- size: `7`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0xdde0`
- `0xde50`
- `0xdee0`
- `0xdf60`
- `0xfa10`

## pseudocode

```c

```

## disassembly

```asm
0xacf0  ldarg.0
0xacf1  ldfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Asynchronous.TransactionLogBackupData::<LastBackupDateTime>k__BackingField
0xacf6  ret
```
