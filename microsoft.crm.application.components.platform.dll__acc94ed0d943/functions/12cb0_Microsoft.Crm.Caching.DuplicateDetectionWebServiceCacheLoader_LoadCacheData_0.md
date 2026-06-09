# Microsoft.Crm.Caching.DuplicateDetectionWebServiceCacheLoader::LoadCacheData_0

- ea: `0x12cb0`
- end: `0x12dfc`
- name: `Microsoft.Crm.Caching.DuplicateDetectionWebServiceCacheLoader::LoadCacheData_0`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x12ca0`

## callees

- `0x127e0`
- `0x127f0`
- `0x12cb0`
- `0x12e00`
- `0x12e60`
- `0x59800`

## string_xrefs

- `0x12cc4`: `Duplicate Detection Web Service Cache Loader started loading cache at: {0}`
- `0x12dd0`: `Duplicate Detection Web Service Cache Loader finished loading cache at: {0}\nTotal time taken; {1}`

## pseudocode

```c

```

## disassembly

```asm
0x12cb0  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DuplicateRulesData::.ctor()
0x12cb5  stloc.0
0x12cb6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x12cbb  stloc.1
0x12cbc  ldarg.2
0x12cbd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x12cc2  ldc.i4.s 0x1A
0x12cc4  ldstr    aDuplicateDetec// "Duplicate Detection Web Service Cache L"...
0x12cc9  ldc.i4.1
0x12cca  newarr   [mscorlib]System.Object
0x12ccf  dup
0x12cd0  ldc.i4.0
0x12cd1  ldloca.s 1
0x12cd3  call     instance string [mscorlib]System.DateTime::ToString()
0x12cd8  stelem.ref
0x12cd9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12cde  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x12ce3  stloc.s  4
0x12ce5  ldstr    aDuplicaterule// "duplicaterule"
0x12cea  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x12cef  dup
0x12cf0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.AllColumns::.ctor()
0x12cf5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x12cfa  ldarg.2
0x12cfb  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x12d00  stloc.s  5
0x12d02  ldloc.s  5
0x12d04  ldstr    aDuplicateDetec_0// "Duplicate Detection Rules"
0x12d09  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12d0e  ldloc.s  5
0x12d10  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x12d15  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DuplicateRuleSet
0x12d1a  stloc.s  6
0x12d1c  ldnull
0x12d1d  stloc.s  7
0x12d1f  ldnull
0x12d20  stloc.s  8
0x12d22  ldnull
0x12d23  stloc.s  9
0x12d25  ldc.i4.0
0x12d26  stloc.s  0xA
0x12d28  ldc.i4.0
0x12d29  stloc.s  0xB
0x12d2b  br.s     loc_12D92
0x12d2d  ldloc.s  5
0x12d2f  ldloc.s  0xB
0x12d31  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x12d36  newobj   instance void Microsoft.Crm.Caching.CacheApplicationEntityWrapper::.ctor(class Microsoft.Crm.Application.Platform.Entity entity)
0x12d3b  stloc.s  7
0x12d3d  ldloc.s  7
0x12d3f  brfalse.s loc_12D8C
0x12d41  ldloc.s  6
0x12d43  ldloc.s  0xA
0x12d45  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DuplicateRuleSet::.ctor()
0x12d4a  stelem.ref
0x12d4b  ldloc.s  6
0x12d4d  ldloc.s  0xA
0x12d4f  ldelem.ref
0x12d50  ldloc.s  7
0x12d52  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DuplicateRuleSet::set_DuplicateRule(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheEntityWrapper)
0x12d57  ldarg.0
0x12d58  ldloc.s  7
0x12d5a  ldstr    aDuplicaterulei// "duplicateruleid"
0x12d5f  callvirt instance object Microsoft.Crm.Caching.CacheApplicationEntityWrapper::GetAttributeValue(string attributeName)
0x12d64  unbox.any [mscorlib]System.Guid
0x12d69  ldarg.2
0x12d6a  call     instance class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Caching.DuplicateDetectionWebServiceCacheLoader::FetchRuleConditions(valuetype [mscorlib]System.Guid ruleId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x12d6f  stloc.s  8
0x12d71  ldarg.0
0x12d72  ldloc.s  8
0x12d74  call     instance class Microsoft.Crm.Caching.CacheApplicationEntityWrapper[] Microsoft.Crm.Caching.DuplicateDetectionWebServiceCacheLoader::GetCacheEntityWrappers(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection ruleConditions)
0x12d79  stloc.s  9
0x12d7b  ldloc.s  6
0x12d7d  ldloc.s  0xA
0x12d7f  dup
0x12d80  ldc.i4.1
0x12d81  add
0x12d82  stloc.s  0xA
0x12d84  ldelem.ref
0x12d85  ldloc.s  9
0x12d87  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DuplicateRuleSet::set_DuplicateRuleConditions(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheEntityWrapper[])
0x12d8c  ldloc.s  0xB
0x12d8e  ldc.i4.1
0x12d8f  add
0x12d90  stloc.s  0xB
0x12d92  ldloc.s  0xB
0x12d94  ldloc.s  5
0x12d96  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x12d9b  blt.s    loc_12D2D
0x12d9d  ldloc.0
0x12d9e  ldloc.s  6
0x12da0  ldarg.2
0x12da1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x12da6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DuplicateRulesData::Initialize(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DuplicateRuleSet[], valuetype [mscorlib]System.Guid)
0x12dab  leave.s  loc_12DB9
0x12dad  ldloc.s  4
0x12daf  brfalse.s loc_12DB8
0x12db1  ldloc.s  4
0x12db3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12db8  endfinally
0x12db9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x12dbe  stloc.2
0x12dbf  ldloca.s 2
0x12dc1  ldloc.1
0x12dc2  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x12dc7  stloc.3
0x12dc8  ldarg.2
0x12dc9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x12dce  ldc.i4.s 0x1A
0x12dd0  ldstr    aDuplicateDetec_1// "Duplicate Detection Web Service Cache L"...
0x12dd5  ldc.i4.2
0x12dd6  newarr   [mscorlib]System.Object
0x12ddb  dup
0x12ddc  ldc.i4.0
0x12ddd  ldloca.s 2
0x12ddf  call     instance string [mscorlib]System.DateTime::ToString()
0x12de4  stelem.ref
0x12de5  dup
0x12de6  ldc.i4.1
0x12de7  ldloca.s 3
0x12de9  constrained. [mscorlib]System.TimeSpan
0x12def  callvirt instance string [mscorlib]System.Object::ToString()
0x12df4  stelem.ref
0x12df5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12dfa  ldloc.0
0x12dfb  ret
```
