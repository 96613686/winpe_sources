# Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::GetNearestPostponeTime

- ea: `0xcf50`
- end: `0xcf6b`
- name: `Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::GetNearestPostponeTime`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xced0`

## callees

- `0xcf50`
- `0xcf70`
- `0xcfa0`

## pseudocode

```c

```

## disassembly

```asm
0xcf50  ldarg.0
0xcf51  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::GetPostponeTimeOfFailedJobs()
0xcf56  stloc.0
0xcf57  ldarg.0
0xcf58  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::GetPostponeTimeForMoreRecords()
0xcf5d  stloc.1
0xcf5e  ldloc.1
0xcf5f  ldloc.0
0xcf60  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xcf65  brtrue.s loc_CF69
0xcf67  ldloc.0
0xcf68  ret
0xcf69  ldloc.1
0xcf6a  ret
```
