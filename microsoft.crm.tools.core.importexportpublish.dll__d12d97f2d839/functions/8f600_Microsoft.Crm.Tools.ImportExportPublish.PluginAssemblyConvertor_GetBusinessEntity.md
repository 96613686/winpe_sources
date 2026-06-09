# Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyConvertor::GetBusinessEntity

- ea: `0x8f600`
- end: `0x8f877`
- name: `Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyConvertor::GetBusinessEntity`
- size: `631`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x8f600`
- `0x8f880`

## string_xrefs

- `0x8f75a`: `PluginAssemblyId`
- `0x8f76c`: `PluginAssemblyId`
- `0x8f78e`: `PluginAssemblyId`
- `0x8f60b`: `PluginAssembly`
- `0x8f66b`: `publickeytoken`
- `0x8f783`: `pluginassemblyid`
- `0x8f7db`: `pluginassemblyid`

## pseudocode

```c

```

## disassembly

```asm
0x8f600  ldarg.1
0x8f601  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x8f606  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_EntitiesByName()
0x8f60b  ldstr    aPluginassembly_0// "PluginAssembly"
0x8f610  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x8f615  ldarg.1
0x8f616  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginAssembly::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8f61b  stloc.0
0x8f61c  ldarg.2
0x8f61d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8f622  ldstr    aFullname// "FullName"
0x8f627  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x8f62c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8f631  call     class [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::GenerateFromFullAssemblyName(string)
0x8f636  stloc.1
0x8f637  ldloc.0
0x8f638  ldstr    aName// "name"
0x8f63d  ldloc.1
0x8f63e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_ShortName()
0x8f643  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f648  ldloc.0
0x8f649  ldstr    aVersion// "version"
0x8f64e  ldloc.1
0x8f64f  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_Version()
0x8f654  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f659  ldloc.0
0x8f65a  ldstr    aCulture// "culture"
0x8f65f  ldloc.1
0x8f660  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_Culture()
0x8f665  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f66a  ldloc.0
0x8f66b  ldstr    aPublickeytoken// "publickeytoken"
0x8f670  ldloc.1
0x8f671  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::get_PublicKeyToken()
0x8f676  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f67b  ldarg.2
0x8f67c  ldstr    aIsolationmode// "IsolationMode"
0x8f681  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f686  stloc.2
0x8f687  ldloc.2
0x8f688  brfalse.s loc_8F6AA
0x8f68a  ldloc.0
0x8f68b  ldstr    aIsolationmode_0// "isolationmode"
0x8f690  ldloc.2
0x8f691  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f696  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f69b  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8f6a0  box      [mscorlib]System.Int32
0x8f6a5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f6aa  ldarg.2
0x8f6ab  ldstr    aDescription_0// "Description"
0x8f6b0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f6b5  stloc.2
0x8f6b6  ldloc.2
0x8f6b7  brfalse.s loc_8F6CA
0x8f6b9  ldloc.0
0x8f6ba  ldstr    aDescription// "description"
0x8f6bf  ldloc.2
0x8f6c0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f6c5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f6ca  ldarg.2
0x8f6cb  ldstr    aSourcetype_0// "SourceType"
0x8f6d0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f6d5  stloc.2
0x8f6d6  ldloc.2
0x8f6d7  brfalse.s loc_8F6F9
0x8f6d9  ldloc.0
0x8f6da  ldstr    aSourcetype// "sourcetype"
0x8f6df  ldloc.2
0x8f6e0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f6e5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f6ea  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8f6ef  box      [mscorlib]System.Int32
0x8f6f4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f6f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x8f6fe  ldstr    aIscustomizable// "iscustomizable"
0x8f703  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x8f708  brfalse.s loc_8F734
0x8f70a  ldarg.2
0x8f70b  ldstr    aIscustomizable_0// "IsCustomizable"
0x8f710  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f715  stloc.2
0x8f716  ldloc.2
0x8f717  brfalse.s loc_8F734
0x8f719  ldloc.0
0x8f71a  ldstr    aIscustomizable// "iscustomizable"
0x8f71f  ldloc.2
0x8f720  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f725  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x8f72a  box      [mscorlib]System.Boolean
0x8f72f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f734  ldarg.2
0x8f735  ldstr    aPath_0// "Path"
0x8f73a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f73f  stloc.2
0x8f740  ldloc.2
0x8f741  brfalse.s loc_8F754
0x8f743  ldloc.0
0x8f744  ldstr    aPath// "path"
0x8f749  ldloc.2
0x8f74a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f74f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f754  ldarg.2
0x8f755  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8f75a  ldstr    aPluginassembly// "PluginAssemblyId"
0x8f75f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x8f764  brfalse.s loc_8F7AE
0x8f766  ldarg.2
0x8f767  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8f76c  ldstr    aPluginassembly// "PluginAssemblyId"
0x8f771  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x8f776  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8f77b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8f780  brtrue.s loc_8F7AE
0x8f782  ldloc.0
0x8f783  ldstr    aPluginassembly_1// "pluginassemblyid"
0x8f788  ldarg.2
0x8f789  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8f78e  ldstr    aPluginassembly// "PluginAssemblyId"
0x8f793  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x8f798  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8f79d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8f7a2  box      [mscorlib]System.Guid
0x8f7a7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f7ac  br.s     loc_8F7EB
0x8f7ae  ldarg.2
0x8f7af  ldstr    aFilename// "FileName"
0x8f7b4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f7b9  stloc.2
0x8f7ba  ldloc.2
0x8f7bb  brfalse.s loc_8F7EB
0x8f7bd  ldarg.0
0x8f7be  ldloc.2
0x8f7bf  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f7c4  ldloca.s 3
0x8f7c6  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyConvertor::TryParseGuidInFileName(string pluginAssemblyFileName, [out] valuetype [mscorlib]System.Guid& pluginAssemblyId)
0x8f7cb  brfalse.s loc_8F7EB
0x8f7cd  ldloc.3
0x8f7ce  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8f7d3  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8f7d8  brfalse.s loc_8F7EB
0x8f7da  ldloc.0
0x8f7db  ldstr    aPluginassembly_1// "pluginassemblyid"
0x8f7e0  ldloc.3
0x8f7e1  box      [mscorlib]System.Guid
0x8f7e6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f7eb  ldarg.2
0x8f7ec  ldstr    aUrl// "Url"
0x8f7f1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f7f6  stloc.2
0x8f7f7  ldloc.2
0x8f7f8  brfalse.s loc_8F80B
0x8f7fa  ldloc.0
0x8f7fb  ldstr    aUrl_0// "url"
0x8f800  ldloc.2
0x8f801  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f806  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f80b  ldarg.2
0x8f80c  ldstr    aUsername// "UserName"
0x8f811  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f816  stloc.2
0x8f817  ldloc.2
0x8f818  brfalse.s loc_8F82B
0x8f81a  ldloc.0
0x8f81b  ldstr    aUsername_0// "username"
0x8f820  ldloc.2
0x8f821  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f826  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f82b  ldarg.2
0x8f82c  ldstr    aAuthtype// "AuthType"
0x8f831  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f836  stloc.2
0x8f837  ldloc.2
0x8f838  brfalse.s loc_8F855
0x8f83a  ldloc.0
0x8f83b  ldstr    aAuthtype_0// "authtype"
0x8f840  ldloc.2
0x8f841  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f846  call     int32 [mscorlib]System.Int32::Parse(string)
0x8f84b  box      [mscorlib]System.Int32
0x8f850  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f855  ldarg.2
0x8f856  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x8f85b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f860  stloc.2
0x8f861  ldloc.2
0x8f862  brfalse.s loc_8F875
0x8f864  ldloc.0
0x8f865  ldstr    aIntroducedvers// "introducedversion"
0x8f86a  ldloc.2
0x8f86b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f870  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f875  ldloc.0
0x8f876  ret
```
