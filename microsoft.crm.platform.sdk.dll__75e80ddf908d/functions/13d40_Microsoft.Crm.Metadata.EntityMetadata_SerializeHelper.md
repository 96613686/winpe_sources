# Microsoft.Crm.Metadata.EntityMetadata::SerializeHelper

- ea: `0x13d40`
- end: `0x14b9f`
- name: `Microsoft.Crm.Metadata.EntityMetadata::SerializeHelper`
- size: `3679`
- prototype: ``
- caller_count: `2`
- callee_count: `136`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x13cf0`
- `0x14ba0`

## callees

- `0xbb70`
- `0x12d10`
- `0x12d20`
- `0x12d30`
- `0x12d40`
- `0x12d50`
- `0x12d60`
- `0x12d70`
- `0x12d80`
- `0x12db0`
- `0x12dc0`
- `0x12df0`
- `0x12e00`
- `0x12e10`
- `0x12e20`
- `0x12e30`
- `0x12e40`
- `0x12e50`
- `0x12e60`
- `0x12e70`
- `0x12e80`
- `0x12e90`
- `0x12ea0`
- `0x12eb0`
- `0x12ee0`
- `0x12ef0`
- `0x12f00`
- `0x12f10`
- `0x12f20`
- `0x12f30`
- `0x12f40`
- `0x12f50`
- `0x12f60`
- `0x12fa0`
- `0x12fb0`
- `0x12fc0`
- `0x12fd0`
- `0x12fe0`
- `0x12ff0`
- `0x13000`
- `0x13010`
- `0x13020`
- `0x13030`
- `0x13040`
- `0x13050`
- `0x13060`
- `0x13070`
- `0x13080`
- `0x13090`
- `0x130a0`

## string_xrefs

- `0x143b3`: `IsRenameable`
- `0x13edb`: `IsSecurityIntersect`
- `0x1412a`: `MobileAccessLevelMask`
- `0x14182`: `IsReadOnlyInMobileClient`
- `0x142c1`: `IsAIRUpdated`
- `0x14369`: `ExtensionTableName`
- `0x143fb`: `IsMergeEnabledSolutionComponent`
- `0x144ed`: `ServiceClassName`
- `0x14506`: `ServiceAssembly`
- `0x14580`: `CanModifyMobileClientReadOnly`
- `0x145e0`: `IsReadingPaneEnabled`
- `0x145f8`: `IsQuickCreateEnabled`
- `0x14694`: `CanCreateAttributes`
- `0x146f4`: `CanCreateForms`
- `0x1470c`: `CanCreateCharts`
- `0x14724`: `CanCreateViews`
- `0x147a9`: `ParentComponentType`
- `0x149cc`: `IsDocumentRecommendationsEnabled`
- `0x14b3e`: `AvailableForCreate`
- `0x14b61`: `AvailableForUpdate`
- `0x14b84`: `AvailableForDelete`

## pseudocode

```c

```

## disassembly

```asm
0x13d40  ldarg.1
0x13d41  ldstr    aName// "Name"
0x13d46  ldarg.0
0x13d47  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x13d4c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x13d51  ldarg.2
0x13d52  ldc.i4.2
0x13d53  and
0x13d54  brfalse.s loc_13D75
0x13d56  ldarg.1
0x13d57  ldstr    aEntityid// "EntityId"
0x13d5c  ldarg.0
0x13d5d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x13d62  stloc.0
0x13d63  ldloca.s 0
0x13d65  constrained. [mscorlib]System.Guid
0x13d6b  callvirt instance string [mscorlib]System.Object::ToString()
0x13d70  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13d75  ldarg.0
0x13d76  call     instance int32 Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x13d7b  brfalse.s loc_13DA0
0x13d7d  ldarg.1
0x13d7e  ldstr    aObjecttypecode// "ObjectTypeCode"
0x13d83  ldarg.0
0x13d84  ldfld    class Microsoft.Crm.Metadata.IEntityDescription Microsoft.Crm.Metadata.EntityMetadata::_entityInfo
0x13d89  callvirt instance int32 Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x13d8e  stloc.1
0x13d8f  ldloca.s 1
0x13d91  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13d96  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x13d9b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13da0  ldarg.0
0x13da1  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0x13da6  ldarg.0
0x13da7  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x13dac  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x13db1  brfalse.s loc_13DC4
0x13db3  ldarg.1
0x13db4  ldstr    aPhysicalname// "PhysicalName"
0x13db9  ldarg.0
0x13dba  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0x13dbf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13dc4  ldarg.0
0x13dc5  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x13dca  ldarg.0
0x13dcb  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x13dd0  ldc.i4.5
0x13dd1  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x13dd6  brfalse.s loc_13DE9
0x13dd8  ldarg.1
0x13dd9  ldstr    aLogicalname// "LogicalName"
0x13dde  ldarg.0
0x13ddf  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x13de4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13de9  ldarg.0
0x13dea  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_ExternalName()
0x13def  brfalse.s loc_13E02
0x13df1  ldarg.1
0x13df2  ldstr    aExternalname// "ExternalName"
0x13df7  ldarg.0
0x13df8  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_ExternalName()
0x13dfd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13e02  ldarg.0
0x13e03  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_ExternalCollectionName()
0x13e08  brfalse.s loc_13E1B
0x13e0a  ldarg.1
0x13e0b  ldstr    aExternalcollec// "ExternalCollectionName"
0x13e10  ldarg.0
0x13e11  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_ExternalCollectionName()
0x13e16  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13e1b  ldarg.0
0x13e1c  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_CollectionName()
0x13e21  brfalse.s loc_13E34
0x13e23  ldarg.1
0x13e24  ldstr    aCollectionname// "CollectionName"
0x13e29  ldarg.0
0x13e2a  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_CollectionName()
0x13e2f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13e34  ldarg.0
0x13e35  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_LogicalCollectionName()
0x13e3a  brfalse.s loc_13E4D
0x13e3c  ldarg.1
0x13e3d  ldstr    aLogicalcollect// "LogicalCollectionName"
0x13e42  ldarg.0
0x13e43  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_LogicalCollectionName()
0x13e48  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13e4d  ldarg.0
0x13e4e  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_BaseTableName()
0x13e53  ldarg.0
0x13e54  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x13e59  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x13e5e  brfalse.s loc_13E71
0x13e60  ldarg.1
0x13e61  ldstr    aBasetablename// "BaseTableName"
0x13e66  ldarg.0
0x13e67  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_BaseTableName()
0x13e6c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13e71  ldarg.0
0x13e72  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityMetadata::get_InheritsFrom()
0x13e77  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13e7c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x13e81  brfalse.s loc_13EA2
0x13e83  ldarg.1
0x13e84  ldstr    aInheritsfrom// "InheritsFrom"
0x13e89  ldarg.0
0x13e8a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityMetadata::get_InheritsFrom()
0x13e8f  stloc.0
0x13e90  ldloca.s 0
0x13e92  constrained. [mscorlib]System.Guid
0x13e98  callvirt instance string [mscorlib]System.Object::ToString()
0x13e9d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13ea2  ldarg.0
0x13ea3  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsInheritedFrom()
0x13ea8  brfalse.s loc_13EBA
0x13eaa  ldarg.1
0x13eab  ldstr    aIsinheritedfro// "IsInheritedFrom"
0x13eb0  ldstr    a1_1// "1"
0x13eb5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13eba  ldarg.0
0x13ebb  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsIntersect()
0x13ec0  brfalse.s loc_13ED2
0x13ec2  ldarg.1
0x13ec3  ldstr    aIsintersect// "IsIntersect"
0x13ec8  ldstr    a1_1// "1"
0x13ecd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13ed2  ldarg.0
0x13ed3  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsSecurityIntersect()
0x13ed8  brfalse.s loc_13EEA
0x13eda  ldarg.1
0x13edb  ldstr    aIssecurityinte// "IsSecurityIntersect"
0x13ee0  ldstr    a1_1// "1"
0x13ee5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13eea  ldarg.0
0x13eeb  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsLookupTable()
0x13ef0  brfalse.s loc_13F02
0x13ef2  ldarg.1
0x13ef3  ldstr    aIslookuptable// "IsLookupTable"
0x13ef8  ldstr    a1_1// "1"
0x13efd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13f02  ldarg.0
0x13f03  call     instance int32 Microsoft.Crm.Metadata.EntityMetadata::get_EventMask()
0x13f08  brfalse.s loc_13F28
0x13f0a  ldarg.1
0x13f0b  ldstr    aEventmask// "EventMask"
0x13f10  ldarg.0
0x13f11  call     instance int32 Microsoft.Crm.Metadata.EntityMetadata::get_EventMask()
0x13f16  stloc.1
0x13f17  ldloca.s 1
0x13f19  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13f1e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x13f23  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13f28  ldarg.0
0x13f29  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsLogicalEntity()
0x13f2e  brfalse.s loc_13F40
0x13f30  ldarg.1
0x13f31  ldstr    aIslogicalentit// "IsLogicalEntity"
0x13f36  ldstr    a1_1// "1"
0x13f3b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13f40  ldarg.0
0x13f41  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizableDatabaseValue()
0x13f46  brfalse.s loc_13F58
0x13f48  ldarg.1
0x13f49  ldstr    aIscustomizable// "IsCustomizable"
0x13f4e  ldstr    a1_1// "1"
0x13f53  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13f58  ldarg.0
0x13f59  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsManaged()
0x13f5e  brtrue.s loc_13F70
0x13f60  ldarg.1
0x13f61  ldstr    aIsmanaged// "IsManaged"
0x13f66  ldstr    a0_0// "0"
0x13f6b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13f70  ldarg.0
0x13f71  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsCollaboration()
0x13f76  brfalse.s loc_13F88
0x13f78  ldarg.1
0x13f79  ldstr    aIscollaboratio// "IsCollaboration"
0x13f7e  ldstr    a1_1// "1"
0x13f83  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13f88  ldarg.0
0x13f89  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsMultipleQueueEnabled()
0x13f8e  brfalse.s loc_13FA0
0x13f90  ldarg.1
0x13f91  ldstr    aIsmultiplequeu// "IsMultipleQueueEnabled"
0x13f96  ldstr    a1_1// "1"
0x13f9b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13fa0  ldarg.0
0x13fa1  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_AutoRouteToOwnerQueue()
0x13fa6  brfalse.s loc_13FB8
0x13fa8  ldarg.1
0x13fa9  ldstr    aAutoroutetoown// "AutoRouteToOwnerQueue"
0x13fae  ldstr    a1_1// "1"
0x13fb3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13fb8  ldarg.0
0x13fb9  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsConnectionsEnabled()
0x13fbe  brfalse.s loc_13FD0
0x13fc0  ldarg.1
0x13fc1  ldstr    aIsconnectionse// "IsConnectionsEnabled"
0x13fc6  ldstr    a1_1// "1"
0x13fcb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13fd0  ldarg.0
0x13fd1  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_EntityHelpUrl()
0x13fd6  brfalse.s loc_13FE9
0x13fd8  ldarg.1
0x13fd9  ldstr    aEntityhelpurl// "EntityHelpUrl"
0x13fde  ldarg.0
0x13fdf  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_EntityHelpUrl()
0x13fe4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x13fe9  ldarg.0
0x13fea  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_EntityHelpUrlEnabled()
0x13fef  brfalse.s loc_14001
0x13ff1  ldarg.1
0x13ff2  ldstr    aEntityhelpurle// "EntityHelpUrlEnabled"
0x13ff7  ldstr    a1_1// "1"
0x13ffc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x14001  ldarg.0
0x14002  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_IconLargeName()
0x14007  brfalse.s loc_1401A
0x14009  ldarg.1
0x1400a  ldstr    aIconlargename// "IconLargeName"
0x1400f  ldarg.0
0x14010  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_IconLargeName()
0x14015  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1401a  ldarg.0
0x1401b  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_IconMediumName()
0x14020  brfalse.s loc_14033
0x14022  ldarg.1
0x14023  ldstr    aIconmediumname// "IconMediumName"
0x14028  ldarg.0
0x14029  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_IconMediumName()
0x1402e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x14033  ldarg.0
0x14034  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_IconSmallName()
0x14039  brfalse.s loc_1404C
0x1403b  ldarg.1
0x1403c  ldstr    aIconsmallname// "IconSmallName"
0x14041  ldarg.0
0x14042  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_IconSmallName()
0x14047  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1404c  ldarg.0
0x1404d  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_IconVectorName()
0x14052  brfalse.s loc_14065
0x14054  ldarg.1
0x14055  ldstr    aIconvectorname// "IconVectorName"
0x1405a  ldarg.0
0x1405b  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_IconVectorName()
0x14060  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x14065  ldarg.0
0x14066  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x1406b  brfalse.s loc_1407D
0x1406d  ldarg.1
0x1406e  ldstr    aIsactivity// "IsActivity"
0x14073  ldstr    a1_1// "1"
0x14078  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1407d  ldarg.1
0x1407e  ldstr    aActivitytypema// "ActivityTypeMask"
0x14083  ldarg.0
0x14084  call     instance valuetype Microsoft.Crm.Metadata.ActivityTypeMasks Microsoft.Crm.Metadata.EntityMetadata::get_ActivityTypeMask()
0x14089  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1408e  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x14093  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x14098  ldarg.0
0x14099  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_AddressTableName()
0x1409e  brfalse.s loc_140B1
0x140a0  ldarg.1
0x140a1  ldstr    aAddresstablena// "AddressTableName"
0x140a6  ldarg.0
0x140a7  call     instance string Microsoft.Crm.Metadata.EntityMetadata::get_AddressTableName()
0x140ac  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x140b1  ldarg.0
0x140b2  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsMappable()
0x140b7  brfalse.s loc_140C9
0x140b9  ldarg.1
0x140ba  ldstr    aIsmappable// "IsMappable"
0x140bf  ldstr    a1_1// "1"
0x140c4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x140c9  ldarg.0
0x140ca  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsImportable()
0x140cf  brfalse.s loc_140E1
0x140d1  ldarg.1
0x140d2  ldstr    aIsimportable// "IsImportable"
0x140d7  ldstr    a1_1// "1"
0x140dc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x140e1  ldarg.0
0x140e2  call     instance bool Microsoft.Crm.Metadata.EntityMetadata::get_IsDuplicateCheckSupported()
0x140e7  brfalse.s loc_140F9
0x140e9  ldarg.1
0x140ea  ldstr    aIsduplicateche// "IsDuplicateCheckSupported"
0x140ef  ldstr    a1_1// "1"
0x140f4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x140f9  ldarg.0
0x140fa  call     instance valuetype Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityMetadata::get_OwnershipTypeMask()
0x140ff  brfalse.s loc_14121
0x14101  ldarg.1
0x14102  ldstr    aOwnershiptypem// "OwnershipTypeMask"
0x14107  ldtoken  Microsoft.Crm.Metadata.OwnershipTypes
0x1410c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14111  ldarg.0
0x14112  call     instance valuetype Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityMetadata::get_OwnershipTypeMask()
0x14117  call     string Microsoft.Crm.Platform.ConvertHelper::EnumToXmlString(class [mscorlib]System.Type enumType, int32 value)
  ... truncated ...
```
