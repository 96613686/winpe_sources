# Microsoft.Crm.Asynchronous.QueueStatisticsHelper::WriteToEventViewer

- ea: `0x12560`
- end: `0x1277c`
- name: `Microsoft.Crm.Asynchronous.QueueStatisticsHelper::WriteToEventViewer`
- size: `540`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x23f0`
- `0x57d0`
- `0x7bc0`

## callees

- `0xfdf0`
- `0xff30`
- `0x10170`
- `0x12560`
- `0x12830`
- `0x128a0`
- `0x17e90`

## string_xrefs

- `0x125e8`: `MSCRMAsyncService`
- `0x12663`: `MSCRMAsyncService`

## pseudocode

```c

```

## disassembly

```asm
0x12560  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x12565  stloc.0
0x12566  ldc.i4.0
0x12567  stloc.1
0x12568  ldarg.1
0x12569  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::get_Keys()
0x1256e  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::GetEnumerator()
0x12573  stloc.2
0x12574  br.s     loc_12598
0x12576  ldloca.s 2
0x12578  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::get_Current()
0x1257d  stloc.3
0x1257e  ldarg.1
0x1257f  ldloc.3
0x12580  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::get_Item(void)
0x12585  ldarg.2
0x12586  callvirt instance bool Microsoft.Crm.Asynchronous.OrgStatistics::IsQueueBackloggedForExtendedPeriod(valuetype Microsoft.Crm.Asynchronous.QueueType queueType)
0x1258b  brfalse.s loc_12598
0x1258d  ldloc.1
0x1258e  ldc.i4.1
0x1258f  add
0x12590  stloc.1
0x12591  ldloc.0
0x12592  ldloc.3
0x12593  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x12598  ldloca.s 2
0x1259a  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::MoveNext()
0x1259f  brtrue.s loc_12576
0x125a1  leave.s  loc_125B1
0x125a3  ldloca.s 2
0x125a5  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>
0x125ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x125b0  endfinally
0x125b1  ldloc.1
0x125b2  call     int32 Microsoft.Crm.Asynchronous.Settings::get_MaxNoOfAllowedBacklogOrganizations()
0x125b7  ble.s    loc_12634
0x125b9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x125be  stloc.s  4
0x125c0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x125c5  stloc.s  5
0x125c7  ldloc.s  5
0x125c9  ldsfld   string [mscorlib]System.String::Empty
0x125ce  stfld    string <>c__DisplayClass4_0::organizationList
0x125d3  ldloc.0
0x125d4  ldloc.s  5
0x125d6  ldftn    instance void <>c__DisplayClass4_0::<WriteToEventViewer>b__0(valuetype [mscorlib]System.Guid organizationGuid)
0x125dc  newobj   instance void class [mscorlib]System.Action`1<valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x125e1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ForEach(class [mscorlib]System.Action`1<var<u1>>)
0x125e6  ldloc.s  4
0x125e8  ldstr    aMscrmasyncserv_0// "MSCRMAsyncService"
0x125ed  ldc.i4.1
0x125ee  ldc.i4   0xC0006306
0x125f3  conv.u8
0x125f4  ldc.i4.2
0x125f5  newarr   [mscorlib]System.Object
0x125fa  dup
0x125fb  ldc.i4.0
0x125fc  ldarga.s 2
0x125fe  constrained. Microsoft.Crm.Asynchronous.QueueType
0x12604  callvirt instance string [mscorlib]System.Object::ToString()
0x12609  stelem.ref
0x1260a  dup
0x1260b  ldc.i4.1
0x1260c  ldloc.s  5
0x1260e  ldfld    string <>c__DisplayClass4_0::organizationList
0x12613  stelem.ref
0x12614  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x12619  ldarg.0
0x1261a  ldloc.1
0x1261b  call     instance void Microsoft.Crm.Asynchronous.QueueStatisticsHelper::SampleScaleGroupBackloggedOrgsCount(int32 count)
0x12620  ldloc.0
0x12621  stloc.s  6
0x12623  leave    loc_12779
0x12628  ldloc.s  4
0x1262a  brfalse.s loc_12633
0x1262c  ldloc.s  4
0x1262e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12633  endfinally
0x12634  ldloc.0
0x12635  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x1263a  stloc.s  7
0x1263c  br       loc_12754
0x12641  ldloca.s 7
0x12643  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x12648  stloc.s  8
0x1264a  ldarg.1
0x1264b  ldloc.s  8
0x1264d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.OrgStatistics>::get_Item(void)
0x12652  ldarg.2
0x12653  callvirt instance class Microsoft.Crm.Asynchronous.QueueStatistics[] Microsoft.Crm.Asynchronous.OrgStatistics::GetQueueSamplesInReverse(valuetype Microsoft.Crm.Asynchronous.QueueType queueType)
0x12658  stloc.s  9
0x1265a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x1265f  stloc.s  0xA
0x12661  ldloc.s  0xA
0x12663  ldstr    aMscrmasyncserv_0// "MSCRMAsyncService"
0x12668  ldc.i4.1
0x12669  ldc.i4   0xC0006305
0x1266e  conv.u8
0x1266f  ldc.i4.s 0xA
0x12671  newarr   [mscorlib]System.Object
0x12676  dup
0x12677  ldc.i4.0
0x12678  ldarga.s 2
0x1267a  constrained. Microsoft.Crm.Asynchronous.QueueType
0x12680  callvirt instance string [mscorlib]System.Object::ToString()
0x12685  stelem.ref
0x12686  dup
0x12687  ldc.i4.1
0x12688  ldloc.s  8
0x1268a  box      [mscorlib]System.Guid
0x1268f  stelem.ref
0x12690  dup
0x12691  ldc.i4.2
0x12692  ldarg.0
0x12693  ldloc.s  9
0x12695  ldstr    aBacklogvolume// "BacklogVolume"
0x1269a  ldc.i4.3
0x1269b  call     instance int32 Microsoft.Crm.Asynchronous.QueueStatisticsHelper::GetSampleValue(class Microsoft.Crm.Asynchronous.QueueStatistics[] backlogStats, string statName, int32 index)
0x126a0  box      [mscorlib]System.Int32
0x126a5  stelem.ref
0x126a6  dup
0x126a7  ldc.i4.3
0x126a8  ldarg.0
0x126a9  ldloc.s  9
0x126ab  ldstr    aMaxlatency// "MaxLatency"
0x126b0  ldc.i4.3
0x126b1  call     instance int32 Microsoft.Crm.Asynchronous.QueueStatisticsHelper::GetSampleValue(class Microsoft.Crm.Asynchronous.QueueStatistics[] backlogStats, string statName, int32 index)
0x126b6  box      [mscorlib]System.Int32
0x126bb  stelem.ref
0x126bc  dup
0x126bd  ldc.i4.4
0x126be  ldarg.0
0x126bf  ldloc.s  9
0x126c1  ldstr    aBacklogvolume// "BacklogVolume"
0x126c6  ldc.i4.2
0x126c7  call     instance int32 Microsoft.Crm.Asynchronous.QueueStatisticsHelper::GetSampleValue(class Microsoft.Crm.Asynchronous.QueueStatistics[] backlogStats, string statName, int32 index)
0x126cc  box      [mscorlib]System.Int32
0x126d1  stelem.ref
0x126d2  dup
0x126d3  ldc.i4.5
0x126d4  ldarg.0
0x126d5  ldloc.s  9
0x126d7  ldstr    aMaxlatency// "MaxLatency"
0x126dc  ldc.i4.2
0x126dd  call     instance int32 Microsoft.Crm.Asynchronous.QueueStatisticsHelper::GetSampleValue(class Microsoft.Crm.Asynchronous.QueueStatistics[] backlogStats, string statName, int32 index)
0x126e2  box      [mscorlib]System.Int32
0x126e7  stelem.ref
0x126e8  dup
0x126e9  ldc.i4.6
0x126ea  ldarg.0
0x126eb  ldloc.s  9
0x126ed  ldstr    aBacklogvolume// "BacklogVolume"
0x126f2  ldc.i4.1
0x126f3  call     instance int32 Microsoft.Crm.Asynchronous.QueueStatisticsHelper::GetSampleValue(class Microsoft.Crm.Asynchronous.QueueStatistics[] backlogStats, string statName, int32 index)
0x126f8  box      [mscorlib]System.Int32
0x126fd  stelem.ref
0x126fe  dup
0x126ff  ldc.i4.7
0x12700  ldarg.0
0x12701  ldloc.s  9
0x12703  ldstr    aMaxlatency// "MaxLatency"
0x12708  ldc.i4.1
0x12709  call     instance int32 Microsoft.Crm.Asynchronous.QueueStatisticsHelper::GetSampleValue(class Microsoft.Crm.Asynchronous.QueueStatistics[] backlogStats, string statName, int32 index)
0x1270e  box      [mscorlib]System.Int32
0x12713  stelem.ref
0x12714  dup
0x12715  ldc.i4.8
0x12716  ldarg.0
0x12717  ldloc.s  9
0x12719  ldstr    aBacklogvolume// "BacklogVolume"
0x1271e  ldc.i4.0
0x1271f  call     instance int32 Microsoft.Crm.Asynchronous.QueueStatisticsHelper::GetSampleValue(class Microsoft.Crm.Asynchronous.QueueStatistics[] backlogStats, string statName, int32 index)
0x12724  box      [mscorlib]System.Int32
0x12729  stelem.ref
0x1272a  dup
0x1272b  ldc.i4.s 9
0x1272d  ldarg.0
0x1272e  ldloc.s  9
0x12730  ldstr    aMaxlatency// "MaxLatency"
0x12735  ldc.i4.0
0x12736  call     instance int32 Microsoft.Crm.Asynchronous.QueueStatisticsHelper::GetSampleValue(class Microsoft.Crm.Asynchronous.QueueStatistics[] backlogStats, string statName, int32 index)
0x1273b  box      [mscorlib]System.Int32
0x12740  stelem.ref
0x12741  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x12746  leave.s  loc_12754
0x12748  ldloc.s  0xA
0x1274a  brfalse.s loc_12753
0x1274c  ldloc.s  0xA
0x1274e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12753  endfinally
0x12754  ldloca.s 7
0x12756  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x1275b  brtrue   loc_12641
0x12760  leave.s  loc_12770
0x12762  ldloca.s 7
0x12764  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x1276a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1276f  endfinally
0x12770  ldarg.0
0x12771  ldloc.1
0x12772  call     instance void Microsoft.Crm.Asynchronous.QueueStatisticsHelper::SampleScaleGroupBackloggedOrgsCount(int32 count)
0x12777  ldloc.0
0x12778  ret
0x12779  ldloc.s  6
0x1277b  ret
```
