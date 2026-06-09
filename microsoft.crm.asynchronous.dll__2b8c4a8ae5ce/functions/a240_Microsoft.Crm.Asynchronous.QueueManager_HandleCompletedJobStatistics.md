# Microsoft.Crm.Asynchronous.QueueManager::HandleCompletedJobStatistics

- ea: `0xa240`
- end: `0xa311`
- name: `Microsoft.Crm.Asynchronous.QueueManager::HandleCompletedJobStatistics`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xa3d0`

## callees

- `0xa240`
- `0xa320`
- `0xfcf0`
- `0xff50`
- `0xffd0`
- `0x100c0`

## pseudocode

```c

```

## disassembly

```asm
0xa240  ldc.i4.0
0xa241  stloc.0
0xa242  ldarg.0
0xa243  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics> Microsoft.Crm.Asynchronous.QueueManager::executionTimes
0xa248  stloc.1
0xa249  ldc.i4.0
0xa24a  stloc.2
0xa24b  ldloc.1
0xa24c  ldloca.s 2
0xa24e  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa253  ldarg.0
0xa254  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics> Microsoft.Crm.Asynchronous.QueueManager::executionTimes
0xa259  ldarg.2
0xa25a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::ContainsKey(var<u1>)
0xa25f  brtrue.s loc_A272
0xa261  ldarg.0
0xa262  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics> Microsoft.Crm.Asynchronous.QueueManager::executionTimes
0xa267  ldarg.2
0xa268  newobj   instance void Microsoft.Crm.Asynchronous.OrgStatistics::.ctor()
0xa26d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::set_Item(var<u1>, !!T0)
0xa272  ldarg.0
0xa273  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics> Microsoft.Crm.Asynchronous.QueueManager::executionTimes
0xa278  ldarg.2
0xa279  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::get_Item(void)
0xa27e  ldarg.1
0xa27f  callvirt instance void Microsoft.Crm.Asynchronous.OrgStatistics::RecordExecutionTime(int32 timeInMilliseconds)
0xa284  ldarg.0
0xa285  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics> Microsoft.Crm.Asynchronous.QueueManager::executionTimes
0xa28a  ldarg.2
0xa28b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::get_Item(void)
0xa290  callvirt instance int32 Microsoft.Crm.Asynchronous.OrgStatistics::get_AverageRecentExecutionTimeInMilliseconds()
0xa295  stloc.0
0xa296  leave.s  loc_A2A2
0xa298  ldloc.2
0xa299  brfalse.s loc_A2A1
0xa29b  ldloc.1
0xa29c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa2a1  endfinally
0xa2a2  ldloc.0
0xa2a3  call     int32 Microsoft.Crm.Asynchronous.Settings::get_LongJobThresholdInMilliseconds()
0xa2a8  ble.s    loc_A2DD
0xa2aa  ldarg.0
0xa2ab  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.QueueManager::orgsWithLongRunningJobsInRecentPast
0xa2b0  stloc.3
0xa2b1  ldc.i4.0
0xa2b2  stloc.2
0xa2b3  ldloc.3
0xa2b4  ldloca.s 2
0xa2b6  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa2bb  ldarg.0
0xa2bc  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.QueueManager::orgsWithLongRunningJobsInRecentPast
0xa2c1  ldarg.2
0xa2c2  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0xa2c7  brtrue.s loc_A2D1
0xa2c9  ldarg.0
0xa2ca  ldarg.2
0xa2cb  ldc.i4.1
0xa2cc  call     instance void Microsoft.Crm.Asynchronous.QueueManager::UpdateLongRunningJobs(valuetype [mscorlib]System.Guid organizationId, valuetype Microsoft.Crm.Asynchronous.JobLengthRange jobLengthRange)
0xa2d1  leave.s  loc_A310
0xa2d3  ldloc.2
0xa2d4  brfalse.s loc_A2DC
0xa2d6  ldloc.3
0xa2d7  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa2dc  endfinally
0xa2dd  ldarg.0
0xa2de  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.QueueManager::orgsWithLongRunningJobsInRecentPast
0xa2e3  stloc.3
0xa2e4  ldc.i4.0
0xa2e5  stloc.2
0xa2e6  ldloc.3
0xa2e7  ldloca.s 2
0xa2e9  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa2ee  ldarg.0
0xa2ef  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.QueueManager::orgsWithLongRunningJobsInRecentPast
0xa2f4  ldarg.2
0xa2f5  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0xa2fa  brfalse.s loc_A304
0xa2fc  ldarg.0
0xa2fd  ldarg.2
0xa2fe  ldc.i4.0
0xa2ff  call     instance void Microsoft.Crm.Asynchronous.QueueManager::UpdateLongRunningJobs(valuetype [mscorlib]System.Guid organizationId, valuetype Microsoft.Crm.Asynchronous.JobLengthRange jobLengthRange)
0xa304  leave.s  loc_A310
0xa306  ldloc.2
0xa307  brfalse.s loc_A30F
0xa309  ldloc.3
0xa30a  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa30f  endfinally
0xa310  ret
```
