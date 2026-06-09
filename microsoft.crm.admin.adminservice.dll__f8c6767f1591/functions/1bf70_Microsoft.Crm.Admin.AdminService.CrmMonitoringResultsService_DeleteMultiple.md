# Microsoft.Crm.Admin.AdminService.CrmMonitoringResultsService::DeleteMultiple

- ea: `0x1bf70`
- end: `0x1c082`
- name: `Microsoft.Crm.Admin.AdminService.CrmMonitoringResultsService::DeleteMultiple`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c420`

## callees

- `0x1bf10`
- `0x1bf70`

## string_xrefs

- `0x1c045`: `D:\a\1\s\src\CrmLive\Admin\MonitoringResults\CrmMonitoringResultsService.cs`
- `0x1bf71`: `Monitoring Result Ids to be deleted are NULL`
- `0x1c040`: `DeleteMultiple`
- `0x1c057`: `Deleted MonitoringResults, Ids=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x1bf70  ldarg.1
0x1bf71  ldstr    aMonitoringResu// "Monitoring Result Ids to be deleted are"...
0x1bf76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1bf7b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1bf80  stloc.0
0x1bf81  ldarg.1
0x1bf82  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x1bf87  brtrue.s loc_1BF8E
0x1bf89  leave    loc_1C081
0x1bf8e  ldarg.1
0x1bf8f  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x1bf94  ldc.i4.1
0x1bf95  bne.un.s loc_1BFA9
0x1bf97  ldarg.0
0x1bf98  ldarg.1
0x1bf99  ldc.i4.0
0x1bf9a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x1bf9f  call     instance void Microsoft.Crm.Admin.AdminService.CrmMonitoringResultsService::Delete(valuetype [mscorlib]System.Guid monitoringResultId)
0x1bfa4  br       loc_1C050
0x1bfa9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1bfae  stloc.1
0x1bfaf  ldc.i4.1
0x1bfb0  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x1bfb5  stloc.2
0x1bfb6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection>::.ctor()
0x1bfbb  stloc.3
0x1bfbc  ldarg.1
0x1bfbd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x1bfc2  stloc.s  4
0x1bfc4  br.s     loc_1C010
0x1bfc6  ldloc.s  4
0x1bfc8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x1bfcd  stloc.s  5
0x1bfcf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::.ctor()
0x1bfd4  stloc.s  6
0x1bfd6  ldloc.s  6
0x1bfd8  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison> [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::get_PropertyComparisonList()
0x1bfdd  ldc.i4.0
0x1bfde  ldloc.s  5
0x1bfe0  box      [mscorlib]System.Guid
0x1bfe5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x1bfea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison>::Add(var<u1>)
0x1bfef  ldloc.s  6
0x1bff1  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison> [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::get_PropertyComparisonList()
0x1bff6  ldc.i4.0
0x1bff7  ldloc.s  5
0x1bff9  box      [mscorlib]System.Guid
0x1bffe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x1c003  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison>::Add(var<u1>)
0x1c008  ldloc.3
0x1c009  ldloc.s  6
0x1c00b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection>::Add(var<u1>)
0x1c010  ldloc.s  4
0x1c012  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1c017  brtrue.s loc_1BFC6
0x1c019  leave.s  loc_1C027
0x1c01b  ldloc.s  4
0x1c01d  brfalse.s loc_1C026
0x1c01f  ldloc.s  4
0x1c021  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c026  endfinally
0x1c027  ldloc.1
0x1c028  ldstr    aId// "Id"
0x1c02d  ldloc.3
0x1c02e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c033  ldloc.2
0x1c034  ldc.i4.0
0x1c035  ldloc.1
0x1c036  stelem.ref
0x1c037  ldloc.0
0x1c038  ldstr    aMonitoringresu// "MonitoringResults"
0x1c03d  ldloc.2
0x1c03e  ldc.i4.s 0x71
0x1c040  ldstr    aDeletemultiple// "DeleteMultiple"
0x1c045  ldstr    aDA1SSrcCrmlive_38// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Monit"...
0x1c04a  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1c04f  pop
0x1c050  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1c055  ldc.i4.s 9
0x1c057  ldstr    aDeletedMonitor_0// "Deleted MonitoringResults, Ids=({0})"
0x1c05c  ldc.i4.1
0x1c05d  newarr   [mscorlib]System.Object
0x1c062  dup
0x1c063  ldc.i4.0
0x1c064  ldstr    asc_533CA// ","
0x1c069  ldarg.1
0x1c06a  call     T0x2B000072
0x1c06f  stelem.ref
0x1c070  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c075  leave.s  loc_1C081
0x1c077  ldloc.0
0x1c078  brfalse.s loc_1C080
0x1c07a  ldloc.0
0x1c07b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c080  endfinally
0x1c081  ret
```
