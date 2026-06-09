# Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::GetOptionSet

- ea: `0x39f70`
- end: `0x3a232`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::GetOptionSet`
- size: `706`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x30230`
- `0x701c0`

## callees

- `0x39230`
- `0x39770`
- `0x39940`
- `0x39cd0`
- `0x39d50`
- `0x39f70`
- `0x3a240`
- `0x3a270`
- `0x96590`
- `0x965b0`

## string_xrefs

- `0x3a135`: `attributeOptionValueXmlAttribute`
- `0x3a13e`: `attributeStateValueXmlAttribute`
- `0x3a147`: `attributeStatusValueXmlAttribute`
- `0x39feb`: `optionSetXmlAttributes`

## pseudocode

```c

```

## disassembly

```asm
0x39f70  ldc.i4.0
0x39f71  stloc.0
0x39f72  ldarg.1
0x39f73  ldstr    aOptionset_0// "optionset"
0x39f78  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x39f7d  stloc.1
0x39f7e  ldarg.3
0x39f7f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IOptionSetDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_OptionSetDescription()
0x39f84  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag
0x39f89  stloc.2
0x39f8a  ldloc.2
0x39f8b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_SolutionId()
0x39f90  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x39f95  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x39f9a  stloc.0
0x39f9b  ldloc.2
0x39f9c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x39fa1  stloc.3
0x39fa2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType, valuetype NodeNames> Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_nodeNames
0x39fa7  ldloc.3
0x39fa8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType, valuetype NodeNames>::get_Item(void)
0x39fad  stloc.s  9
0x39faf  ldloca.s 9
0x39fb1  call     instance string NodeNames::get_SingularName()
0x39fb6  stloc.s  4
0x39fb8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType, valuetype NodeNames> Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_nodeNames
0x39fbd  ldloc.3
0x39fbe  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType, valuetype NodeNames>::get_Item(void)
0x39fc3  stloc.s  9
0x39fc5  ldloca.s 9
0x39fc7  call     instance string NodeNames::get_PluralName()
0x39fcc  stloc.s  5
0x39fce  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType, string> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetTypes::get_OptionSetNamesByType()
0x39fd3  ldloc.3
0x39fd4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType, string>::get_Item(void)
0x39fd9  stloc.s  6
0x39fdb  ldarg.0
0x39fdc  ldarg.1
0x39fdd  ldloc.1
0x39fde  ldstr    aOptionsettype// "OptionSetType"
0x39fe3  ldloc.s  6
0x39fe5  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x39fea  ldarg.0
0x39feb  ldstr    aOptionsetxmlat// "optionSetXmlAttributes"
0x39ff0  ldarg.1
0x39ff1  ldloc.1
0x39ff2  ldloc.2
0x39ff3  ldarg.s  6
0x39ff5  ldarg.s  7
0x39ff7  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeMetadataBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataDescriptionPropertyBag pb, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MetadataDifferenceCache mdc, class [mscorlib]System.Version exportAsVersion)
0x39ffc  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributes(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x3a001  ldarg.0
0x3a002  ldstr    aOptionset_1// "optionSet"
0x3a007  ldarg.1
0x3a008  ldloc.1
0x3a009  ldloc.2
0x3a00a  ldarg.s  6
0x3a00c  ldarg.s  7
0x3a00e  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeMetadataBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataDescriptionPropertyBag pb, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MetadataDifferenceCache mdc, class [mscorlib]System.Version exportAsVersion)
0x3a013  ldloc.2
0x3a014  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_IsManaged()
0x3a019  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x3a01e  ldarg.3
0x3a01f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_ParentOptionSet()
0x3a024  brfalse.s loc_3A063
0x3a026  ldarg.3
0x3a027  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_IsGlobal()
0x3a02c  brfalse.s loc_3A063
0x3a02e  ldloc.0
0x3a02f  ldarg.3
0x3a030  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_ParentOptionSet()
0x3a035  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IOptionSetDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_OptionSetDescription()
0x3a03a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IOptionSetDescription::get_SolutionId()
0x3a03f  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x3a044  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3a049  or
0x3a04a  stloc.0
0x3a04b  ldarg.0
0x3a04c  ldarg.1
0x3a04d  ldloc.1
0x3a04e  ldstr    aParentoptionse// "ParentOptionSetName"
0x3a053  ldarg.3
0x3a054  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_ParentOptionSet()
0x3a059  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Name()
0x3a05e  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x3a063  ldloc.0
0x3a064  ldarg.0
0x3a065  ldarg.1
0x3a066  ldloc.1
0x3a067  ldarg.3
0x3a068  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_DisplayNames()
0x3a06d  ldarg.s  4
0x3a06f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabelCollection(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a074  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection
0x3a079  ldstr    aDisplayname// "displayname"
0x3a07e  ldstr    aDisplaynames// "displaynames"
0x3a083  ldc.i4.1
0x3a084  ldnull
0x3a085  ldnull
0x3a086  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x3a08b  or
0x3a08c  stloc.0
0x3a08d  ldloc.0
0x3a08e  ldarg.0
0x3a08f  ldarg.1
0x3a090  ldloc.1
0x3a091  ldarg.3
0x3a092  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Descriptions()
0x3a097  ldarg.s  4
0x3a099  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabelCollection(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a09e  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection
0x3a0a3  ldstr    aDescription_0// "Description"
0x3a0a8  ldstr    aDescriptions// "Descriptions"
0x3a0ad  ldc.i4.1
0x3a0ae  ldnull
0x3a0af  ldnull
0x3a0b0  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x3a0b5  or
0x3a0b6  stloc.0
0x3a0b7  ldarg.1
0x3a0b8  ldloc.s  5
0x3a0ba  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3a0bf  stloc.s  7
0x3a0c1  ldloc.1
0x3a0c2  ldloc.s  7
0x3a0c4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3a0c9  pop
0x3a0ca  ldsfld   string [mscorlib]System.String::Empty
0x3a0cf  stloc.s  8
0x3a0d1  ldarg.3
0x3a0d2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Options()
0x3a0d7  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Values()
0x3a0dc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::GetEnumerator()
0x3a0e1  stloc.s  0xA
0x3a0e3  br       loc_3A1FE
0x3a0e8  ldloc.s  0xA
0x3a0ea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Current()
0x3a0ef  stloc.s  0xB
0x3a0f1  ldarg.1
0x3a0f2  ldloc.s  4
0x3a0f4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3a0f9  stloc.s  0xC
0x3a0fb  ldloc.s  0xB
0x3a0fd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributePicklistValueDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_PicklistValueDescription()
0x3a102  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag
0x3a107  stloc.s  0xD
0x3a109  ldloc.0
0x3a10a  ldloc.s  0xD
0x3a10c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_SolutionId()
0x3a111  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x3a116  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3a11b  or
0x3a11c  stloc.0
0x3a11d  ldloc.3
0x3a11e  switch   loc_3A135, loc_3A13E, loc_3A147, loc_3A135
0x3a133  br.s     loc_3A14E
0x3a135  ldstr    aAttributeoptio// "attributeOptionValueXmlAttribute"
0x3a13a  stloc.s  8
0x3a13c  br.s     loc_3A14E
0x3a13e  ldstr    aAttributestate// "attributeStateValueXmlAttribute"
0x3a143  stloc.s  8
0x3a145  br.s     loc_3A14E
0x3a147  ldstr    aAttributestatu// "attributeStatusValueXmlAttribute"
0x3a14c  stloc.s  8
0x3a14e  ldarg.0
0x3a14f  ldloc.s  8
0x3a151  ldarg.1
0x3a152  ldloc.s  0xC
0x3a154  ldloc.s  0xD
0x3a156  ldarg.s  6
0x3a158  ldarg.s  7
0x3a15a  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeMetadataBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataDescriptionPropertyBag pb, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MetadataDifferenceCache mdc, class [mscorlib]System.Version exportAsVersion)
0x3a15f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributes(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x3a164  ldloc.0
0x3a165  ldarg.0
0x3a166  ldarg.1
0x3a167  ldloc.s  0xC
0x3a169  ldloc.s  0xB
0x3a16b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x3a170  ldarg.s  4
0x3a172  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabelCollection(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a177  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection
0x3a17c  ldstr    aLabel// "label"
0x3a181  ldstr    aLabels// "labels"
0x3a186  ldc.i4.1
0x3a187  ldnull
0x3a188  ldnull
0x3a189  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x3a18e  or
0x3a18f  stloc.0
0x3a190  ldloc.0
0x3a191  ldarg.0
0x3a192  ldarg.1
0x3a193  ldloc.s  0xC
0x3a195  ldloc.s  0xB
0x3a197  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Descriptions()
0x3a19c  ldarg.s  4
0x3a19e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabelCollection(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a1a3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection
0x3a1a8  ldstr    aDescription_0// "Description"
0x3a1ad  ldstr    aDescriptions// "Descriptions"
0x3a1b2  ldc.i4.1
0x3a1b3  ldnull
0x3a1b4  ldnull
0x3a1b5  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x3a1ba  or
0x3a1bb  stloc.0
0x3a1bc  ldloc.0
0x3a1bd  ldarg.0
0x3a1be  ldarg.1
0x3a1bf  ldloc.s  0xC
0x3a1c1  ldloc.s  0xB
0x3a1c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Colors()
0x3a1c8  ldarg.s  4
0x3a1ca  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabelCollection(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a1cf  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection
0x3a1d4  ldstr    aColor// "Color"
0x3a1d9  ldstr    aColors// "Colors"
0x3a1de  ldc.i4.1
0x3a1df  ldnull
0x3a1e0  ldnull
0x3a1e1  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x3a1e6  or
0x3a1e7  stloc.0
0x3a1e8  ldarg.0
0x3a1e9  ldloc.s  0xD
0x3a1eb  ldarg.s  6
0x3a1ed  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ShouldOptionBeAdded(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag picklistInfo, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MetadataDifferenceCache mdc)
0x3a1f2  brfalse.s loc_3A1FE
0x3a1f4  ldloc.s  7
0x3a1f6  ldloc.s  0xC
0x3a1f8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3a1fd  pop
0x3a1fe  ldloc.s  0xA
0x3a200  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3a205  brtrue   loc_3A0E8
0x3a20a  leave.s  loc_3A218
0x3a20c  ldloc.s  0xA
0x3a20e  brfalse.s loc_3A217
0x3a210  ldloc.s  0xA
0x3a212  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3a217  endfinally
0x3a218  ldarg.s  5
0x3a21a  brfalse.s loc_3A228
0x3a21c  ldarg.0
0x3a21d  ldarg.1
0x3a21e  ldloc.1
0x3a21f  ldarg.3
0x3a220  ldarg.s  4
0x3a222  ldloc.0
0x3a223  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddGlobalInformation(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode optionSetNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata optionSetMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool hasChanged)
0x3a228  ldarg.2
0x3a229  ldloc.1
0x3a22a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3a22f  pop
0x3a230  ldloc.0
0x3a231  ret
```
