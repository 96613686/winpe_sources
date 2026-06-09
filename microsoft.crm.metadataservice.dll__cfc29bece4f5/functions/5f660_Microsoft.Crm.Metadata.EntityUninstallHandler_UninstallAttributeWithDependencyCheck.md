# Microsoft.Crm.Metadata.EntityUninstallHandler::UninstallAttributeWithDependencyCheck

- ea: `0x5f660`
- end: `0x5f80b`
- name: `Microsoft.Crm.Metadata.EntityUninstallHandler::UninstallAttributeWithDependencyCheck`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5f5d0`
- `0x5f660`

## callees

- `0x5f660`
- `0x5f810`

## string_xrefs

- `0x5f6be`: `dependentcomponentobjectid`
- `0x5f6d4`: `dependentcomponentparentid`
- `0x5f6e9`: `dependentcomponentparentid`

## pseudocode

```c

```

## disassembly

```asm
0x5f660  ldarg.0
0x5f661  ldarg.s  4
0x5f663  ldarg.s  7
0x5f665  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5f66a  call     instance bool Microsoft.Crm.Metadata.EntityUninstallHandler::SkipAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5f66f  brtrue   loc_5F80A
0x5f674  ldarg.s  5
0x5f676  ldarg.s  4
0x5f678  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x5f67d  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x5f682  brtrue   loc_5F80A
0x5f687  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::.ctor()
0x5f68c  ldarg.s  4
0x5f68e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x5f693  ldc.i4.2
0x5f694  ldarg.s  7
0x5f696  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5f69b  ldc.i4.1
0x5f69c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::RetrieveDependentComponentsInternal(valuetype [mscorlib]System.Guid, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x5f6a1  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5f6a6  stloc.0
0x5f6a7  br       loc_5F7CE
0x5f6ac  ldloc.0
0x5f6ad  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5f6b2  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5f6b7  stloc.1
0x5f6b8  ldloc.1
0x5f6b9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x5f6be  ldstr    aDependentcompo_1// "dependentcomponentobjectid"
0x5f6c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x5f6c8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x5f6cd  unbox.any [mscorlib]System.Guid
0x5f6d2  stloc.2
0x5f6d3  ldloc.1
0x5f6d4  ldstr    aDependentcompo_2// "dependentcomponentparentid"
0x5f6d9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5f6de  brtrue   loc_5F7CE
0x5f6e3  ldloc.1
0x5f6e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x5f6e9  ldstr    aDependentcompo_2// "dependentcomponentparentid"
0x5f6ee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x5f6f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x5f6f8  unbox.any [mscorlib]System.Guid
0x5f6fd  ldarg.s  4
0x5f6ff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_EntityId()
0x5f704  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5f709  brfalse  loc_5F7CE
0x5f70e  ldloca.s 2
0x5f710  ldarg.s  6
0x5f712  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x5f717  brtrue   loc_5F7CE
0x5f71c  ldarg.3
0x5f71d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesById()
0x5f722  ldloc.2
0x5f723  box      [mscorlib]System.Guid
0x5f728  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x5f72d  brfalse  loc_5F7CE
0x5f732  ldarg.s  8
0x5f734  ldc.i4.s 0xA
0x5f736  ble.s    loc_5F7AA
0x5f738  ldnull
0x5f739  ldarg.s  7
0x5f73b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5f740  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5f745  ldc.i4.s 0x38
0x5f747  ldstr    aDependencyChai// "Dependency Chain Length is not expected"...
0x5f74c  ldc.i4.3
0x5f74d  newarr   [mscorlib]System.Object
0x5f752  dup
0x5f753  ldc.i4.0
0x5f754  ldarg.s  4
0x5f756  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x5f75b  box      [mscorlib]System.Guid
0x5f760  stelem.ref
0x5f761  dup
0x5f762  ldc.i4.1
0x5f763  ldloc.2
0x5f764  box      [mscorlib]System.Guid
0x5f769  stelem.ref
0x5f76a  dup
0x5f76b  ldc.i4.2
0x5f76c  ldarg.3
0x5f76d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x5f772  box      [mscorlib]System.Guid
0x5f777  stelem.ref
0x5f778  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5f77d  ldstr    aDependencyChai// "Dependency Chain Length is not expected"...
0x5f782  ldarg.s  4
0x5f784  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x5f789  box      [mscorlib]System.Guid
0x5f78e  ldloc.2
0x5f78f  box      [mscorlib]System.Guid
0x5f794  ldarg.3
0x5f795  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x5f79a  box      [mscorlib]System.Guid
0x5f79f  call     string [mscorlib]System.String::Format(string, object, object, object)
0x5f7a4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x5f7a9  throw
0x5f7aa  ldarg.0
0x5f7ab  ldarg.1
0x5f7ac  ldarg.2
0x5f7ad  ldarg.3
0x5f7ae  ldarg.3
0x5f7af  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesById()
0x5f7b4  ldloc.2
0x5f7b5  box      [mscorlib]System.Guid
0x5f7ba  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x5f7bf  ldarg.s  5
0x5f7c1  ldarg.s  6
0x5f7c3  ldarg.s  7
0x5f7c5  ldarg.s  8
0x5f7c7  ldc.i4.1
0x5f7c8  add
0x5f7c9  call     instance void Microsoft.Crm.Metadata.EntityUninstallHandler::UninstallAttributeWithDependencyCheck(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentUninstaller uninstaller, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData attributeTypeMapData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> deletedAttributes, valuetype [mscorlib]System.Guid originalAttributeId, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext, int32 recursionDepth)
0x5f7ce  ldloc.0
0x5f7cf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5f7d4  brtrue   loc_5F6AC
0x5f7d9  leave.s  loc_5F7EC
0x5f7db  ldloc.0
0x5f7dc  isinst   [mscorlib]System.IDisposable
0x5f7e1  stloc.3
0x5f7e2  ldloc.3
0x5f7e3  brfalse.s loc_5F7EB
0x5f7e5  ldloc.3
0x5f7e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f7eb  endfinally
0x5f7ec  ldarg.1
0x5f7ed  ldarg.2
0x5f7ee  ldarg.s  4
0x5f7f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x5f7f5  ldarg.s  7
0x5f7f7  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentUninstaller::Uninstall(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext)
0x5f7fc  ldarg.s  5
0x5f7fe  ldarg.s  4
0x5f800  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x5f805  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x5f80a  ret
```
