# Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::SetUpdateEntityInfoFromNode

- ea: `0x443d0`
- end: `0x444ed`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::SetUpdateEntityInfoFromNode`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x427e0`

## callees

- `0x443d0`
- `0x51610`

## string_xrefs

- `0x44425`: `AvailableForCreate`
- `0x44433`: `AvailableForCreate`
- `0x4444d`: `AvailableForDelete`
- `0x4445b`: `AvailableForDelete`
- `0x44475`: `AvailableForUpdate`
- `0x44483`: `AvailableForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x443d0  ldarg.0
0x443d1  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x443d6  ldarg.2
0x443d7  ldarg.0
0x443d8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_context
0x443dd  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::FillEntityUpdateInfoParameter(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo updateInfo, class [System.Xml]System.Xml.XmlNode entityNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x443e2  ldarg.0
0x443e3  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportEntityAttributeHandlerBase::_isInternalSolution
0x443e8  brfalse  loc_444EC
0x443ed  ldarg.2
0x443ee  ldstr    aOwnershiptypem// "OwnershipTypeMask"
0x443f3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x443f8  brfalse.s loc_44424
0x443fa  ldarg.1
0x443fb  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x44400  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x44405  ldarg.2
0x44406  ldstr    aOwnershiptypem// "OwnershipTypeMask"
0x4440b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x44410  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x44415  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x4441a  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x4441f  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_OwnershipTypeMask(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes)
0x44424  ldarg.2
0x44425  ldstr    aAvailableforcr// "AvailableForCreate"
0x4442a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4442f  brfalse.s loc_4444C
0x44431  ldarg.1
0x44432  ldarg.2
0x44433  ldstr    aAvailableforcr// "AvailableForCreate"
0x44438  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4443d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x44442  call     int32 [mscorlib]System.Int32::Parse(string)
0x44447  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_AvailableForCreate(int32)
0x4444c  ldarg.2
0x4444d  ldstr    aAvailableforde// "AvailableForDelete"
0x44452  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x44457  brfalse.s loc_44474
0x44459  ldarg.1
0x4445a  ldarg.2
0x4445b  ldstr    aAvailableforde// "AvailableForDelete"
0x44460  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x44465  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4446a  call     int32 [mscorlib]System.Int32::Parse(string)
0x4446f  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_AvailableForDelete(int32)
0x44474  ldarg.2
0x44475  ldstr    aAvailableforup// "AvailableForUpdate"
0x4447a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4447f  brfalse.s loc_4449C
0x44481  ldarg.1
0x44482  ldarg.2
0x44483  ldstr    aAvailableforup// "AvailableForUpdate"
0x44488  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4448d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x44492  call     int32 [mscorlib]System.Int32::Parse(string)
0x44497  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_AvailableForUpdate(int32)
0x4449c  ldarg.2
0x4449d  ldstr    aAvailableforre// "AvailableForRetrieve"
0x444a2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x444a7  brfalse.s loc_444C4
0x444a9  ldarg.1
0x444aa  ldarg.2
0x444ab  ldstr    aAvailableforre// "AvailableForRetrieve"
0x444b0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x444b5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x444ba  call     int32 [mscorlib]System.Int32::Parse(string)
0x444bf  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_AvailableForRetrieve(int32)
0x444c4  ldarg.2
0x444c5  ldstr    aIsaudited// "IsAudited"
0x444ca  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x444cf  brfalse.s loc_444EC
0x444d1  ldarg.1
0x444d2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x444d7  ldarg.2
0x444d8  ldstr    aIsaudited// "IsAudited"
0x444dd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x444e2  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode)
0x444e7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_IsAudited(bool)
0x444ec  ret
```
