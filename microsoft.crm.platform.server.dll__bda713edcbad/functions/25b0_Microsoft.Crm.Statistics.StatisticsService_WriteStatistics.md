# Microsoft.Crm.Statistics.StatisticsService::WriteStatistics

- ea: `0x25b0`
- end: `0x27b1`
- name: `Microsoft.Crm.Statistics.StatisticsService::WriteStatistics`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x25b0`

## callees

- `0x1c50`
- `0x1d30`
- `0x1e50`
- `0x1f30`
- `0x2310`
- `0x25b0`
- `0x27c0`
- `0x2ae0`

## string_xrefs

- `0x26de`: `StatisticsServiceWaitTimeMillis`
- `0x27a4`: `WriteStatistics Stopped.`

## pseudocode

```c

```

## disassembly

```asm
0x25b0  ldc.i4.0
0x25b1  stloc.0
0x25b2  ldc.i4.0
0x25b3  stloc.1
0x25b4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x25b9  stloc.2
0x25ba  ldarg.0
0x25bb  volatile.
0x25bd  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.Crm.Statistics.StatisticsService::_running
0x25c2  brfalse  loc_26CA
0x25c7  ldarg.0
0x25c8  volatile.
0x25ca  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.Crm.Statistics.StatisticsService::_disabled
0x25cf  brtrue   loc_26CA
0x25d4  call     class Microsoft.Crm.Statistics.StatisticsCollector Microsoft.Crm.Statistics.StatisticsCollector::get_Instance()
0x25d9  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Statistics.StatisticsCollector::RetrieveOrganizations()
0x25de  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x25e3  stloc.s  4
0x25e5  br       loc_26B0
0x25ea  ldloc.s  4
0x25ec  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x25f1  stloc.s  5
0x25f3  call     class Microsoft.Crm.Statistics.StatisticsCollector Microsoft.Crm.Statistics.StatisticsCollector::get_Instance()
0x25f8  ldloc.s  5
0x25fa  callvirt instance bool Microsoft.Crm.Statistics.StatisticsCollector::IsStatisticsCollectionEnabled(valuetype [mscorlib]System.Guid organizationId)
0x25ff  brfalse  loc_26B0
0x2604  ldc.i4.0
0x2605  stloc.0
0x2606  ldc.i4.0
0x2607  stloc.1
0x2608  ldloc.s  5
0x260a  stloc.2
0x260b  call     class Microsoft.Crm.Statistics.StatisticsCollector Microsoft.Crm.Statistics.StatisticsCollector::get_Instance()
0x2610  ldloc.s  5
0x2612  callvirt instance class Microsoft.Crm.Statistics.StatisticsArrayCollection Microsoft.Crm.Statistics.StatisticsCollector::RetrieveStatistics(valuetype [mscorlib]System.Guid organizationId)
0x2617  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x261c  stloc.s  6
0x261e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2623  stloc.s  8
0x2625  ldloca.s 8
0x2627  ldc.r8   -1.0
0x2630  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x2635  stloc.s  7
0x2637  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Statistics.StatisticsArray>::GetEnumerator()
0x263c  stloc.s  9
0x263e  br.s     loc_268B
0x2640  ldloc.s  9
0x2642  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Statistics.StatisticsArray>::get_Current()
0x2647  stloc.s  0xA
0x2649  ldloc.s  0xA
0x264b  ldloca.s 6
0x264d  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x2652  callvirt instance int32 Microsoft.Crm.Statistics.StatisticsArray::get_Item(int32 index)
0x2657  brfalse.s loc_266A
0x2659  ldarg.0
0x265a  ldloca.s 6
0x265c  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x2661  ldloc.s  0xA
0x2663  ldloc.s  5
0x2665  call     instance void Microsoft.Crm.Statistics.StatisticsService::SaveStatistic(int32 hour, class Microsoft.Crm.Statistics.StatisticsArray array, valuetype [mscorlib]System.Guid orgId)
0x266a  ldloc.s  0xA
0x266c  ldloca.s 7
0x266e  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x2673  callvirt instance int32 Microsoft.Crm.Statistics.StatisticsArray::get_Item(int32 index)
0x2678  brfalse.s loc_268B
0x267a  ldarg.0
0x267b  ldloca.s 7
0x267d  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x2682  ldloc.s  0xA
0x2684  ldloc.s  5
0x2686  call     instance void Microsoft.Crm.Statistics.StatisticsService::SaveStatistic(int32 hour, class Microsoft.Crm.Statistics.StatisticsArray array, valuetype [mscorlib]System.Guid orgId)
0x268b  ldloc.s  9
0x268d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2692  brtrue.s loc_2640
0x2694  leave.s  loc_26A2
0x2696  ldloc.s  9
0x2698  brfalse.s loc_26A1
0x269a  ldloc.s  9
0x269c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26a1  endfinally
0x26a2  ldc.i4.1
0x26a3  stloc.0
0x26a4  ldarg.0
0x26a5  ldloc.s  6
0x26a7  ldloc.s  5
0x26a9  call     instance void Microsoft.Crm.Statistics.StatisticsService::ClearStatistics(valuetype [mscorlib]System.DateTime time, valuetype [mscorlib]System.Guid orgId)
0x26ae  ldc.i4.1
0x26af  stloc.1
0x26b0  ldloc.s  4
0x26b2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26b7  brtrue   loc_25EA
0x26bc  leave.s  loc_26D9
0x26be  ldloc.s  4
0x26c0  brfalse.s loc_26C9
0x26c2  ldloc.s  4
0x26c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26c9  endfinally
0x26ca  ldarg.0
0x26cb  volatile.
0x26cd  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.Crm.Statistics.StatisticsService::_disabled
0x26d2  brfalse.s loc_26D9
0x26d4  leave    loc_27B0
0x26d9  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x26de  ldstr    aStatisticsserv// "StatisticsServiceWaitTimeMillis"
0x26e3  ldc.i4.0
0x26e4  callvirt T0x2B000002
0x26e9  stloc.3
0x26ea  ldloca.s 3
0x26ec  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x26f1  brfalse.s loc_270F
0x26f3  ldloca.s 3
0x26f5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x26fa  ldsfld   int32 Microsoft.Crm.Statistics.StatisticsService::TwoHoursMillis
0x26ff  bge.s    loc_270F
0x2701  ldloca.s 3
0x2703  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x2708  ldsfld   int32 Microsoft.Crm.Statistics.StatisticsService::FiveSecondsMillis
0x270d  bge.s    loc_271B
0x270f  ldsfld   int32 Microsoft.Crm.Statistics.StatisticsService::FiveMinutesMillis
0x2714  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x2719  br.s     loc_2727
0x271b  ldloca.s 3
0x271d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x2722  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x2727  leave    Microsoft.Crm.Statistics.StatisticsService__WriteStatistics
0x272c  pop
0x272d  rethrow
0x272f  stloc.s  0xB
0x2731  ldloc.0
0x2732  brtrue.s loc_273D
0x2734  ldstr    aExceptionSavin// "Exception saving statistics: {0}"
0x2739  stloc.s  0xC
0x273b  br.s     loc_2750
0x273d  ldloc.1
0x273e  brtrue.s loc_2749
0x2740  ldstr    aExceptionClear// "Exception clearing statistics: {0}"
0x2745  stloc.s  0xC
0x2747  br.s     loc_2750
0x2749  ldstr    aExceptionProce// "Exception processing statistics: {0}"
0x274e  stloc.s  0xC
0x2750  ldloc.0
0x2751  brfalse.s loc_2756
0x2753  ldloc.1
0x2754  brtrue.s loc_276F
0x2756  ldloc.s  0xB
0x2758  ldloc.2
0x2759  ldc.i4.s 0x14
0x275b  ldloc.s  0xC
0x275d  ldc.i4.1
0x275e  newarr   [mscorlib]System.Object
0x2763  dup
0x2764  ldc.i4.0
0x2765  ldloc.s  0xB
0x2767  stelem.ref
0x2768  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x276d  br.s     loc_278A
0x276f  ldloc.s  0xB
0x2771  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2776  ldc.i4.s 0x14
0x2778  ldloc.s  0xC
0x277a  ldc.i4.1
0x277b  newarr   [mscorlib]System.Object
0x2780  dup
0x2781  ldc.i4.0
0x2782  ldloc.s  0xB
0x2784  stelem.ref
0x2785  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x278a  leave    Microsoft.Crm.Statistics.StatisticsService__WriteStatistics
0x278f  ldnull
0x2790  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2795  ldc.i4.s 0x14
0x2797  ldstr    a0// "{0}"
0x279c  ldc.i4.1
0x279d  newarr   [mscorlib]System.Object
0x27a2  dup
0x27a3  ldc.i4.0
0x27a4  ldstr    aWritestatistic// "WriteStatistics Stopped."
0x27a9  stelem.ref
0x27aa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x27af  endfinally
0x27b0  ret
```
