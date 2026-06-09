# Microsoft.Crm.Caching.SimilarityRuleWebServiceCacheLoader::LoadCacheData_0

- ea: `0x14780`
- end: `0x1488e`
- name: `Microsoft.Crm.Caching.SimilarityRuleWebServiceCacheLoader::LoadCacheData_0`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14770`

## callees

- `0x127e0`
- `0x14780`
- `0x59800`

## string_xrefs

- `0x14794`: `Similarity Rule Web Service Cache Loader started loading cache at: {0}`
- `0x14862`: `Similarity Rule Web Service Cache Loader finished loading cache at: {0}\nTotal time taken; {1}`

## pseudocode

```c

```

## disassembly

```asm
0x14780  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SimilarityRulesData::.ctor()
0x14785  stloc.0
0x14786  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1478b  stloc.1
0x1478c  ldarg.2
0x1478d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x14792  ldc.i4.s 0x1A
0x14794  ldstr    aSimilarityRule// "Similarity Rule Web Service Cache Loade"...
0x14799  ldc.i4.1
0x1479a  newarr   [mscorlib]System.Object
0x1479f  dup
0x147a0  ldc.i4.0
0x147a1  ldloca.s 1
0x147a3  call     instance string [mscorlib]System.DateTime::ToString()
0x147a8  stelem.ref
0x147a9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x147ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x147b3  stloc.s  4
0x147b5  ldstr    aSimilarityrule// "similarityrule"
0x147ba  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x147bf  dup
0x147c0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.AllColumns::.ctor()
0x147c5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x147ca  ldarg.2
0x147cb  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x147d0  stloc.s  5
0x147d2  ldloc.s  5
0x147d4  ldstr    aSimilarityRule_0// "Similarity Rules"
0x147d9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x147de  ldloc.s  5
0x147e0  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x147e5  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SimilarityRuleSet
0x147ea  stloc.s  6
0x147ec  ldc.i4.0
0x147ed  stloc.s  7
0x147ef  ldc.i4.0
0x147f0  stloc.s  8
0x147f2  br.s     loc_14824
0x147f4  ldloc.s  5
0x147f6  ldloc.s  8
0x147f8  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x147fd  newobj   instance void Microsoft.Crm.Caching.CacheApplicationEntityWrapper::.ctor(class Microsoft.Crm.Application.Platform.Entity entity)
0x14802  stloc.s  9
0x14804  ldloc.s  9
0x14806  brfalse.s loc_1481E
0x14808  ldloc.s  6
0x1480a  ldloc.s  7
0x1480c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SimilarityRuleSet::.ctor()
0x14811  stelem.ref
0x14812  ldloc.s  6
0x14814  ldloc.s  7
0x14816  ldelem.ref
0x14817  ldloc.s  9
0x14819  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SimilarityRuleSet::set_SimilarityRule(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheEntityWrapper)
0x1481e  ldloc.s  8
0x14820  ldc.i4.1
0x14821  add
0x14822  stloc.s  8
0x14824  ldloc.s  8
0x14826  ldloc.s  5
0x14828  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x1482d  blt.s    loc_147F4
0x1482f  ldloc.0
0x14830  ldloc.s  6
0x14832  ldarg.2
0x14833  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x14838  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SimilarityRulesData::Initialize(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SimilarityRuleSet[], valuetype [mscorlib]System.Guid)
0x1483d  leave.s  loc_1484B
0x1483f  ldloc.s  4
0x14841  brfalse.s loc_1484A
0x14843  ldloc.s  4
0x14845  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1484a  endfinally
0x1484b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x14850  stloc.2
0x14851  ldloca.s 2
0x14853  ldloc.1
0x14854  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x14859  stloc.3
0x1485a  ldarg.2
0x1485b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x14860  ldc.i4.s 0x1A
0x14862  ldstr    aSimilarityRule_1// "Similarity Rule Web Service Cache Loade"...
0x14867  ldc.i4.2
0x14868  newarr   [mscorlib]System.Object
0x1486d  dup
0x1486e  ldc.i4.0
0x1486f  ldloca.s 2
0x14871  call     instance string [mscorlib]System.DateTime::ToString()
0x14876  stelem.ref
0x14877  dup
0x14878  ldc.i4.1
0x14879  ldloca.s 3
0x1487b  constrained. [mscorlib]System.TimeSpan
0x14881  callvirt instance string [mscorlib]System.Object::ToString()
0x14886  stelem.ref
0x14887  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1488c  ldloc.0
0x1488d  ret
```
