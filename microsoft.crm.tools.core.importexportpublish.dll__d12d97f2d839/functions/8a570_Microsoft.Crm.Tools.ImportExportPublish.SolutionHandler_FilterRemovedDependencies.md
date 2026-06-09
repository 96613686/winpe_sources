# Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::FilterRemovedDependencies

- ea: `0x8a570`
- end: `0x8a6ac`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::FilterRemovedDependencies`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x89dc0`

## callees

- `0x3a780`
- `0x3aa60`
- `0x3aa80`
- `0x8a570`
- `0x8a6e0`

## string_xrefs

- `0x8a592`: `requiredcomponentintroducedversion`
- `0x8a60f`: `requiredcomponentintroducedversion`
- `0x8a642`: `requiredcomponentintroducedversion`
- `0x8a5cc`: `dependentcomponentobjectid`
- `0x8a5ba`: `dependentcomponenttype`
- `0x8a61c`: `requiredcomponentbasesolutionid`
- `0x8a629`: `requiredcomponentbasesolutionid`

## pseudocode

```c

```

## disassembly

```asm
0x8a570  ldstr    aDependency_1// "Dependency"
0x8a575  ldarg.2
0x8a576  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8a57b  stloc.0
0x8a57c  ldarg.0
0x8a57d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x8a582  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x8a587  ldstr    aDependency_1// "Dependency"
0x8a58c  ldc.i4.0
0x8a58d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8a592  ldstr    aRequiredcompon_1// "requiredcomponentintroducedversion"
0x8a597  ldc.i4.1
0x8a598  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8a59d  ldnull
0x8a59e  cgt.un
0x8a5a0  stloc.1
0x8a5a1  ldarg.1
0x8a5a2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x8a5a7  stloc.2
0x8a5a8  br       loc_8A689
0x8a5ad  ldloc.2
0x8a5ae  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8a5b3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x8a5b8  stloc.3
0x8a5b9  ldloc.3
0x8a5ba  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x8a5bf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8a5c4  unbox.any [mscorlib]System.Int32
0x8a5c9  stloc.s  4
0x8a5cb  ldloc.3
0x8a5cc  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x8a5d1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8a5d6  unbox.any [mscorlib]System.Guid
0x8a5db  stloc.s  5
0x8a5dd  ldc.i4.1
0x8a5de  stloc.s  6
0x8a5e0  ldarg.0
0x8a5e1  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::get_ExportToTargetVersionContext()
0x8a5e6  ldloc.s  5
0x8a5e8  ldloc.s  4
0x8a5ea  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0)
0x8a5ef  ldc.i4.0
0x8a5f0  ldnull
0x8a5f1  callvirt instance valuetype Microsoft.Crm.Tools.ImportExportPublish.ComponentAction Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::ActionToBeTakenOnComponent(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32> dependentComponent, bool addFilteredComponentComment, [opt] class [mscorlib]System.Version introducedVersion)
0x8a5f6  ldc.i4.1
0x8a5f7  bne.un.s loc_8A5FE
0x8a5f9  ldc.i4.0
0x8a5fa  stloc.s  6
0x8a5fc  br.s     loc_8A67D
0x8a5fe  ldarg.0
0x8a5ff  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::get_ExportToTargetVersionContext()
0x8a604  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::IsTargetVersionSpecified()
0x8a609  brfalse.s loc_8A67D
0x8a60b  ldloc.1
0x8a60c  brfalse.s loc_8A67D
0x8a60e  ldloc.3
0x8a60f  ldstr    aRequiredcompon_1// "requiredcomponentintroducedversion"
0x8a614  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x8a619  brtrue.s loc_8A67D
0x8a61b  ldloc.3
0x8a61c  ldstr    aRequiredcompon_2// "requiredcomponentbasesolutionid"
0x8a621  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x8a626  brtrue.s loc_8A63A
0x8a628  ldloc.3
0x8a629  ldstr    aRequiredcompon_2// "requiredcomponentbasesolutionid"
0x8a62e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8a633  unbox.any [mscorlib]System.Guid
0x8a638  br.s     loc_8A63F
0x8a63a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8a63f  stloc.s  7
0x8a641  ldloc.3
0x8a642  ldstr    aRequiredcompon_1// "requiredcomponentintroducedversion"
0x8a647  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8a64c  unbox.any [mscorlib]System.Double
0x8a651  ldarg.0
0x8a652  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::get_ExportToTargetVersionContext()
0x8a657  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x8a65c  callvirt instance string [mscorlib]System.Object::ToString()
0x8a661  call     valuetype [mscorlib]System.Nullable`1<float64> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyNodeService::ConvertVersionToDouble(string)
0x8a666  stloc.s  8
0x8a668  ldloca.s 8
0x8a66a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<float64>::get_Value()
0x8a66f  ble.un.s loc_8A67D
0x8a671  ldloc.s  7
0x8a673  call     bool [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::IsSystemSolution(valuetype [mscorlib]System.Guid)
0x8a678  brfalse.s loc_8A67D
0x8a67a  ldc.i4.0
0x8a67b  stloc.s  6
0x8a67d  ldloc.s  6
0x8a67f  brfalse.s loc_8A689
0x8a681  ldloc.0
0x8a682  ldloc.3
0x8a683  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x8a688  pop
0x8a689  ldloc.2
0x8a68a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8a68f  brtrue   loc_8A5AD
0x8a694  leave.s  loc_8A6AA
0x8a696  ldloc.2
0x8a697  isinst   [mscorlib]System.IDisposable
0x8a69c  stloc.s  9
0x8a69e  ldloc.s  9
0x8a6a0  brfalse.s loc_8A6A9
0x8a6a2  ldloc.s  9
0x8a6a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8a6a9  endfinally
0x8a6aa  ldloc.0
0x8a6ab  ret
```
