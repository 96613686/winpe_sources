# Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::GetPostponeTimeForMoreRecords

- ea: `0xcfa0`
- end: `0xcfe0`
- name: `Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::GetPostponeTimeForMoreRecords`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0xcf50`

## callees

- `0xc850`
- `0xcfa0`
- `0xcfe0`
- `0xd000`
- `0xd020`
- `0xd120`

## pseudocode

```c

```

## disassembly

```asm
0xcfa0  ldarg.0
0xcfa1  ldfld    class Microsoft.Crm.Asynchronous.Rollups.JobSelector Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::_selector
0xcfa6  callvirt instance void Microsoft.Crm.Asynchronous.Rollups.JobSelector::Dispose()
0xcfab  ldarg.0
0xcfac  ldfld    class Microsoft.Crm.Asynchronous.Rollups.JobSelector Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::_selector
0xcfb1  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.JobSelector::get_NumberOfJobsDisposed()
0xcfb6  ldc.i4.0
0xcfb7  bgt.s    loc_CFC6
0xcfb9  ldarg.0
0xcfba  ldfld    class Microsoft.Crm.Asynchronous.Rollups.JobSelector Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::_selector
0xcfbf  callvirt instance bool Microsoft.Crm.Asynchronous.Rollups.JobSelector::get_AreJobsPending()
0xcfc4  br.s     loc_CFC7
0xcfc6  ldc.i4.1
0xcfc7  brfalse.s loc_CFD9
0xcfc9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xcfce  call     valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_IncrementalRollupSelfPostponeInterval()
0xcfd3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xcfd8  ret
0xcfd9  ldarg.0
0xcfda  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.AsyncJobPostponeAgent::get_DateTimeEpoch()
0xcfdf  ret
```
