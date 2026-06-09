# Microsoft.Crm.Application.Caching.RibbonCommandCacheLoader::LoadCacheData

- ea: `0x56790`
- end: `0x5699d`
- name: `Microsoft.Crm.Application.Caching.RibbonCommandCacheLoader::LoadCacheData`
- size: `525`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x566e0`
- `0x56790`
- `0x569a0`
- `0x56a00`
- `0x56b00`
- `0x5be20`
- `0xa5e70`

## string_xrefs

- `0x567cb`: `command`
- `0x56887`: `command`
- `0x567e1`: `commanddefinition`
- `0x5689e`: `commanddefinition`

## pseudocode

```c

```

## disassembly

```asm
0x56790  newobj   instance void <>c__DisplayClass0_0::.ctor()
0x56795  stloc.0
0x56796  ldloc.0
0x56797  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue>::.ctor()
0x5679c  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue> <>c__DisplayClass0_0::allCommands
0x567a1  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x567a6  brfalse  loc_5685E
0x567ab  ldarg.0
0x567ac  ldarg.2
0x567ad  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Platform.Entity> Microsoft.Crm.Application.Caching.RibbonCommandCacheLoader::GetAllEntitiesForOutlookClient(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x567b2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x567b7  stloc.1
0x567b8  br       loc_56844
0x567bd  ldloc.1
0x567be  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x567c3  stloc.2
0x567c4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::.ctor()
0x567c9  dup
0x567ca  ldloc.2
0x567cb  ldstr    aCommand_0// "command"
0x567d0  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x567d5  castclass [mscorlib]System.String
0x567da  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::set_Command(string)
0x567df  dup
0x567e0  ldloc.2
0x567e1  ldstr    aCommanddefinit// "commanddefinition"
0x567e6  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x567eb  castclass [mscorlib]System.String
0x567f0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::set_CommandDefinitionXml(string)
0x567f5  dup
0x567f6  ldloc.2
0x567f7  ldstr    aEntity// "entity"
0x567fc  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x56801  castclass [mscorlib]System.String
0x56806  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::set_EntityLogicalName(string)
0x5680b  dup
0x5680c  ldloc.2
0x5680d  ldstr    aSolutionid_0// "solutionid"
0x56812  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x56817  unbox.any [mscorlib]System.Guid
0x5681c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::set_SolutionId(valuetype [mscorlib]System.Guid)
0x56821  dup
0x56822  ldloc.2
0x56823  ldstr    aVersionnumber// "versionnumber"
0x56828  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x5682d  unbox.any [mscorlib]System.Int64
0x56832  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::set_VersionNumber(int64)
0x56837  stloc.3
0x56838  ldloc.0
0x56839  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue> <>c__DisplayClass0_0::allCommands
0x5683e  ldloc.3
0x5683f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue>::Add(var<u1>)
0x56844  ldloc.1
0x56845  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5684a  brtrue   loc_567BD
0x5684f  leave    loc_5694A
0x56854  ldloc.1
0x56855  brfalse.s loc_5685D
0x56857  ldloc.1
0x56858  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5685d  endfinally
0x5685e  ldarg.0
0x5685f  ldarg.2
0x56860  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Application.Caching.RibbonCommandCacheLoader::GetAllBusinessEntities(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x56865  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5686a  stloc.s  4
0x5686c  br       loc_56927
0x56871  ldloc.s  4
0x56873  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x56878  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5687d  stloc.s  5
0x5687f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::.ctor()
0x56884  dup
0x56885  ldloc.s  5
0x56887  ldstr    aCommand_0// "command"
0x5688c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x56891  castclass [mscorlib]System.String
0x56896  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::set_Command(string)
0x5689b  dup
0x5689c  ldloc.s  5
0x5689e  ldstr    aCommanddefinit// "commanddefinition"
0x568a3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x568a8  castclass [mscorlib]System.String
0x568ad  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::set_CommandDefinitionXml(string)
0x568b2  dup
0x568b3  ldloc.s  5
0x568b5  ldstr    aEntity// "entity"
0x568ba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x568bf  castclass [mscorlib]System.String
0x568c4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::set_EntityLogicalName(string)
0x568c9  dup
0x568ca  ldloc.s  5
0x568cc  ldstr    aSolutionid_0// "solutionid"
0x568d1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x568d6  unbox.any [mscorlib]System.Guid
0x568db  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::set_SolutionId(valuetype [mscorlib]System.Guid)
0x568e0  dup
0x568e1  ldloc.s  5
0x568e3  ldstr    aVersionnumber// "versionnumber"
0x568e8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x568ed  unbox.any [mscorlib]System.Int64
0x568f2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::set_VersionNumber(int64)
0x568f7  dup
0x568f8  ldloc.s  5
0x568fa  ldstr    aSolution1Modif// "solution1.modifiedon"
0x568ff  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x56904  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x56909  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x5690e  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x56913  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue::set_SolutionModifiedOn(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0x56918  stloc.s  6
0x5691a  ldloc.0
0x5691b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue> <>c__DisplayClass0_0::allCommands
0x56920  ldloc.s  6
0x56922  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue>::Add(var<u1>)
0x56927  ldloc.s  4
0x56929  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5692e  brtrue   loc_56871
0x56933  leave.s  loc_5694A
0x56935  ldloc.s  4
0x56937  isinst   [mscorlib]System.IDisposable
0x5693c  stloc.s  7
0x5693e  ldloc.s  7
0x56940  brfalse.s loc_56949
0x56942  ldloc.s  7
0x56944  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x56949  endfinally
0x5694a  ldarg.0
0x5694b  ldarg.2
0x5694c  ldloc.0
0x5694d  ldftn    instance void <>c__DisplayClass0_0::<LoadCacheData>b__0(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x56953  newobj   instance void class [mscorlib]System.Action`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext>::.ctor(object, native int)
0x56958  call     instance void Microsoft.Crm.Application.Caching.RibbonCommandCacheLoader::RunInExecutionContext(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class [mscorlib]System.Action`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext> action)
0x5695d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandsCacheValue::.ctor()
0x56962  dup
0x56963  ldloc.0
0x56964  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue> <>c__DisplayClass0_0::allCommands
0x56969  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue> <>c::<>9__0_1
0x5696e  dup
0x5696f  brtrue.s loc_56988
0x56971  pop
0x56972  ldsfld   class <>c <>c::<>9
0x56977  ldftn    instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue <>c::<LoadCacheData>b__0_1(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue entity)
0x5697d  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue>::.ctor(object, native int)
0x56982  dup
0x56983  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue> <>c::<>9__0_1
0x56988  newobj   instance void Microsoft.Crm.Application.Caching.RibbonCommandComparer::.ctor()
0x5698d  call     T0x2B00008C
0x56992  call     T0x2B00008D
0x56997  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCacheValue> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandsCacheValue::AllCommands
0x5699c  ret
```
