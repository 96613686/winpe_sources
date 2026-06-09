# Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::CreateNewEntityRelationship

- ea: `0x6da90`
- end: `0x6e660`
- name: `Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::CreateNewEntityRelationship`
- size: `3024`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x31520`
- `0x31580`
- `0x317b0`
- `0x31b30`
- `0x6da90`
- `0x6e660`
- `0x6e690`
- `0x6e6c0`
- `0x6e800`
- `0x6e820`
- `0x6f2d0`

## string_xrefs

- `0x6e099`: `IsRenameable`
- `0x6dc84`: `CascadeDelete`
- `0x6dc97`: `CascadeDelete`
- `0x6df54`: `requiredlevel cannot be null in field XML for entity relationship {0}.`
- `0x6e545`: `ShouldSkipChildAttributeCreate`
- `0x6e553`: `ShouldSkipChildAttributeCreate`
- `0x6e59b`: `DoNotUpdateAttribute`
- `0x6e5a9`: `DoNotUpdateAttribute`
- `0x6e5d1`: `Import_BEGIN_{0}.ImportItem: RelationshipService.Create`
- `0x6e5fd`: `Import_END_{0}.ImportItem: RelationshipService.Create`

## pseudocode

```c

```

## disassembly

```asm
0x6da90  ldarg.1
0x6da91  ldstr    aEntityrelation_22// "entityRelationshipNode"
0x6da96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6da9b  ldarg.2
0x6da9c  ldstr    aImporthelper// "importHelper"
0x6daa1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6daa6  ldarg.3
0x6daa7  ldstr    aAffectedhierar// "affectedHierarchies"
0x6daac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6dab1  ldarg.s  4
0x6dab3  ldstr    aLoclabelhelper// "locLabelHelper"
0x6dab8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6dabd  ldarg.s  5
0x6dabf  ldstr    aContext// "context"
0x6dac4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6dac9  ldarg.s  6
0x6dacb  ldstr    aMetadatahelper// "metadataHelper"
0x6dad0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6dad5  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::.ctor()
0x6dada  stloc.0
0x6dadb  ldarg.1
0x6dadc  ldstr    aRelationshipde// "RelationshipDescription"
0x6dae1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dae6  brtrue.s loc_6DB03
0x6dae8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6daed  ldstr    aRelationshipde_0// "RelationshipDescription cannot be null "...
0x6daf2  ldc.i4.0
0x6daf3  newarr   [mscorlib]System.Object
0x6daf8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6dafd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x6db02  throw
0x6db03  ldarg.1
0x6db04  ldstr    aRelationshipde// "RelationshipDescription"
0x6db09  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6db0e  ldstr    aDescriptionsDe// "Descriptions/Description"
0x6db13  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x6db18  stloc.s  7
0x6db1a  ldloc.0
0x6db1b  ldloc.s  7
0x6db1d  ldstr    aDescriptions// "Descriptions"
0x6db22  ldstr    aDescription_0// "Description"
0x6db27  ldarg.s  5
0x6db29  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor(class [System.Xml]System.Xml.XmlNodeList, string, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6db2e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_Description(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x6db33  ldloc.0
0x6db34  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_Description()
0x6db39  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::get_Count()
0x6db3e  ldc.i4.0
0x6db3f  ble.s    loc_6DB78
0x6db41  ldloc.0
0x6db42  ldarg.s  4
0x6db44  ldnull
0x6db45  ldloc.0
0x6db46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_Description()
0x6db4b  ldloc.0
0x6db4c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_Description()
0x6db51  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::get_ActualLabels()
0x6db56  ldc.i4.0
0x6db57  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label>::get_Item(!!T0)
0x6db5c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_LabelDescription()
0x6db61  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription::get_ObjectId()
0x6db66  ldstr    aDescription_0// "Description"
0x6db6b  ldc.i4.1
0x6db6c  ldarg.s  5
0x6db6e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocLabelHelper::MergeLabels(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, valuetype [mscorlib]System.Guid, string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6db73  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_Description(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x6db78  leave.s  loc_6DB86
0x6db7a  ldloc.s  7
0x6db7c  brfalse.s loc_6DB85
0x6db7e  ldloc.s  7
0x6db80  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6db85  endfinally
0x6db86  ldarg.1
0x6db87  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6db8c  ldstr    aName_1// "Name"
0x6db91  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6db96  brtrue.s loc_6DBB3
0x6db98  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6db9d  ldstr    aSchemanameCann// "SchemaName cannot be null for entity re"...
0x6dba2  ldc.i4.0
0x6dba3  newarr   [mscorlib]System.Object
0x6dba8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6dbad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x6dbb2  throw
0x6dbb3  ldloc.0
0x6dbb4  ldarg.1
0x6dbb5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6dbba  ldstr    aName_1// "Name"
0x6dbbf  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6dbc4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6dbc9  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_SchemaName(string)
0x6dbce  ldarg.1
0x6dbcf  ldstr    aReferencedenti_2// "ReferencedEntityName"
0x6dbd4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dbd9  brtrue.s loc_6DBFF
0x6dbdb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6dbe0  ldstr    aReferencedenti_4// "ReferencedEntityName cannot be null for"...
0x6dbe5  ldc.i4.1
0x6dbe6  newarr   [mscorlib]System.Object
0x6dbeb  dup
0x6dbec  ldc.i4.0
0x6dbed  ldloc.0
0x6dbee  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x6dbf3  stelem.ref
0x6dbf4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6dbf9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x6dbfe  throw
0x6dbff  ldloc.0
0x6dc00  ldarg.1
0x6dc01  ldstr    aReferencedenti_2// "ReferencedEntityName"
0x6dc06  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dc0b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6dc10  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_PrimaryEntityName(string)
0x6dc15  ldarg.1
0x6dc16  ldstr    aReferencingent// "ReferencingEntityName"
0x6dc1b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dc20  brtrue.s loc_6DC46
0x6dc22  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6dc27  ldstr    aReferencingent_1// "ReferencingEntityName cannot be null fo"...
0x6dc2c  ldc.i4.1
0x6dc2d  newarr   [mscorlib]System.Object
0x6dc32  dup
0x6dc33  ldc.i4.0
0x6dc34  ldloc.0
0x6dc35  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x6dc3a  stelem.ref
0x6dc3b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6dc40  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x6dc45  throw
0x6dc46  ldloc.0
0x6dc47  ldarg.1
0x6dc48  ldstr    aReferencingent// "ReferencingEntityName"
0x6dc4d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dc52  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6dc57  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelatedEntityName(string)
0x6dc5c  ldloc.0
0x6dc5d  ldarg.1
0x6dc5e  ldstr    aCascadeassign_0// "CascadeAssign"
0x6dc63  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::GetCascadeLinkType(class [System.Xml]System.Xml.XmlNode entityRelationshipNode, string cascadeType)
0x6dc68  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeAssign(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6dc6d  ldarg.s  5
0x6dc6f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x6dc74  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x6dc79  ldarg.s  5
0x6dc7b  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInternalSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6dc80  brfalse.s loc_6DC95
0x6dc82  ldloc.0
0x6dc83  ldarg.1
0x6dc84  ldstr    aCascadedelete_0// "CascadeDelete"
0x6dc89  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::GetCascadeDeleteLinkType(class [System.Xml]System.Xml.XmlNode entityRelationshipNode, string cascadeType)
0x6dc8e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6dc93  br.s     loc_6DCA6
0x6dc95  ldloc.0
0x6dc96  ldarg.1
0x6dc97  ldstr    aCascadedelete_0// "CascadeDelete"
0x6dc9c  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::GetCascadeLinkType(class [System.Xml]System.Xml.XmlNode entityRelationshipNode, string cascadeType)
0x6dca1  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6dca6  ldloc.0
0x6dca7  ldarg.1
0x6dca8  ldstr    aCascademerge_0// "CascadeMerge"
0x6dcad  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::GetCascadeLinkType(class [System.Xml]System.Xml.XmlNode entityRelationshipNode, string cascadeType)
0x6dcb2  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeMerge(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6dcb7  ldloc.0
0x6dcb8  ldarg.1
0x6dcb9  ldstr    aCascadereparen_0// "CascadeReparent"
0x6dcbe  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::GetCascadeLinkType(class [System.Xml]System.Xml.XmlNode entityRelationshipNode, string cascadeType)
0x6dcc3  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeReparent(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6dcc8  ldloc.0
0x6dcc9  ldarg.1
0x6dcca  ldstr    aCascadeshare_0// "CascadeShare"
0x6dccf  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::GetCascadeLinkType(class [System.Xml]System.Xml.XmlNode entityRelationshipNode, string cascadeType)
0x6dcd4  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeShare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6dcd9  ldloc.0
0x6dcda  ldarg.1
0x6dcdb  ldstr    aCascadeunshare_0// "CascadeUnshare"
0x6dce0  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::GetCascadeLinkType(class [System.Xml]System.Xml.XmlNode entityRelationshipNode, string cascadeType)
0x6dce5  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeUnshare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6dcea  ldarg.1
0x6dceb  ldstr    aCascaderollupv_0// "CascadeRollupView"
0x6dcf0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dcf5  brfalse.s loc_6DD22
0x6dcf7  ldloc.0
0x6dcf8  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6dcfd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6dd02  ldarg.1
0x6dd03  ldstr    aCascaderollupv_0// "CascadeRollupView"
0x6dd08  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dd0d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6dd12  ldc.i4.1
0x6dd13  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x6dd18  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x6dd1d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeRollupView(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0x6dd22  ldarg.1
0x6dd23  ldstr    aReferencingatt_0// "ReferencingAttributeName"
0x6dd28  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dd2d  brtrue.s loc_6DD53
0x6dd2f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6dd34  ldstr    aReferencingatt_1// "ReferencingAttributeName cannot be null"...
0x6dd39  ldc.i4.1
0x6dd3a  newarr   [mscorlib]System.Object
0x6dd3f  dup
0x6dd40  ldc.i4.0
0x6dd41  ldloc.0
0x6dd42  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x6dd47  stelem.ref
0x6dd48  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6dd4d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x6dd52  throw
0x6dd53  ldloc.0
0x6dd54  ldarg.1
0x6dd55  ldstr    aReferencingatt_0// "ReferencingAttributeName"
0x6dd5a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dd5f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6dd64  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeName(string)
0x6dd69  ldarg.1
0x6dd6a  ldstr    aReferencedattr// "ReferencedAttributeName"
0x6dd6f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dd74  brfalse.s loc_6DD8C
0x6dd76  ldloc.0
0x6dd77  ldarg.1
0x6dd78  ldstr    aReferencedattr// "ReferencedAttributeName"
0x6dd7d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dd82  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6dd87  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_ReferencedAttributeName(string)
0x6dd8c  ldarg.1
0x6dd8d  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x6dd92  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6dd97  stloc.1
0x6dd98  ldloc.1
0x6dd99  brfalse.s loc_6DDAC
0x6dd9b  ldloc.0
0x6dd9c  ldloc.1
0x6dd9d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6dda2  call     class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToVersionFromString(string)
0x6dda7  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IntroducedVersion(class [mscorlib]System.Version)
0x6ddac  ldarg.1
0x6ddad  ldstr    aIsvalidforadva// "IsValidForAdvancedFind"
0x6ddb2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6ddb7  brfalse.s loc_6DDDF
0x6ddb9  ldloc.0
0x6ddba  ldarg.1
0x6ddbb  ldstr    aIsvalidforadva// "IsValidForAdvancedFind"
0x6ddc0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6ddc5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6ddca  ldstr    a1// "1"
0x6ddcf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6ddd4  brtrue.s loc_6DDD9
0x6ddd6  ldc.i4.0
0x6ddd7  br.s     loc_6DDDA
0x6ddd9  ldc.i4.1
0x6ddda  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipValidForAdvancedFind(bool)
0x6dddf  ldloc.0
0x6dde0  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_PrimaryEntityName()
0x6dde5  ldloc.0
0x6dde6  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelatedEntityName()
0x6ddeb  ldc.i4.5
0x6ddec  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6ddf1  ldc.i4.0
0x6ddf2  ceq
0x6ddf4  stloc.2
0x6ddf5  ldloc.2
0x6ddf6  brfalse.s loc_6DE19
0x6ddf8  ldloc.0
0x6ddf9  ldarg.1
0x6ddfa  call     bool Microsoft.Crm.Tools.ImportExportPublish.OneToManyEntityRelationshipProcessor::IsHierarchical(class [System.Xml]System.Xml.XmlNode entityRelationshipNode)
0x6ddff  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IsHierarchical(bool)
0x6de04  ldloc.0
0x6de05  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_IsHierarchical()
0x6de0a  brfalse.s loc_6DE19
0x6de0c  ldarg.3
0x6de0d  ldloc.0
0x6de0e  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_PrimaryEntityName()
0x6de13  ldc.i4.0
0x6de14  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.IHierarchyChangesSet::Add(string entityName, bool isRemoval)
0x6de19  ldloc.0
0x6de1a  ldarg.1
0x6de1b  ldstr    aIscustomizable_0// "IsCustomizable"
0x6de20  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6de25  brtrue.s loc_6DE2A
0x6de27  ldloc.2
0x6de28  br.s     loc_6DE4A
0x6de2a  ldloc.2
0x6de2b  brfalse.s loc_6DE49
0x6de2d  ldarg.1
0x6de2e  ldstr    aIscustomizable_0// "IsCustomizable"
0x6de33  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6de38  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6de3d  ldstr    a1// "1"
0x6de42  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6de47  br.s     loc_6DE4A
0x6de49  ldc.i4.0
0x6de4a  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CanChangeHierarchicalSettings(bool)
0x6de4f  ldarg.0
0x6de50  ldloc.0
0x6de51  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelatedEntityName()
0x6de56  ldarg.s  5
0x6de58  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x6de5d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.EntityRelationshipProcessor::GetEntityId(string entityName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x6de62  stloc.3
0x6de63  ldarg.s  5
  ... truncated ...
```
