# Microsoft.Crm.Common.Yammer.YammerState::IsYammerEnabledActivityFeedsSolutionInstalled

- ea: `0x630`
- end: `0x718`
- name: `Microsoft.Crm.Common.Yammer.YammerState::IsYammerEnabledActivityFeedsSolutionInstalled`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x480`

## callees

- `0x630`

## pseudocode

```c

```

## disassembly

```asm
0x630  ldnull
0x631  stloc.1
0x632  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0x637  ldstr    aActivityfeedsc// "ActivityFeedsCore"
0x63c  ldarg.0
0x63d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x642  ldloca.s 0
0x644  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::TryLookupSolutionId(string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid&)
0x649  brfalse.s loc_65D
0x64b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0x650  ldloc.0
0x651  ldarg.0
0x652  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution>::LookupEntry(void, var<u1>)
0x657  stloc.1
0x658  br       loc_6F8
0x65d  ldstr    aSolution// "solution"
0x662  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x667  dup
0x668  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x66d  ldstr    aSolutionid// "solutionid"
0x672  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x677  dup
0x678  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x67d  ldstr    aUniquename// "uniquename"
0x682  ldc.i4.0
0x683  ldstr    aActivityfeedsc// "ActivityFeedsCore"
0x688  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x68d  ldc.i4.0
0x68e  ldc.i4.1
0x68f  ldarg.0
0x690  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, bool, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x695  stloc.3
0x696  ldloc.3
0x697  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x69c  ldc.i4.1
0x69d  cgt
0x69f  ldc.i4.0
0x6a0  ceq
0x6a2  ldstr    aThereShouldOnl// "There should only be one solution with "...
0x6a7  ldc.i4.2
0x6a8  newarr   [mscorlib]System.Object
0x6ad  dup
0x6ae  ldc.i4.0
0x6af  ldstr    aActivityfeedsc// "ActivityFeedsCore"
0x6b4  stelem.ref
0x6b5  dup
0x6b6  ldc.i4.1
0x6b7  ldloc.3
0x6b8  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6bd  box      [mscorlib]System.Int32
0x6c2  stelem.ref
0x6c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x6c8  ldloc.3
0x6c9  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6ce  brfalse.s loc_6F6
0x6d0  ldloc.3
0x6d1  ldc.i4.0
0x6d2  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x6d7  ldstr    aSolutionid// "solutionid"
0x6dc  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6e1  unbox.any [mscorlib]System.Guid
0x6e6  stloc.0
0x6e7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0x6ec  ldloc.0
0x6ed  ldarg.0
0x6ee  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution>::LookupEntry(void, var<u1>)
0x6f3  stloc.1
0x6f4  br.s     loc_6F8
0x6f6  ldc.i4.0
0x6f7  ret
0x6f8  ldloc.1
0x6f9  brfalse.s loc_716
0x6fb  ldloc.1
0x6fc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_Version()
0x701  ldloca.s 2
0x703  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0x708  brfalse.s loc_716
0x70a  ldloc.2
0x70b  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Common.Yammer.YammerState::ActivityFeedsYammerMinSolutionVersion
0x710  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x715  ret
0x716  ldc.i4.0
0x717  ret
```
