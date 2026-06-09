# Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::GetPostponeTimeOfFailedJobs

- ea: `0xcf70`
- end: `0xcf94`
- name: `Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::GetPostponeTimeOfFailedJobs`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xcf50`

## callees

- `0xcf70`
- `0xcfe0`
- `0xd010`

## pseudocode

```c

```

## disassembly

```asm
0xcf70  ldarg.0
0xcf71  ldfld    class Microsoft.Crm.Asynchronous.Rollups.JobSelector Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::_selector
0xcf76  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Asynchronous.Rollups.JobSelector::get_NearestPostponeTime()
0xcf7b  stloc.0
0xcf7c  ldloca.s 0
0xcf7e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xcf83  brfalse.s loc_CF8D
0xcf85  ldloca.s 0
0xcf87  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0xcf8c  ret
0xcf8d  ldarg.0
0xcf8e  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::get_DateTimeEpoch()
0xcf93  ret
```
