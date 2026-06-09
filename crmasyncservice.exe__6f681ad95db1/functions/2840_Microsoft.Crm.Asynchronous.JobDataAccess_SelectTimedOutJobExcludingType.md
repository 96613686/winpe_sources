# Microsoft.Crm.Asynchronous.JobDataAccess::SelectTimedOutJobExcludingType

- ea: `0x2840`
- end: `0x2858`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::SelectTimedOutJobExcludingType`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2860`

## pseudocode

```c

```

## disassembly

```asm
0x2840  ldarg.0
0x2841  ldarg.1
0x2842  ldstr    aAndOperationty_0// " AND OperationType <> {0}"
0x2847  ldarg.2
0x2848  box      [mscorlib]System.Int32
0x284d  call     string [mscorlib]System.String::Format(string, object)
0x2852  call     instance class Microsoft.Crm.Asynchronous.AsyncJob Microsoft.Crm.Asynchronous.JobDataAccess::SelectTimedOutJobInternal(valuetype [mscorlib]System.TimeSpan jobMaxExecutionTime, [opt] string operationTypeClause)
0x2857  ret
```
