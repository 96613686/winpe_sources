# Microsoft.Crm.Metadata.EntityDescription::FillPropertiesFromXml_0

- ea: `0x2c390`
- end: `0x2d837`
- name: `Microsoft.Crm.Metadata.EntityDescription::FillPropertiesFromXml_0`
- size: `5287`
- prototype: ``
- caller_count: `0`
- callee_count: `148`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0xbbf0`
- `0xbc40`
- `0xbc50`
- `0xbc60`
- `0xbc80`
- `0x18a80`
- `0x2c390`
- `0x2d860`
- `0x2d870`
- `0x2d880`
- `0x2d8a0`
- `0x2d8c0`
- `0x2d8e0`
- `0x2d900`
- `0x2d920`
- `0x2d940`
- `0x2d960`
- `0x2d980`
- `0x2d9a0`
- `0x2d9c0`
- `0x2d9e0`
- `0x2da00`
- `0x2da20`
- `0x2da40`
- `0x2da60`
- `0x2da80`
- `0x2daa0`
- `0x2dac0`
- `0x2dae0`
- `0x2db00`
- `0x2db20`
- `0x2db40`
- `0x2db60`
- `0x2db80`
- `0x2dba0`
- `0x2dbc0`
- `0x2dbe0`
- `0x2dc00`
- `0x2dc20`
- `0x2dc40`
- `0x2dc60`
- `0x2dc80`
- `0x2dca0`
- `0x2dcc0`
- `0x2dce0`
- `0x2dd00`
- `0x2dd20`
- `0x2dd40`
- `0x2dd60`
- `0x2dd80`

## string_xrefs

- `0x2cd2c`: `IsRenameable`
- `0x2cd3a`: `IsRenameable`
- `0x2c57b`: `IsSecurityIntersect`
- `0x2c589`: `IsSecurityIntersect`
- `0x2c949`: `MobileAccessLevelMask`
- `0x2c961`: `MobileAccessLevelMask`
- `0x2c9c1`: `IsReadOnlyInMobileClient`
- `0x2c9cf`: `IsReadOnlyInMobileClient`
- `0x2cbce`: `IsAIRUpdated`
- `0x2cbdc`: `IsAIRUpdated`
- `0x2ccc3`: `ExtensionTableName`
- `0x2ccd1`: `ExtensionTableName`
- `0x2cd95`: `IsMergeEnabledSolutionComponent`
- `0x2cda3`: `IsMergeEnabledSolutionComponent`
- `0x2cfde`: `ServiceClassName`
- `0x2cfec`: `ServiceClassName`
- `0x2d001`: `ServiceAssembly`
- `0x2d00f`: `ServiceAssembly`
- `0x2d292`: `CanModifyMobileClientReadOnly`
- `0x2d2a0`: `CanModifyMobileClientReadOnly`
- `0x2d2fb`: `IsReadingPaneEnabled`
- `0x2d309`: `IsReadingPaneEnabled`
- `0x2d341`: `IsQuickCreateEnabled`
- `0x2d34f`: `IsQuickCreateEnabled`
- `0x2d418`: `CanCreateAttributes`
- `0x2d426`: `CanCreateAttributes`
- `0x2d4a4`: `CanCreateForms`
- `0x2d4b2`: `CanCreateForms`
- `0x2d4c7`: `CanCreateCharts`
- `0x2d4d5`: `CanCreateCharts`
- `0x2d4ea`: `CanCreateViews`
- `0x2d4f8`: `CanCreateViews`
- `0x2d1d9`: `ParentComponentType`
- `0x2d1e7`: `ParentComponentType`
- `0x2d0d3`: `IsDocumentRecommendationsEnabled`
- `0x2d0e1`: `IsDocumentRecommendationsEnabled`
- `0x2d77e`: `AvailableForCreate`
- `0x2d796`: `AvailableForCreate`
- `0x2d7b0`: `AvailableForUpdate`
- `0x2d7c8`: `AvailableForUpdate`
- `0x2d7e2`: `AvailableForDelete`
- `0x2d7fa`: `AvailableForDelete`
- `0x2d31e`: `AutoCreateAccessTeams`
- `0x2d32c`: `AutoCreateAccessTeams`
- `0x2d2b5`: `HasIdsTable`
- `0x2d2c3`: `HasIdsTable`
- `0x2c3a9`: `Entity XML must contain the entity id`

## pseudocode

```c

```

## disassembly

```asm
0x2c390  ldarg.1
0x2c391  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2c396  stloc.0
0x2c397  ldarg.1
0x2c398  ldstr    aEntityid// "EntityId"
0x2c39d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c3a2  ldnull
0x2c3a3  ceq
0x2c3a5  ldarg.2
0x2c3a6  and
0x2c3a7  brfalse.s loc_2C3B4
0x2c3a9  ldstr    aEntityXmlMustC// "Entity XML must contain the entity id"
0x2c3ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x2c3b3  throw
0x2c3b4  ldarg.0
0x2c3b5  ldarg.1
0x2c3b6  ldstr    aEntityid// "EntityId"
0x2c3bb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c3c0  brfalse.s loc_2C3D9
0x2c3c2  ldarg.1
0x2c3c3  ldstr    aEntityid// "EntityId"
0x2c3c8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c3cd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c3d2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2c3d7  br.s     loc_2C3DE
0x2c3d9  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x2c3de  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_EntityId(valuetype [mscorlib]System.Guid value)
0x2c3e3  ldloc.0
0x2c3e4  ldstr    aName// "Name"
0x2c3e9  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2c3ee  brfalse.s loc_2C406
0x2c3f0  ldarg.0
0x2c3f1  ldloc.0
0x2c3f2  ldstr    aName// "Name"
0x2c3f7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2c3fc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2c401  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_Name(string value)
0x2c406  ldarg.1
0x2c407  ldstr    aObjecttypecode// "ObjectTypeCode"
0x2c40c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c411  brfalse.s loc_2C433
0x2c413  ldarg.0
0x2c414  ldarg.1
0x2c415  ldstr    aObjecttypecode// "ObjectTypeCode"
0x2c41a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c41f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c424  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c429  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x2c42e  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_ObjectTypeCode(int32 value)
0x2c433  ldarg.1
0x2c434  ldstr    aPhysicalname// "PhysicalName"
0x2c439  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c43e  brfalse.s loc_2C458
0x2c440  ldarg.0
0x2c441  ldarg.1
0x2c442  ldstr    aPhysicalname// "PhysicalName"
0x2c447  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c44c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c451  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_PhysicalName(string value)
0x2c456  br.s     loc_2C464
0x2c458  ldarg.0
0x2c459  ldarg.0
0x2c45a  callvirt instance string Microsoft.Crm.Metadata.EntityDescription::get_Name()
0x2c45f  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_PhysicalName(string value)
0x2c464  ldarg.1
0x2c465  ldstr    aLogicalname// "LogicalName"
0x2c46a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c46f  brfalse.s loc_2C489
0x2c471  ldarg.0
0x2c472  ldarg.1
0x2c473  ldstr    aLogicalname// "LogicalName"
0x2c478  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c47d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c482  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_LogicalName(string value)
0x2c487  br.s     loc_2C49A
0x2c489  ldarg.0
0x2c48a  ldarg.0
0x2c48b  callvirt instance string Microsoft.Crm.Metadata.EntityDescription::get_Name()
0x2c490  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x2c495  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_LogicalName(string value)
0x2c49a  ldarg.1
0x2c49b  ldstr    aExternalname// "ExternalName"
0x2c4a0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c4a5  brfalse.s loc_2C4BD
0x2c4a7  ldarg.0
0x2c4a8  ldarg.1
0x2c4a9  ldstr    aExternalname// "ExternalName"
0x2c4ae  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c4b3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c4b8  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_ExternalName(string value)
0x2c4bd  ldarg.1
0x2c4be  ldstr    aExternalcollec// "ExternalCollectionName"
0x2c4c3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c4c8  brfalse.s loc_2C4E0
0x2c4ca  ldarg.0
0x2c4cb  ldarg.1
0x2c4cc  ldstr    aExternalcollec// "ExternalCollectionName"
0x2c4d1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c4d6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c4db  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_ExternalCollectionName(string value)
0x2c4e0  ldarg.1
0x2c4e1  ldstr    aCollectionname// "CollectionName"
0x2c4e6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c4eb  brfalse.s loc_2C503
0x2c4ed  ldarg.0
0x2c4ee  ldarg.1
0x2c4ef  ldstr    aCollectionname// "CollectionName"
0x2c4f4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c4f9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c4fe  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_CollectionName(string value)
0x2c503  ldarg.1
0x2c504  ldstr    aBasetablename// "BaseTableName"
0x2c509  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c50e  brfalse.s loc_2C528
0x2c510  ldarg.0
0x2c511  ldarg.1
0x2c512  ldstr    aBasetablename// "BaseTableName"
0x2c517  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c51c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c521  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_BaseTableName(string value)
0x2c526  br.s     loc_2C534
0x2c528  ldarg.0
0x2c529  ldarg.0
0x2c52a  callvirt instance string Microsoft.Crm.Metadata.EntityDescription::get_Name()
0x2c52f  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_BaseTableName(string value)
0x2c534  ldarg.1
0x2c535  ldstr    aLogicalcollect// "LogicalCollectionName"
0x2c53a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c53f  brfalse.s loc_2C557
0x2c541  ldarg.0
0x2c542  ldarg.1
0x2c543  ldstr    aLogicalcollect// "LogicalCollectionName"
0x2c548  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c54d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c552  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_LogicalCollectionName(string value)
0x2c557  ldarg.1
0x2c558  ldstr    aIsintersect// "IsIntersect"
0x2c55d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c562  brfalse.s loc_2C57A
0x2c564  ldarg.0
0x2c565  ldarg.1
0x2c566  ldstr    aIsintersect// "IsIntersect"
0x2c56b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c570  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2c575  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsIntersect(bool value)
0x2c57a  ldarg.1
0x2c57b  ldstr    aIssecurityinte// "IsSecurityIntersect"
0x2c580  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c585  brfalse.s loc_2C59D
0x2c587  ldarg.0
0x2c588  ldarg.1
0x2c589  ldstr    aIssecurityinte// "IsSecurityIntersect"
0x2c58e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c593  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2c598  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsSecurityIntersect(bool value)
0x2c59d  ldarg.1
0x2c59e  ldstr    aIslookuptable// "IsLookupTable"
0x2c5a3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c5a8  brfalse.s loc_2C5C0
0x2c5aa  ldarg.0
0x2c5ab  ldarg.1
0x2c5ac  ldstr    aIslookuptable// "IsLookupTable"
0x2c5b1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c5b6  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2c5bb  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsLookupTable(bool value)
0x2c5c0  ldarg.1
0x2c5c1  ldstr    aEventmask// "EventMask"
0x2c5c6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c5cb  brfalse.s loc_2C5ED
0x2c5cd  ldarg.0
0x2c5ce  ldarg.1
0x2c5cf  ldstr    aEventmask// "EventMask"
0x2c5d4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c5d9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c5de  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c5e3  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x2c5e8  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_EventMask(int32 value)
0x2c5ed  ldarg.1
0x2c5ee  ldstr    aIslogicalentit// "IsLogicalEntity"
0x2c5f3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c5f8  brfalse.s loc_2C610
0x2c5fa  ldarg.0
0x2c5fb  ldarg.1
0x2c5fc  ldstr    aIslogicalentit// "IsLogicalEntity"
0x2c601  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c606  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2c60b  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsLogicalEntity(bool value)
0x2c610  ldarg.1
0x2c611  ldstr    aIscustomizable// "IsCustomizable"
0x2c616  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c61b  brfalse.s loc_2C633
0x2c61d  ldarg.0
0x2c61e  ldarg.1
0x2c61f  ldstr    aIscustomizable// "IsCustomizable"
0x2c624  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c629  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2c62e  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsCustomizable(bool value)
0x2c633  ldarg.1
0x2c634  ldstr    aIsmanaged// "IsManaged"
0x2c639  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c63e  brfalse.s loc_2C657
0x2c640  ldarg.0
0x2c641  ldarg.1
0x2c642  ldstr    aIsmanaged// "IsManaged"
0x2c647  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c64c  ldc.i4.1
0x2c64d  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node, bool defaultValue)
0x2c652  callvirt instance void Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::set_IsManaged(bool value)
0x2c657  ldarg.1
0x2c658  ldstr    aIscollaboratio// "IsCollaboration"
0x2c65d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c662  brfalse.s loc_2C67A
0x2c664  ldarg.0
0x2c665  ldarg.1
0x2c666  ldstr    aIscollaboratio// "IsCollaboration"
0x2c66b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c670  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2c675  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsCollaboration(bool value)
0x2c67a  ldarg.1
0x2c67b  ldstr    aIsmultiplequeu// "IsMultipleQueueEnabled"
0x2c680  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c685  brfalse.s loc_2C69D
0x2c687  ldarg.0
0x2c688  ldarg.1
0x2c689  ldstr    aIsmultiplequeu// "IsMultipleQueueEnabled"
0x2c68e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c693  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2c698  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsMultipleQueueEnabled(bool value)
0x2c69d  ldarg.1
0x2c69e  ldstr    aAutoroutetoown// "AutoRouteToOwnerQueue"
0x2c6a3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c6a8  brfalse.s loc_2C6C0
0x2c6aa  ldarg.0
0x2c6ab  ldarg.1
0x2c6ac  ldstr    aAutoroutetoown// "AutoRouteToOwnerQueue"
0x2c6b1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c6b6  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2c6bb  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_AutoRouteToOwnerQueue(bool value)
0x2c6c0  ldarg.1
0x2c6c1  ldstr    aEntityhelpurl// "EntityHelpUrl"
0x2c6c6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c6cb  brfalse.s loc_2C6E3
0x2c6cd  ldarg.0
0x2c6ce  ldarg.1
0x2c6cf  ldstr    aEntityhelpurl// "EntityHelpUrl"
0x2c6d4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c6d9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c6de  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_EntityHelpUrl(string value)
0x2c6e3  ldarg.1
0x2c6e4  ldstr    aEntityhelpurle// "EntityHelpUrlEnabled"
0x2c6e9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c6ee  brfalse.s loc_2C706
0x2c6f0  ldarg.0
0x2c6f1  ldarg.1
0x2c6f2  ldstr    aEntityhelpurle// "EntityHelpUrlEnabled"
0x2c6f7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c6fc  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2c701  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_EntityHelpUrlEnabled(bool value)
0x2c706  ldarg.1
0x2c707  ldstr    aIshsmenabled// "IsHSMEnabled"
0x2c70c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c711  brfalse.s loc_2C729
0x2c713  ldarg.0
0x2c714  ldarg.1
0x2c715  ldstr    aIshsmenabled// "IsHSMEnabled"
0x2c71a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c71f  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2c724  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsHSMEnabled(bool value)
0x2c729  ldarg.1
0x2c72a  ldstr    aIsconnectionse// "IsConnectionsEnabled"
0x2c72f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c734  brfalse.s loc_2C74C
0x2c736  ldarg.0
0x2c737  ldarg.1
0x2c738  ldstr    aIsconnectionse// "IsConnectionsEnabled"
0x2c73d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c742  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x2c747  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IsConnectionsEnabled(bool value)
0x2c74c  ldarg.1
0x2c74d  ldstr    aIconlargename// "IconLargeName"
0x2c752  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c757  brfalse.s loc_2C76F
0x2c759  ldarg.0
0x2c75a  ldarg.1
0x2c75b  ldstr    aIconlargename// "IconLargeName"
0x2c760  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c765  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c76a  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IconLargeName(string value)
0x2c76f  ldarg.1
0x2c770  ldstr    aIconmediumname// "IconMediumName"
0x2c775  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c77a  brfalse.s loc_2C792
0x2c77c  ldarg.0
0x2c77d  ldarg.1
0x2c77e  ldstr    aIconmediumname// "IconMediumName"
0x2c783  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2c788  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2c78d  callvirt instance void Microsoft.Crm.Metadata.EntityDescription::set_IconMediumName(string value)
0x2c792  ldarg.1
0x2c793  ldstr    aIconsmallname// "IconSmallName"
  ... truncated ...
```
