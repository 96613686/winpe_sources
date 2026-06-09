# Microsoft.Crm.Asynchronous.Rollups.JobSelector::MoveNext

- ea: `0xd0b0`
- end: `0xd10f`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelector::MoveNext`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xc310`
- `0x10800`

## callees

- `0xc830`
- `0xc890`
- `0xd040`
- `0xd050`
- `0xd0b0`
- `0xd190`

## pseudocode

```c

```

## disassembly

```asm
0xd0b0  ldarg.0
0xd0b1  ldfld    bool Microsoft.Crm.Asynchronous.Rollups.JobSelector::_isDisposed
0xd0b6  brfalse.s loc_D0BA
0xd0b8  ldc.i4.0
0xd0b9  ret
0xd0ba  ldarg.0
0xd0bb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob> Microsoft.Crm.Asynchronous.Rollups.JobSelector::_enumerator
0xd0c0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd0c5  stloc.0
0xd0c6  ldloc.0
0xd0c7  brtrue.s loc_D0F8
0xd0c9  ldarg.0
0xd0ca  ldfld    bool Microsoft.Crm.Asynchronous.Rollups.JobSelector::_ignoreSettingsAndForceYield
0xd0cf  brtrue.s loc_D0F8
0xd0d1  call     valuetype Microsoft.Crm.Asynchronous.Rollups.PostponePolicy Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_IncrementalRollupSelfPostponePolicy()
0xd0d6  ldc.i4.1
0xd0d7  beq.s    loc_D0E6
0xd0d9  ldarg.0
0xd0da  call     instance int32 Microsoft.Crm.Asynchronous.Rollups.JobSelector::get_NumberOfJobsProcessed()
0xd0df  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_IncrementalRollupMaxRecordsToProcess()
0xd0e4  bge.s    loc_D0F8
0xd0e6  ldarg.0
0xd0e7  call     instance void Microsoft.Crm.Asynchronous.Rollups.JobSelector::SelectJobs()
0xd0ec  ldarg.0
0xd0ed  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob> Microsoft.Crm.Asynchronous.Rollups.JobSelector::_enumerator
0xd0f2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd0f7  stloc.0
0xd0f8  ldloc.0
0xd0f9  brfalse.s loc_D10D
0xd0fb  ldarg.0
0xd0fc  call     instance int32 Microsoft.Crm.Asynchronous.Rollups.JobSelector::get_NumberOfJobsProcessed()
0xd101  stloc.1
0xd102  ldarg.0
0xd103  ldloc.1
0xd104  ldc.i4.1
0xd105  add
0xd106  call     instance void Microsoft.Crm.Asynchronous.Rollups.JobSelector::set_NumberOfJobsProcessed(int32 value)
0xd10b  ldc.i4.1
0xd10c  ret
0xd10d  ldc.i4.0
0xd10e  ret
```
