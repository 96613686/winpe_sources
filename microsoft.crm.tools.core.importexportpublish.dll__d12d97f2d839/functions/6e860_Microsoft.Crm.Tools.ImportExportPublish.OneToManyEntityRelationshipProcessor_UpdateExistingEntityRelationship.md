# Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::UpdateExistingEntityRelationship

- ea: `0x6e860`
- end: `0x6f1e2`
- name: `Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::UpdateExistingEntityRelationship`
- size: `2434`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x31520`
- `0x31580`
- `0x317b0`
- `0x31b30`
- `0x6e820`
- `0x6e860`
- `0x6f230`
- `0x6f2d0`
- `0x6f320`
- `0x6f360`
- `0x6f470`

## string_xrefs

- `0x6ebd1`: `linkedattributeid`
- `0x6ed2b`: `linkedattributeid`
- `0x6ed3a`: `linkedattributeid`
- `0x6eef7`: `IsRenameable`
- `0x6ebf9`: `isrenameable`
- `0x6ecbc`: `isrenameable`
- `0x6eccb`: `isrenameable`
- `0x6e89f`: `CascadeDelete`
- `0x6e8b7`: `CascadeDelete`
- `0x6f156`: `Import_BEGIN_{0}.ImportItem: RelationshipService.Update`
- `0x6f183`: `Import_END_{0}.ImportItem: RelationshipService.Update`

## pseudocode

```c

```

## disassembly

```asm
0x6e860  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::.ctor()
0x6e865  stloc.0
0x6e866  ldarg.1
0x6e867  ldstr    aCascadeassign_0// "CascadeAssign"
0x6e86c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e871  brfalse.s loc_6E89E
0x6e873  ldloc.0
0x6e874  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e879  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6e87e  ldarg.1
0x6e87f  ldstr    aCascadeassign_0// "CascadeAssign"
0x6e884  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e889  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6e88e  ldc.i4.1
0x6e88f  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x6e894  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e899  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeAssign(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6e89e  ldarg.1
0x6e89f  ldstr    aCascadedelete_0// "CascadeDelete"
0x6e8a4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e8a9  brfalse.s loc_6E8D6
0x6e8ab  ldloc.0
0x6e8ac  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e8b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6e8b6  ldarg.1
0x6e8b7  ldstr    aCascadedelete_0// "CascadeDelete"
0x6e8bc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e8c1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6e8c6  ldc.i4.1
0x6e8c7  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x6e8cc  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e8d1  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6e8d6  ldarg.s  7
0x6e8d8  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x6e8dd  brfalse.s loc_6E917
0x6e8df  ldarg.1
0x6e8e0  ldstr    aCascademerge_0// "CascadeMerge"
0x6e8e5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e8ea  brfalse.s loc_6E917
0x6e8ec  ldloc.0
0x6e8ed  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e8f2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6e8f7  ldarg.1
0x6e8f8  ldstr    aCascademerge_0// "CascadeMerge"
0x6e8fd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e902  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6e907  ldc.i4.1
0x6e908  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x6e90d  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e912  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeMerge(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6e917  ldarg.1
0x6e918  ldstr    aCascadereparen_0// "CascadeReparent"
0x6e91d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e922  brfalse.s loc_6E94F
0x6e924  ldloc.0
0x6e925  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e92a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6e92f  ldarg.1
0x6e930  ldstr    aCascadereparen_0// "CascadeReparent"
0x6e935  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e93a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6e93f  ldc.i4.1
0x6e940  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x6e945  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e94a  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeReparent(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6e94f  ldarg.1
0x6e950  ldstr    aCascadeshare_0// "CascadeShare"
0x6e955  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e95a  brfalse.s loc_6E987
0x6e95c  ldloc.0
0x6e95d  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e962  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6e967  ldarg.1
0x6e968  ldstr    aCascadeshare_0// "CascadeShare"
0x6e96d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e972  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6e977  ldc.i4.1
0x6e978  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x6e97d  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e982  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeShare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6e987  ldarg.1
0x6e988  ldstr    aCascadeunshare_0// "CascadeUnshare"
0x6e98d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e992  brfalse.s loc_6E9BF
0x6e994  ldloc.0
0x6e995  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e99a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6e99f  ldarg.1
0x6e9a0  ldstr    aCascadeunshare_0// "CascadeUnshare"
0x6e9a5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e9aa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6e9af  ldc.i4.1
0x6e9b0  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x6e9b5  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e9ba  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeUnshare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6e9bf  ldarg.1
0x6e9c0  ldstr    aCascaderollupv_0// "CascadeRollupView"
0x6e9c5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e9ca  brfalse.s loc_6E9F7
0x6e9cc  ldloc.0
0x6e9cd  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e9d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6e9d7  ldarg.1
0x6e9d8  ldstr    aCascaderollupv_0// "CascadeRollupView"
0x6e9dd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6e9e2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6e9e7  ldc.i4.1
0x6e9e8  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x6e9ed  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6e9f2  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeRollupView(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6e9f7  ldarg.0
0x6e9f8  ldarg.2
0x6e9f9  ldarg.s  6
0x6e9fb  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::GetRelationshipReferencingAttributeId(valuetype [mscorlib]System.Guid entityRelationshipId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6ea00  stloc.1
0x6ea01  ldloc.1
0x6ea02  ldarg.s  6
0x6ea04  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x6ea09  ldloca.s 2
0x6ea0b  ldloca.s 3
0x6ea0d  call     void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::GetExistingAttributeDisplayInformation(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection&, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection&)
0x6ea12  ldarg.1
0x6ea13  ldstr    aRelationshipde// "RelationshipDescription"
0x6ea18  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6ea1d  brfalse  loc_6EAA5
0x6ea22  ldarg.1
0x6ea23  ldstr    aRelationshipde// "RelationshipDescription"
0x6ea28  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6ea2d  ldstr    aDescriptionsDe// "Descriptions/Description"
0x6ea32  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x6ea37  stloc.s  8
0x6ea39  ldloc.0
0x6ea3a  ldloc.s  8
0x6ea3c  ldstr    aDescriptions// "Descriptions"
0x6ea41  ldstr    aDescription_0// "Description"
0x6ea46  ldarg.s  6
0x6ea48  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor(class [System.Xml]System.Xml.XmlNodeList, string, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6ea4d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_Description(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x6ea52  ldloc.0
0x6ea53  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::get_Description()
0x6ea58  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::get_Count()
0x6ea5d  ldc.i4.0
0x6ea5e  ble.s    loc_6EA97
0x6ea60  ldloc.0
0x6ea61  ldarg.s  5
0x6ea63  ldloc.3
0x6ea64  ldloc.0
0x6ea65  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::get_Description()
0x6ea6a  ldloc.0
0x6ea6b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::get_Description()
0x6ea70  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::get_ActualLabels()
0x6ea75  ldc.i4.0
0x6ea76  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label>::get_Item(!!T0)
0x6ea7b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_LabelDescription()
0x6ea80  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription::get_ObjectId()
0x6ea85  ldstr    aDescription_0// "Description"
0x6ea8a  ldc.i4.1
0x6ea8b  ldarg.s  6
0x6ea8d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocLabelHelper::MergeLabels(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, valuetype [mscorlib]System.Guid, string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6ea92  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_Description(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x6ea97  leave.s  loc_6EAA5
0x6ea99  ldloc.s  8
0x6ea9b  brfalse.s loc_6EAA4
0x6ea9d  ldloc.s  8
0x6ea9f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6eaa4  endfinally
0x6eaa5  ldarg.1
0x6eaa6  ldstr    aIsvalidforadva// "IsValidForAdvancedFind"
0x6eaab  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6eab0  brfalse.s loc_6EAD8
0x6eab2  ldloc.0
0x6eab3  ldarg.1
0x6eab4  ldstr    aIsvalidforadva// "IsValidForAdvancedFind"
0x6eab9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6eabe  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6eac3  ldstr    a1// "1"
0x6eac8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6eacd  brtrue.s loc_6EAD2
0x6eacf  ldc.i4.0
0x6ead0  br.s     loc_6EAD3
0x6ead2  ldc.i4.1
0x6ead3  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_RelationshipValidForAdvancedFind(bool)
0x6ead8  ldarg.1
0x6ead9  ldstr    aReferencingent// "ReferencingEntityName"
0x6eade  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6eae3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6eae8  stloc.s  4
0x6eaea  ldarg.1
0x6eaeb  ldstr    aReferencedenti_2// "ReferencedEntityName"
0x6eaf0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6eaf5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6eafa  ldloc.s  4
0x6eafc  ldc.i4.5
0x6eafd  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6eb02  ldc.i4.0
0x6eb03  ceq
0x6eb05  stloc.s  5
0x6eb07  ldloc.s  5
0x6eb09  brfalse  loc_6EBAA
0x6eb0e  ldarg.1
0x6eb0f  ldstr    aIshierarchical_0// "IsHierarchical"
0x6eb14  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6eb19  brfalse  loc_6EBAA
0x6eb1e  ldloc.0
0x6eb1f  ldarg.1
0x6eb20  call     bool Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::IsHierarchical(class [System.Xml]System.Xml.XmlNode entityRelationshipNode)
0x6eb25  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x6eb2a  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_IsHierarchical(valuetype [mscorlib]System.Nullable`1<bool>)
0x6eb2f  ldloc.0
0x6eb30  ldc.i4.1
0x6eb31  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_UpdateEntityRelationship(bool)
0x6eb36  ldloc.s  4
0x6eb38  ldarg.3
0x6eb39  ldarg.s  6
0x6eb3b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::GetExistingHierarchicalEntityRelationship(string entityName, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper importHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6eb40  stloc.s  9
0x6eb42  ldloc.s  9
0x6eb44  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6eb49  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6eb4e  brfalse.s loc_6EB71
0x6eb50  ldloc.s  9
0x6eb52  ldarg.2
0x6eb53  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6eb58  brfalse.s loc_6EB71
0x6eb5a  ldc.i4.0
0x6eb5b  stloc.s  0xC
0x6eb5d  ldloca.s 0xC
0x6eb5f  ldloc.0
0x6eb60  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::get_IsHierarchical()
0x6eb65  box      valuetype [mscorlib]System.Nullable`1<bool>
0x6eb6a  call     instance bool [mscorlib]System.Boolean::Equals(object)
0x6eb6f  br.s     loc_6EB72
0x6eb71  ldc.i4.0
0x6eb72  stloc.s  0xA
0x6eb74  ldc.i4.1
0x6eb75  stloc.s  0xC
0x6eb77  ldloca.s 0xC
0x6eb79  ldloc.0
0x6eb7a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::get_IsHierarchical()
0x6eb7f  box      valuetype [mscorlib]System.Nullable`1<bool>
0x6eb84  call     instance bool [mscorlib]System.Boolean::Equals(object)
0x6eb89  brfalse.s loc_6EB95
0x6eb8b  ldloc.s  9
0x6eb8d  ldarg.2
0x6eb8e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6eb93  br.s     loc_6EB96
0x6eb95  ldc.i4.0
0x6eb96  stloc.s  0xB
0x6eb98  ldloc.s  0xA
0x6eb9a  ldloc.s  0xB
0x6eb9c  or
0x6eb9d  brfalse.s loc_6EBAA
0x6eb9f  ldarg.s  4
0x6eba1  ldloc.s  4
0x6eba3  ldloc.s  0xA
0x6eba5  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.IHierarchyChangesSet::Add(string entityName, bool isRemoval)
0x6ebaa  ldarg.1
0x6ebab  ldstr    aField_0// "field"
0x6ebb0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6ebb5  stloc.s  6
0x6ebb7  ldloc.s  6
0x6ebb9  brfalse  loc_6EF84
0x6ebbe  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x6ebc3  ldloc.1
0x6ebc4  ldstr    aAttribute// "Attribute"
0x6ebc9  ldc.i4.8
0x6ebca  newarr   [mscorlib]System.String
0x6ebcf  dup
0x6ebd0  ldc.i4.0
0x6ebd1  ldstr    aLinkedattribut// "linkedattributeid"
0x6ebd6  stelem.ref
0x6ebd7  dup
0x6ebd8  ldc.i4.1
0x6ebd9  ldstr    aDisplaymask_0// "displaymask"
0x6ebde  stelem.ref
0x6ebdf  dup
0x6ebe0  ldc.i4.2
0x6ebe1  ldstr    aIssecured_0// "issecured"
0x6ebe6  stelem.ref
0x6ebe7  dup
0x6ebe8  ldc.i4.3
0x6ebe9  ldstr    aIsauditenabled_0// "isauditenabled"
0x6ebee  stelem.ref
0x6ebef  dup
0x6ebf0  ldc.i4.4
0x6ebf1  ldstr    aIscustomizable// "iscustomizable"
0x6ebf6  stelem.ref
0x6ebf7  dup
0x6ebf8  ldc.i4.5
0x6ebf9  ldstr    aIsrenameable_0// "isrenameable"
0x6ebfe  stelem.ref
0x6ebff  dup
0x6ec00  ldc.i4.6
0x6ec01  ldstr    aCanmodifysearc_0// "canmodifysearchsettings"
0x6ec06  stelem.ref
0x6ec07  dup
0x6ec08  ldc.i4.7
0x6ec09  ldstr    aCanmodifyrequi_0// "canmodifyrequirementlevelsettings"
0x6ec0e  stelem.ref
0x6ec0f  ldarg.s  6
  ... truncated ...
```
