# Microsoft.Crm.Asynchronous.ImportOperation::GetTotalNumberOfRecords

- ea: `0xba70`
- end: `0xba89`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::GetTotalNumberOfRecords`
- size: `25`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xe550`
- `0x10b00`
- `0x16f30`
- `0x17420`
- `0x17750`
- `0x19b90`
- `0x1b1e0`
- `0x1ba20`
- `0x1c080`
- `0x1c630`

## callees

- `0x4560`

## pseudocode

```c

```

## disassembly

```asm
0xba70  ldstr    aSelectMaxSnFro// "SELECT MAX(SN) FROM "
0xba75  ldarg.1
0xba76  call     string [mscorlib]System.String::Concat(string, string)
0xba7b  stloc.0
0xba7c  ldarg.0
0xba7d  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xba82  ldloc.0
0xba83  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSQLStringWithValue(string command)
0xba88  ret
```
