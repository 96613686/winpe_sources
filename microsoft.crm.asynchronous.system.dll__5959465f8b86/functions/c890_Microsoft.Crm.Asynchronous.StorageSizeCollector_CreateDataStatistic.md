# Microsoft.Crm.Asynchronous.StorageSizeCollector::CreateDataStatistic

- ea: `0xc890`
- end: `0xc8ec`
- name: `Microsoft.Crm.Asynchronous.StorageSizeCollector::CreateDataStatistic`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xc850`

## callees

- `0xc090`
- `0xc3e0`
- `0xc690`
- `0xc890`

## pseudocode

```c

```

## disassembly

```asm
0xc890  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsDatabaseService::.ctor()
0xc895  stloc.0
0xc896  ldarg.0
0xc897  ldarg.2
0xc898  call     instance int32 Microsoft.Crm.Asynchronous.SizeCollectorBase::RetrieveOrganizationDetail(string columnName)
0xc89d  stloc.1
0xc89e  ldarg.0
0xc89f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::get_OrganizationId()
0xc8a4  ldc.i4.s 0x15
0xc8a6  ldstr    aCustomquerySta// "CustomQuery Statistic({0}) and org({1})"...
0xc8ab  ldc.i4.3
0xc8ac  newarr   [mscorlib]System.Object
0xc8b1  dup
0xc8b2  ldc.i4.0
0xc8b3  ldarg.1
0xc8b4  box      [mscorlib]System.Int32
0xc8b9  stelem.ref
0xc8ba  dup
0xc8bb  ldc.i4.1
0xc8bc  ldarg.0
0xc8bd  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::get_OrganizationId()
0xc8c2  box      [mscorlib]System.Guid
0xc8c7  stelem.ref
0xc8c8  dup
0xc8c9  ldc.i4.2
0xc8ca  ldloc.1
0xc8cb  box      [mscorlib]System.Int32
0xc8d0  stelem.ref
0xc8d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc8d6  ldarg.0
0xc8d7  ldloc.0
0xc8d8  ldarg.1
0xc8d9  ldloc.1
0xc8da  call     instance void Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::CreateScalarStatisticRow(class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService service, int32 statisticType, int32 value)
0xc8df  leave.s  loc_C8EB
0xc8e1  ldloc.0
0xc8e2  brfalse.s loc_C8EA
0xc8e4  ldloc.0
0xc8e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc8ea  endfinally
0xc8eb  ret
```
