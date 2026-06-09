# Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::SetCreateUpdateEntityInfoFromNode

- ea: `0x427e0`
- end: `0x43c45`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::SetCreateUpdateEntityInfoFromNode`
- size: `5221`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x44870`

## callees

- `0x421e0`
- `0x427e0`
- `0x43c50`
- `0x44120`
- `0x443d0`
- `0x45bc0`
- `0x45c20`
- `0x45c40`
- `0x50580`
- `0x51250`

## string_xrefs

- `0x42f48`: `isdocumentrecommendationsenabled`
- `0x431bc`: `isreadonlyinmobileclient`
- `0x433c1`: `isreadingpaneenabled`
- `0x4341d`: `isquickcreateenabled`
- `0x42957`: `Could not find entity with name: {0} in MetadataCache`
- `0x42c48`: `serviceclassname`
- `0x42c93`: `serviceassembly`
- `0x43479`: `isairupdated`

## pseudocode

```c

```

## disassembly

```asm
0x427e0  ldarg.1
0x427e1  ldstr    aEntitynode// "entityNode"
0x427e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x427eb  ldarg.1
0x427ec  ldstr    aEntityinfoEnti// "EntityInfo/entity"
0x427f1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x427f6  stloc.0
0x427f7  ldarg.2
0x427f8  ldnull
0x427f9  stind.ref
0x427fa  ldloc.0
0x427fb  brtrue.s loc_4281F
0x427fd  ldarg.0
0x427fe  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_isInternalSolution
0x42803  brfalse.s loc_42806
0x42805  ret
0x42806  ldc.i4   0x80040203
0x4280b  ldc.i4.1
0x4280c  newarr   [mscorlib]System.Object
0x42811  dup
0x42812  ldc.i4.0
0x42813  ldstr    aEntitynodeCann// "entityNode cannot be null"
0x42818  stelem.ref
0x42819  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x4281e  throw
0x4281f  ldloc.0
0x42820  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x42825  brtrue.s loc_42849
0x42827  ldarg.0
0x42828  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_isInternalSolution
0x4282d  brfalse.s loc_42830
0x4282f  ret
0x42830  ldc.i4   0x80040203
0x42835  ldc.i4.1
0x42836  newarr   [mscorlib]System.Object
0x4283b  dup
0x4283c  ldc.i4.0
0x4283d  ldstr    aEntitynodeCann_0// "entityNode cannot be empty"
0x42842  stelem.ref
0x42843  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x42848  throw
0x42849  ldarg.0
0x4284a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_context
0x4284f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42854  stloc.1
0x42855  ldloc.1
0x42856  ldloc.0
0x42857  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::FillPropertiesFromXml(class [System.Xml]System.Xml.XmlNode)
0x4285c  ldarg.1
0x4285d  ldstr    aEntityinfoEnti_0// "EntityInfo/entity/BaseTableName"
0x42862  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x42867  brtrue.s loc_42874
0x42869  ldloc.1
0x4286a  ldstr    asc_9A18C// ""
0x4286f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_BaseTableName(string)
0x42874  ldarg.0
0x42875  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_isInternalSolution
0x4287a  brfalse.s loc_42894
0x4287c  ldloc.1
0x4287d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_ReportViewName()
0x42882  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x42887  brfalse.s loc_42894
0x42889  ldloc.1
0x4288a  ldstr    asc_9ACE8// " "
0x4288f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_ReportViewName(string)
0x42894  ldloc.0
0x42895  ldstr    aLocalizednames_1// "LocalizedNames"
0x4289a  ldstr    aLocalizedname// "LocalizedName"
0x4289f  ldloc.1
0x428a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x428a5  ldstr    aLocalizedname// "LocalizedName"
0x428aa  ldarg.0
0x428ab  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_context
0x428b0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::CreateLabels(class [System.Xml]System.Xml.XmlNode entityNode, string labelPluralName, string labelSingularName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x428b5  stloc.2
0x428b6  ldloc.0
0x428b7  ldstr    aLocalizedcolle_1// "LocalizedCollectionNames"
0x428bc  ldstr    aLocalizedcolle_0// "LocalizedCollectionName"
0x428c1  ldloc.1
0x428c2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x428c7  ldstr    aLocalizedcolle_0// "LocalizedCollectionName"
0x428cc  ldarg.0
0x428cd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_context
0x428d2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::CreateLabels(class [System.Xml]System.Xml.XmlNode entityNode, string labelPluralName, string labelSingularName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x428d7  stloc.3
0x428d8  ldloc.0
0x428d9  ldstr    aDescriptions// "Descriptions"
0x428de  ldstr    aDescription_0// "Description"
0x428e3  ldloc.1
0x428e4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x428e9  ldstr    aDescription_0// "Description"
0x428ee  ldarg.0
0x428ef  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_context
0x428f4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::CreateLabels(class [System.Xml]System.Xml.XmlNode entityNode, string labelPluralName, string labelSingularName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x428f9  stloc.s  4
0x428fb  ldarg.0
0x428fc  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_createEntity
0x42901  brfalse.s loc_42944
0x42903  ldarg.1
0x42904  ldstr    aEntityinfoEnti_1// "EntityInfo/entity/ObjectTypeCode"
0x42909  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x4290e  stloc.s  5
0x42910  ldarg.0
0x42911  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_isInternalSolution
0x42916  brfalse.s loc_42930
0x42918  ldloc.s  5
0x4291a  brfalse.s loc_42930
0x4291c  ldloc.1
0x4291d  ldloc.s  5
0x4291f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x42924  call     int32 [mscorlib]System.Int32::Parse(string)
0x42929  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_ObjectTypeCode(int32)
0x4292e  br.s     loc_42937
0x42930  ldloc.1
0x42931  ldc.i4.m1
0x42932  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_ObjectTypeCode(int32)
0x42937  ldarg.0
0x42938  ldloc.1
0x42939  ldloc.0
0x4293a  ldloc.2
0x4293b  ldloc.3
0x4293c  ldloc.s  4
0x4293e  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::SetCreateEntityInfoFromNode(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag entityInfo, class [System.Xml]System.Xml.XmlNode newentity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection localizedNames, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection localizedCollectionNames, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection descriptions)
0x42943  ret
0x42944  ldarg.0
0x42945  ldc.i4.0
0x42946  stfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityHasChanged
0x4294b  ldarg.2
0x4294c  ldarg.0
0x4294d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::TryGetEntityMetadata()
0x42952  stind.ref
0x42953  ldarg.2
0x42954  ldind.ref
0x42955  brtrue.s loc_4296D
0x42957  ldstr    aCouldNotFindEn// "Could not find entity with name: {0} in"...
0x4295c  ldarg.0
0x4295d  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_EntityName()
0x42962  call     string [mscorlib]System.String::Format(string, object)
0x42967  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4296c  throw
0x4296d  ldarg.0
0x4296e  ldarg.2
0x4296f  ldind.ref
0x42970  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x42975  ldarg.0
0x42976  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_context
0x4297b  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42980  stfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x42985  ldarg.0
0x42986  ldarg.0
0x42987  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x4298c  ldloc.0
0x4298d  ldarg.0
0x4298e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_context
0x42993  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::SetUpdateEntityInfoFromNode(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityUpdateInfo, class [System.Xml]System.Xml.XmlNode newEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x42998  ldarg.0
0x42999  ldarg.0
0x4299a  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityHasChanged
0x4299f  brtrue   loc_42AA8
0x429a4  ldarg.0
0x429a5  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x429aa  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_HasRelatedActivities()
0x429af  ldarg.2
0x429b0  ldind.ref
0x429b1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_HasActivities()
0x429b6  bne.un   loc_42AA8
0x429bb  ldarg.0
0x429bc  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x429c1  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_HasRelatedNotes()
0x429c6  ldarg.2
0x429c7  ldind.ref
0x429c8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_HasNotes()
0x429cd  bne.un   loc_42AA8
0x429d2  ldarg.0
0x429d3  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x429d8  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_HasRelatedFeedback()
0x429dd  ldarg.2
0x429de  ldind.ref
0x429df  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_HasFeedback()
0x429e4  bne.un   loc_42AA8
0x429e9  ldarg.0
0x429ea  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x429ef  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsConnectionsEnabled()
0x429f4  ldarg.2
0x429f5  ldind.ref
0x429f6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsConnectionsEnabled()
0x429fb  bne.un   loc_42AA8
0x42a00  ldarg.0
0x42a01  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x42a06  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsDuplicateCheckSupported()
0x42a0b  ldarg.2
0x42a0c  ldind.ref
0x42a0d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsDuplicateCheckSupported()
0x42a12  bne.un   loc_42AA8
0x42a17  ldarg.0
0x42a18  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x42a1d  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsMailMergeEnabled()
0x42a22  ldarg.2
0x42a23  ldind.ref
0x42a24  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsMailMergeEnabled()
0x42a29  bne.un.s loc_42AA8
0x42a2b  ldarg.0
0x42a2c  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x42a31  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsCollaboration()
0x42a36  ldarg.2
0x42a37  ldind.ref
0x42a38  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCollaboration()
0x42a3d  bne.un.s loc_42AA8
0x42a3f  ldarg.0
0x42a40  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x42a45  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_AutoRouteToOwnerQueue()
0x42a4a  ldarg.2
0x42a4b  ldind.ref
0x42a4c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AutoRouteToOwnerQueue()
0x42a51  bne.un.s loc_42AA8
0x42a53  ldarg.0
0x42a54  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x42a59  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsActivityParty()
0x42a5e  ldarg.2
0x42a5f  ldind.ref
0x42a60  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivityParty()
0x42a65  bne.un.s loc_42AA8
0x42a67  ldarg.0
0x42a68  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x42a6d  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsActivity()
0x42a72  ldarg.2
0x42a73  ldind.ref
0x42a74  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x42a79  bne.un.s loc_42AA8
0x42a7b  ldarg.0
0x42a7c  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x42a81  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsBusinessProcessEnabled()
0x42a86  ldarg.2
0x42a87  ldind.ref
0x42a88  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBusinessProcessEnabled()
0x42a8d  bne.un.s loc_42AA8
0x42a8f  ldarg.0
0x42a90  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x42a95  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMasks [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityMask()
0x42a9a  ldarg.2
0x42a9b  ldind.ref
0x42a9c  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMasks [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityMask()
0x42aa1  ceq
0x42aa3  ldc.i4.0
0x42aa4  ceq
0x42aa6  br.s     loc_42AA9
0x42aa8  ldc.i4.1
0x42aa9  stfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityHasChanged
0x42aae  ldarg.2
0x42aaf  ldind.ref
0x42ab0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x42ab5  brfalse.s loc_42AC0
0x42ab7  ldarg.2
0x42ab8  ldind.ref
0x42ab9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x42abe  br.s     loc_42AC1
0x42ac0  ldnull
0x42ac1  stloc.s  6
0x42ac3  ldarg.2
0x42ac4  ldind.ref
0x42ac5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedCollectionName()
0x42aca  brfalse.s loc_42AD5
0x42acc  ldarg.2
0x42acd  ldind.ref
0x42ace  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedCollectionName()
0x42ad3  br.s     loc_42AD6
0x42ad5  ldnull
0x42ad6  stloc.s  7
0x42ad8  ldarg.2
0x42ad9  ldind.ref
0x42ada  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Description()
0x42adf  brfalse.s loc_42AEA
0x42ae1  ldarg.2
0x42ae2  ldind.ref
0x42ae3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Description()
0x42ae8  br.s     loc_42AEB
0x42aea  ldnull
0x42aeb  stloc.s  8
0x42aed  ldarg.0
0x42aee  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocLabelHelper Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_locLabelHelper
0x42af3  ldloc.s  6
0x42af5  ldloc.2
0x42af6  ldloc.1
0x42af7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x42afc  ldstr    aLocalizedname// "LocalizedName"
0x42b01  ldc.i4.0
0x42b02  ldarg.0
0x42b03  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_context
0x42b08  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocLabelHelper::MergeLabels(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, valuetype [mscorlib]System.Guid, string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x42b0d  stloc.2
0x42b0e  ldarg.0
0x42b0f  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocLabelHelper Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_locLabelHelper
0x42b14  ldloc.s  7
0x42b16  ldloc.3
0x42b17  ldloc.1
0x42b18  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x42b1d  ldstr    aLocalizedcolle_0// "LocalizedCollectionName"
0x42b22  ldc.i4.0
0x42b23  ldarg.0
0x42b24  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_context
  ... truncated ...
```
