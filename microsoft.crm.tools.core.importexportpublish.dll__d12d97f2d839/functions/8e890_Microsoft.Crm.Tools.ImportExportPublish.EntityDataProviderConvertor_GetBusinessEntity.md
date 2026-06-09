# Microsoft.Crm.Tools.ImportExportPublish.EntityDataProviderConvertor::GetBusinessEntity

- ea: `0x8e890`
- end: `0x8e98c`
- name: `Microsoft.Crm.Tools.ImportExportPublish.EntityDataProviderConvertor::GetBusinessEntity`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x8e890`
- `0x8e990`
- `0x8e9b0`

## string_xrefs

- `0x8e937`: `RetrievePluginTypeId`
- `0x8e945`: `RetrieveMultiplePluginTypeId`
- `0x8e90d`: `CreatePluginTypeId`
- `0x8e91b`: `DeletePluginTypeId`
- `0x8e929`: `UpdatePluginTypeId`

## pseudocode

```c

```

## disassembly

```asm
0x8e890  ldarg.1
0x8e891  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8e896  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.EntityDataProvider::.ctor(valuetype [mscorlib]System.Guid)
0x8e89b  stloc.0
0x8e89c  ldarg.1
0x8e89d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x8e8a2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_EntitiesByName()
0x8e8a7  ldstr    aEntitydataprov_0// "EntityDataProvider"
0x8e8ac  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x8e8b1  ldloc.0
0x8e8b2  ldstr    aEntitydataprov_1// "entitydataproviderid"
0x8e8b7  ldarg.2
0x8e8b8  ldstr    aEntitydataprov// "EntityDataProviderId"
0x8e8bd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x8e8c2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8e8c7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8e8cc  box      [mscorlib]System.Guid
0x8e8d1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8e8d6  ldloc.0
0x8e8d7  ldstr    aName// "name"
0x8e8dc  ldarg.2
0x8e8dd  ldstr    aName_1// "Name"
0x8e8e2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x8e8e7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8e8ec  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8e8f1  ldarg.2
0x8e8f2  ldloc.0
0x8e8f3  ldstr    aName_1// "Name"
0x8e8f8  call     void Microsoft.Crm.Tools.ImportExportPublish.EntityDataProviderConvertor::ConvertToStringAttribute(class [System.Xml]System.Xml.XmlNode entityDataProviderNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.EntityDataProvider entityDataProvider, string xmlNodeName)
0x8e8fd  ldarg.2
0x8e8fe  ldloc.0
0x8e8ff  ldstr    aDatasourcelogi// "DataSourceLogicalName"
0x8e904  call     void Microsoft.Crm.Tools.ImportExportPublish.EntityDataProviderConvertor::ConvertToStringAttribute(class [System.Xml]System.Xml.XmlNode entityDataProviderNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.EntityDataProvider entityDataProvider, string xmlNodeName)
0x8e909  ldarg.0
0x8e90a  ldarg.1
0x8e90b  ldloc.0
0x8e90c  ldarg.2
0x8e90d  ldstr    aCreatepluginty// "CreatePluginTypeId"
0x8e912  call     instance void Microsoft.Crm.Tools.ImportExportPublish.EntityDataProviderConvertor::SetPluginTypeIdByTypeName(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entityDataProvider, class [System.Xml]System.Xml.XmlNode entityDataProviderNode, string pluginNodeName)
0x8e917  ldarg.0
0x8e918  ldarg.1
0x8e919  ldloc.0
0x8e91a  ldarg.2
0x8e91b  ldstr    aDeletepluginty// "DeletePluginTypeId"
0x8e920  call     instance void Microsoft.Crm.Tools.ImportExportPublish.EntityDataProviderConvertor::SetPluginTypeIdByTypeName(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entityDataProvider, class [System.Xml]System.Xml.XmlNode entityDataProviderNode, string pluginNodeName)
0x8e925  ldarg.0
0x8e926  ldarg.1
0x8e927  ldloc.0
0x8e928  ldarg.2
0x8e929  ldstr    aUpdatepluginty// "UpdatePluginTypeId"
0x8e92e  call     instance void Microsoft.Crm.Tools.ImportExportPublish.EntityDataProviderConvertor::SetPluginTypeIdByTypeName(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entityDataProvider, class [System.Xml]System.Xml.XmlNode entityDataProviderNode, string pluginNodeName)
0x8e933  ldarg.0
0x8e934  ldarg.1
0x8e935  ldloc.0
0x8e936  ldarg.2
0x8e937  ldstr    aRetrieveplugin// "RetrievePluginTypeId"
0x8e93c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.EntityDataProviderConvertor::SetPluginTypeIdByTypeName(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entityDataProvider, class [System.Xml]System.Xml.XmlNode entityDataProviderNode, string pluginNodeName)
0x8e941  ldarg.0
0x8e942  ldarg.1
0x8e943  ldloc.0
0x8e944  ldarg.2
0x8e945  ldstr    aRetrievemultip// "RetrieveMultiplePluginTypeId"
0x8e94a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.EntityDataProviderConvertor::SetPluginTypeIdByTypeName(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entityDataProvider, class [System.Xml]System.Xml.XmlNode entityDataProviderNode, string pluginNodeName)
0x8e94f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x8e954  ldstr    aIscustomizable// "iscustomizable"
0x8e959  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x8e95e  brfalse.s loc_8E98A
0x8e960  ldarg.2
0x8e961  ldstr    aIscustomizable_0// "IsCustomizable"
0x8e966  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8e96b  stloc.1
0x8e96c  ldloc.1
0x8e96d  brfalse.s loc_8E98A
0x8e96f  ldloc.0
0x8e970  ldstr    aIscustomizable// "iscustomizable"
0x8e975  ldloc.1
0x8e976  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8e97b  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x8e980  box      [mscorlib]System.Boolean
0x8e985  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8e98a  ldloc.0
0x8e98b  ret
```
