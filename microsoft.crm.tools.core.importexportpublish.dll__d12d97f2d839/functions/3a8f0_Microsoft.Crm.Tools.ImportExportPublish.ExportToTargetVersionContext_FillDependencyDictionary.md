# Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::FillDependencyDictionary

- ea: `0x3a8f0`
- end: `0x3aa5c`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::FillDependencyDictionary`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x75980`

## callees

- `0x3a780`
- `0x3a8f0`
- `0x3aa60`

## string_xrefs

- `0x3a98c`: `requiredcomponentobjectid`
- `0x3a99c`: `requiredcomponenttype`
- `0x3a9eb`: `requiredcomponentintroducedversion`
- `0x3a9f8`: `requiredcomponentintroducedversion`
- `0x3a933`: `dependentcomponentobjectid`
- `0x3a943`: `dependentcomponenttype`

## pseudocode

```c

```

## disassembly

```asm
0x3a8f0  ldarg.1
0x3a8f1  ldstr    aSolutionid_0// "solutionId"
0x3a8f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3a8fb  ldarg.0
0x3a8fc  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::IsTargetVersionSpecified()
0x3a901  brtrue.s loc_3A904
0x3a903  ret
0x3a904  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyProcessor::.ctor()
0x3a909  ldarg.1
0x3a90a  ldarg.0
0x3a90b  ldfld    class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::_targetVersion
0x3a910  ldarg.0
0x3a911  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::_context
0x3a916  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyProcessor::RetrieveDependenciesForCompatibility(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3a91b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3a920  stloc.0
0x3a921  br       loc_3AA3A
0x3a926  ldloc.0
0x3a927  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3a92c  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x3a931  stloc.1
0x3a932  ldloc.1
0x3a933  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x3a938  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3a93d  unbox.any [mscorlib]System.Guid
0x3a942  ldloc.1
0x3a943  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x3a948  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3a94d  unbox.any [mscorlib]System.Int32
0x3a952  stloc.2
0x3a953  ldloc.2
0x3a954  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0)
0x3a959  stloc.3
0x3a95a  ldarg.0
0x3a95b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>> Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::_dependencyInfo
0x3a960  ldloc.3
0x3a961  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>>::ContainsKey(var<u1>)
0x3a966  brtrue.s loc_3A979
0x3a968  ldarg.0
0x3a969  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>> Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::_dependencyInfo
0x3a96e  ldloc.3
0x3a96f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::.ctor()
0x3a974  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>>::Add(var<u1>, !!T0)
0x3a979  ldarg.0
0x3a97a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>> Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::_dependencyInfo
0x3a97f  ldloc.3
0x3a980  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>>::get_Item(void)
0x3a985  ldloc.1
0x3a986  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::Add(var<u1>)
0x3a98b  ldloc.1
0x3a98c  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x3a991  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3a996  unbox.any [mscorlib]System.Guid
0x3a99b  ldloc.1
0x3a99c  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x3a9a1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3a9a6  unbox.any [mscorlib]System.Int32
0x3a9ab  stloc.s  4
0x3a9ad  ldloc.s  4
0x3a9af  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0)
0x3a9b4  stloc.s  5
0x3a9b6  ldarg.0
0x3a9b7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>>> Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::_parentInfo
0x3a9bc  ldloc.s  5
0x3a9be  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>>>::ContainsKey(var<u1>)
0x3a9c3  brtrue.s loc_3A9D7
0x3a9c5  ldarg.0
0x3a9c6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>>> Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::_parentInfo
0x3a9cb  ldloc.s  5
0x3a9cd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>>::.ctor()
0x3a9d2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>>>::Add(var<u1>, !!T0)
0x3a9d7  ldarg.0
0x3a9d8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>>> Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::_parentInfo
0x3a9dd  ldloc.s  5
0x3a9df  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>>>::get_Item(void)
0x3a9e4  ldloc.3
0x3a9e5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>>::Add(var<u1>)
0x3a9ea  ldloc.1
0x3a9eb  ldstr    aRequiredcompon_1// "requiredcomponentintroducedversion"
0x3a9f0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x3a9f5  brtrue.s loc_3AA3A
0x3a9f7  ldloc.1
0x3a9f8  ldstr    aRequiredcompon_1// "requiredcomponentintroducedversion"
0x3a9fd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3aa02  unbox.any [mscorlib]System.Double
0x3aa07  stloc.s  6
0x3aa09  ldloca.s 6
0x3aa0b  ldstr    a00// "0.0"
0x3aa10  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3aa15  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x3aa1a  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x3aa1f  ldarg.0
0x3aa20  call     instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x3aa25  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x3aa2a  brfalse.s loc_3AA3A
0x3aa2c  ldarg.0
0x3aa2d  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>> Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::_higherVersionComponents
0x3aa32  ldloc.s  5
0x3aa34  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>>::Add(var<u1>)
0x3aa39  pop
0x3aa3a  ldloc.0
0x3aa3b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3aa40  brtrue   loc_3A926
0x3aa45  leave.s  loc_3AA5B
0x3aa47  ldloc.0
0x3aa48  isinst   [mscorlib]System.IDisposable
0x3aa4d  stloc.s  7
0x3aa4f  ldloc.s  7
0x3aa51  brfalse.s loc_3AA5A
0x3aa53  ldloc.s  7
0x3aa55  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3aa5a  endfinally
0x3aa5b  ret
```
