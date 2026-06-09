# Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::CanHandleDependency

- ea: `0x84e70`
- end: `0x8532f`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::CanHandleDependency`
- size: `1215`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x3a6f0`
- `0x3a780`
- `0x3a7c0`
- `0x3af00`
- `0x84c70`
- `0x84e70`
- `0x85330`
- `0x85350`
- `0x853d0`

## string_xrefs

- `0x84f02`: `layoutxml`
- `0x84efa`: `columnsetxml`
- `0x851e1`: `columnsetxml`
- `0x84ef2`: `fetchxml`
- `0x84f44`: `fetchxml`
- `0x852e2`: `requiredcomponentobjectid`
- `0x8504a`: `/fetch/entity//link-entity`
- `0x850a0`: `link-type`

## pseudocode

```c

```

## disassembly

```asm
0x84e70  ldarg.0
0x84e71  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::get_ExportToTargetVersionContext()
0x84e76  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>> Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_DependencyInfo()
0x84e7b  ldarg.1
0x84e7c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>>::get_Item(void)
0x84e81  stloc.0
0x84e82  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x84e87  stloc.1
0x84e88  ldarg.0
0x84e89  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::get_ExportToTargetVersionContext()
0x84e8e  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x84e93  stloc.2
0x84e94  ldloc.0
0x84e95  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::GetEnumerator()
0x84e9a  stloc.s  8
0x84e9c  br.s     loc_84EBA
0x84e9e  ldloca.s 8
0x84ea0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::get_Current()
0x84ea5  stloc.s  9
0x84ea7  ldarg.0
0x84ea8  ldloc.s  9
0x84eaa  ldloc.2
0x84eab  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::CheckIfDependentComponentHasHigherVersionDependencyFeatureRequirement(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity dependentComponent, class [mscorlib]System.Version targetVersion)
0x84eb0  brfalse.s loc_84EBA
0x84eb2  ldc.i4.0
0x84eb3  stloc.s  0xA
0x84eb5  leave    loc_8532C
0x84eba  ldloca.s 8
0x84ebc  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::MoveNext()
0x84ec1  brtrue.s loc_84E9E
0x84ec3  leave.s  loc_84ED3
0x84ec5  ldloca.s 8
0x84ec7  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>
0x84ecd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x84ed2  endfinally
0x84ed3  ldstr    aSavedquery// "SavedQuery"
0x84ed8  ldarg.0
0x84ed9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84ede  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x84ee3  stloc.3
0x84ee4  ldloc.3
0x84ee5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x84eea  ldc.i4.4
0x84eeb  newarr   [mscorlib]System.String
0x84ef0  dup
0x84ef1  ldc.i4.0
0x84ef2  ldstr    aFetchxml// "fetchxml"
0x84ef7  stelem.ref
0x84ef8  dup
0x84ef9  ldc.i4.1
0x84efa  ldstr    aColumnsetxml// "columnsetxml"
0x84eff  stelem.ref
0x84f00  dup
0x84f01  ldc.i4.2
0x84f02  ldstr    aLayoutxml// "layoutxml"
0x84f07  stelem.ref
0x84f08  dup
0x84f09  ldc.i4.3
0x84f0a  ldstr    aReturnedtypeco// "returnedtypecode"
0x84f0f  stelem.ref
0x84f10  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x84f15  ldarg.1
0x84f16  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>::get_Item1()
0x84f1b  ldstr    aSavedquery// "SavedQuery"
0x84f20  ldarg.0
0x84f21  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84f26  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x84f2b  stloc.s  4
0x84f2d  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryService::.ctor()
0x84f32  ldloc.s  4
0x84f34  ldloc.3
0x84f35  ldarg.0
0x84f36  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84f3b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x84f40  stloc.s  5
0x84f42  ldloc.s  5
0x84f44  ldstr    aFetchxml// "fetchxml"
0x84f49  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x84f4e  isinst   [mscorlib]System.String
0x84f53  stloc.s  6
0x84f55  ldloc.s  6
0x84f57  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x84f5c  brtrue   loc_851DF
0x84f61  ldloc.s  6
0x84f63  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x84f68  stloc.s  0xB
0x84f6a  ldloc.s  0xB
0x84f6c  newobj   instance void [System.Xml]System.Xml.XPath.XPathDocument::.ctor(class [mscorlib]System.IO.TextReader)
0x84f71  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathDocument::CreateNavigator()
0x84f76  stloc.s  0xC
0x84f78  ldloc.s  0xC
0x84f7a  ldstr    aFetchEntityNam// "/fetch/entity/@name"
0x84f7f  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x84f84  stloc.s  0xD
0x84f86  ldloc.s  0xD
0x84f88  brfalse  loc_851D1
0x84f8d  ldloc.s  0xD
0x84f8f  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x84f94  stloc.s  0xE
0x84f96  ldloc.s  0xC
0x84f98  ldstr    aFetchEntityFil_0// "/fetch/entity/filter/condition/@operato"...
0x84f9d  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x84fa2  stloc.s  0xF
0x84fa4  ldarg.0
0x84fa5  ldloc.s  0xF
0x84fa7  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::HasFeatureDependency(class [System.Xml]System.Xml.XPath.XPathNodeIterator nodeIterator)
0x84fac  brfalse.s loc_84FB6
0x84fae  ldc.i4.0
0x84faf  stloc.s  0xA
0x84fb1  leave    loc_8532C
0x84fb6  ldloc.s  0xC
0x84fb8  ldstr    aFetchEntityFil_1// "/fetch/entity/filter/condition/@value"
0x84fbd  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x84fc2  stloc.s  0x10
0x84fc4  ldarg.0
0x84fc5  ldloc.s  0x10
0x84fc7  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::HasDateTimeFeatureDependency(class [System.Xml]System.Xml.XPath.XPathNodeIterator nodeIterator)
0x84fcc  brfalse.s loc_84FD6
0x84fce  ldc.i4.0
0x84fcf  stloc.s  0xA
0x84fd1  leave    loc_8532C
0x84fd6  ldloc.s  0xC
0x84fd8  ldstr    aFetchEntityFil_2// "/fetch/entity/filter[not(@type) or @typ"...
0x84fdd  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x84fe2  stloc.s  0xF
0x84fe4  ldloc.s  0xF
0x84fe6  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XPath.XPathNodeIterator::GetEnumerator()
0x84feb  stloc.s  0x12
0x84fed  br.s     loc_85028
0x84fef  ldloc.s  0x12
0x84ff1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x84ff6  castclass [System.Xml]System.Xml.XPath.XPathItem
0x84ffb  stloc.s  0x13
0x84ffd  ldarg.0
0x84ffe  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::metadataCache
0x85003  ldloc.s  0xE
0x85005  ldc.i4.1
0x85006  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8500b  ldloc.s  0x13
0x8500d  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x85012  ldc.i4.1
0x85013  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x85018  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x8501d  stloc.s  0x14
0x8501f  ldloc.1
0x85020  ldloc.s  0x14
0x85022  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x85027  pop
0x85028  ldloc.s  0x12
0x8502a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8502f  brtrue.s loc_84FEF
0x85031  leave.s  loc_85048
0x85033  ldloc.s  0x12
0x85035  isinst   [mscorlib]System.IDisposable
0x8503a  stloc.s  0x15
0x8503c  ldloc.s  0x15
0x8503e  brfalse.s loc_85047
0x85040  ldloc.s  0x15
0x85042  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x85047  endfinally
0x85048  ldloc.s  0xC
0x8504a  ldstr    aFetchEntityLin// "/fetch/entity//link-entity"
0x8504f  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x85054  stloc.s  0x11
0x85056  ldloc.s  0x11
0x85058  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x8505d  brfalse  loc_851D1
0x85062  ldloc.s  0x11
0x85064  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x85069  dup
0x8506a  ldstr    aName// "name"
0x8506f  ldstr    asc_9A18C// ""
0x85074  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x85079  stloc.s  0x16
0x8507b  dup
0x8507c  ldstr    aTo// "to"
0x85081  ldstr    asc_9A18C// ""
0x85086  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x8508b  stloc.s  0x17
0x8508d  dup
0x8508e  ldstr    aFrom// "from"
0x85093  ldstr    asc_9A18C// ""
0x85098  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x8509d  stloc.s  0x18
0x8509f  dup
0x850a0  ldstr    aLinkType// "link-type"
0x850a5  ldstr    asc_9A18C// ""
0x850aa  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x850af  stloc.s  0x19
0x850b1  ldloc.s  0xE
0x850b3  ldloc.s  0x16
0x850b5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x850ba  brfalse.s loc_8510A
0x850bc  ldarg.0
0x850bd  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::metadataCache
0x850c2  ldloc.s  0x16
0x850c4  ldc.i4.1
0x850c5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x850ca  ldloc.s  0x18
0x850cc  ldc.i4.1
0x850cd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x850d2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x850d7  stloc.s  0x1A
0x850d9  ldloc.1
0x850da  ldloc.s  0x1A
0x850dc  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x850e1  pop
0x850e2  ldarg.0
0x850e3  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::metadataCache
0x850e8  ldloc.s  0x16
0x850ea  ldc.i4.1
0x850eb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x850f0  ldloc.s  0x17
0x850f2  ldc.i4.1
0x850f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x850f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x850fd  stloc.s  0x1A
0x850ff  ldloc.1
0x85100  ldloc.s  0x1A
0x85102  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x85107  pop
0x85108  br.s     loc_85165
0x8510a  ldarg.0
0x8510b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::metadataCache
0x85110  ldloc.s  0x16
0x85112  ldc.i4.1
0x85113  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x85118  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x8511d  stloc.s  0x1B
0x8511f  ldloc.1
0x85120  ldloc.s  0x1B
0x85122  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x85127  pop
0x85128  ldloc.s  0x19
0x8512a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8512f  brtrue.s loc_85165
0x85131  ldloc.s  0x19
0x85133  ldstr    aInner// "inner"
0x85138  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8513d  brfalse.s loc_85165
0x8513f  ldarg.0
0x85140  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::metadataCache
0x85145  ldloc.s  0x16
0x85147  ldc.i4.1
0x85148  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8514d  ldloc.s  0x18
0x8514f  ldc.i4.1
0x85150  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x85155  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x8515a  stloc.s  0x1C
0x8515c  ldloc.1
0x8515d  ldloc.s  0x1C
0x8515f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x85164  pop
0x85165  ldstr    aFilterNotTypeO// "./filter[not(@type) or @type!=\"or\"]//"...
0x8516a  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x8516f  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XPath.XPathNodeIterator::GetEnumerator()
0x85174  stloc.s  0x12
0x85176  br.s     loc_851B1
0x85178  ldloc.s  0x12
0x8517a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8517f  castclass [System.Xml]System.Xml.XPath.XPathItem
0x85184  stloc.s  0x1D
0x85186  ldarg.0
0x85187  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::metadataCache
0x8518c  ldloc.s  0x16
0x8518e  ldc.i4.1
0x8518f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x85194  ldloc.s  0x1D
0x85196  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x8519b  ldc.i4.1
0x8519c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x851a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x851a6  stloc.s  0x1E
0x851a8  ldloc.1
0x851a9  ldloc.s  0x1E
0x851ab  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x851b0  pop
0x851b1  ldloc.s  0x12
0x851b3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x851b8  brtrue.s loc_85178
0x851ba  leave.s  loc_851DF
0x851bc  ldloc.s  0x12
0x851be  isinst   [mscorlib]System.IDisposable
0x851c3  stloc.s  0x15
0x851c5  ldloc.s  0x15
0x851c7  brfalse.s loc_851D0
0x851c9  ldloc.s  0x15
0x851cb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x851d0  endfinally
0x851d1  leave.s  loc_851DF
0x851d3  ldloc.s  0xB
0x851d5  brfalse.s loc_851DE
0x851d7  ldloc.s  0xB
0x851d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x851de  endfinally
0x851df  ldloc.s  5
0x851e1  ldstr    aColumnsetxml// "columnsetxml"
0x851e6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x851eb  isinst   [mscorlib]System.String
  ... truncated ...
```
