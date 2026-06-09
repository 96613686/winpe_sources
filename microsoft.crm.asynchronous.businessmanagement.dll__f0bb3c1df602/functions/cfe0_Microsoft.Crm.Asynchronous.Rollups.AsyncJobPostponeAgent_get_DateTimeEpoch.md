# Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::get_DateTimeEpoch

- ea: `0xcfe0`
- end: `0xcfee`
- name: `Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::get_DateTimeEpoch`
- size: `14`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xced0`
- `0xcf70`
- `0xcfa0`

## pseudocode

```c

```

## disassembly

```asm
0xcfe0  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0xcfe5  stloc.0
0xcfe6  ldloca.s 0
0xcfe8  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0xcfed  ret
```
