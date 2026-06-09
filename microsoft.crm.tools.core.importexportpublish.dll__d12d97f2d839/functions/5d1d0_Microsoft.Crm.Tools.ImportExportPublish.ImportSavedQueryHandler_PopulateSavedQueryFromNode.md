# Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::PopulateSavedQueryFromNode

- ea: `0x5d1d0`
- end: `0x5d480`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::PopulateSavedQueryFromNode`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x5c510`

## callees

- `0x50510`
- `0x5d0b0`
- `0x5d1d0`
- `0x5d480`

## string_xrefs

- `0x5d40c`: `layoutxml`
- `0x5d474`: `layoutxml`
- `0x5d2cc`: `canbedeleted`
- `0x5d2bf`: `CanBeDeleted`
- `0x5d2d2`: `CanBeDeleted`
- `0x5d466`: `columnsetxml`
- `0x5d458`: `fetchxml`

## pseudocode

```c

```

## disassembly

```asm
0x5d1d0  ldarg.1
0x5d1d1  ldstr    aSavedqueryid// "savedqueryid"
0x5d1d6  ldarg.2
0x5d1d7  ldstr    aSavedqueryid// "savedqueryid"
0x5d1dc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d1e1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5d1e6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5d1eb  box      [mscorlib]System.Guid
0x5d1f0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d1f5  ldarg.1
0x5d1f6  ldstr    aReturnedtypeco// "returnedtypecode"
0x5d1fb  ldarg.0
0x5d1fc  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::objectTypeCode
0x5d201  box      [mscorlib]System.Int32
0x5d206  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d20b  ldarg.1
0x5d20c  ldstr    aQuerytype// "querytype"
0x5d211  ldarg.2
0x5d212  ldstr    aQuerytype// "querytype"
0x5d217  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d21c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5d221  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5d226  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x5d22b  box      [mscorlib]System.Int32
0x5d230  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d235  ldarg.1
0x5d236  ldstr    aIsdefault// "isdefault"
0x5d23b  ldarg.0
0x5d23c  ldarg.2
0x5d23d  ldstr    aIsdefault// "isdefault"
0x5d242  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d247  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5d24c  ldstr    a1// "1"
0x5d251  ldc.i4.4
0x5d252  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5d257  ldarg.1
0x5d258  ldstr    aSavedqueryid// "savedqueryid"
0x5d25d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d262  unbox.any [mscorlib]System.Guid
0x5d267  ldarg.1
0x5d268  ldstr    aQuerytype// "querytype"
0x5d26d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d272  unbox.any [mscorlib]System.Int32
0x5d277  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::DetermineIsDefaultValue(bool valueFromXml, valuetype [mscorlib]System.Guid savedQueryId, int32 queryType)
0x5d27c  box      [mscorlib]System.Boolean
0x5d281  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d286  ldarg.2
0x5d287  ldstr    aIscustomizable_0// "IsCustomizable"
0x5d28c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d291  brfalse.s loc_5D2BE
0x5d293  ldarg.1
0x5d294  ldstr    aIscustomizable// "iscustomizable"
0x5d299  ldarg.2
0x5d29a  ldstr    aIscustomizable_0// "IsCustomizable"
0x5d29f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d2a4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5d2a9  ldstr    a1// "1"
0x5d2ae  ldc.i4.4
0x5d2af  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5d2b4  box      [mscorlib]System.Boolean
0x5d2b9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d2be  ldarg.2
0x5d2bf  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x5d2c4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d2c9  brfalse.s loc_5D2F6
0x5d2cb  ldarg.1
0x5d2cc  ldstr    aCanbedeleted// "canbedeleted"
0x5d2d1  ldarg.2
0x5d2d2  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x5d2d7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d2dc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5d2e1  ldstr    a1// "1"
0x5d2e6  ldc.i4.4
0x5d2e7  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5d2ec  box      [mscorlib]System.Boolean
0x5d2f1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d2f6  ldarg.1
0x5d2f7  ldstr    aIsquickfindque// "isquickfindquery"
0x5d2fc  ldarg.2
0x5d2fd  ldstr    aIsquickfindque// "isquickfindquery"
0x5d302  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d307  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5d30c  ldstr    a1// "1"
0x5d311  ldc.i4.4
0x5d312  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5d317  box      [mscorlib]System.Boolean
0x5d31c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d321  ldarg.2
0x5d322  ldstr    aConditionalfor// "conditionalformatting"
0x5d327  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d32c  brfalse.s loc_5D349
0x5d32e  ldarg.1
0x5d32f  ldstr    aConditionalfor// "conditionalformatting"
0x5d334  ldarg.2
0x5d335  ldstr    aConditionalfor// "conditionalformatting"
0x5d33a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d33f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5d344  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d349  ldarg.2
0x5d34a  ldstr    aQueryapi// "queryapi"
0x5d34f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d354  brfalse.s loc_5D371
0x5d356  ldarg.1
0x5d357  ldstr    aQueryapi// "queryapi"
0x5d35c  ldarg.2
0x5d35d  ldstr    aQueryapi// "queryapi"
0x5d362  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d367  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5d36c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d371  ldarg.2
0x5d372  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x5d377  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d37c  brfalse.s loc_5D399
0x5d37e  ldarg.1
0x5d37f  ldstr    aIntroducedvers// "introducedversion"
0x5d384  ldarg.2
0x5d385  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x5d38a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d38f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x5d394  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d399  ldarg.0
0x5d39a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5d39f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5d3a4  ldarg.1
0x5d3a5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x5d3aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string)
0x5d3af  ldarg.0
0x5d3b0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5d3b5  ldarg.0
0x5d3b6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5d3bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5d3c0  ldc.i4.1
0x5d3c1  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x5d3c6  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x5d3cb  stloc.0
0x5d3cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x5d3d1  ldstr    aIscustom// "iscustom"
0x5d3d6  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x5d3db  brfalse.s loc_5D40B
0x5d3dd  ldarg.1
0x5d3de  ldstr    aIscustom// "iscustom"
0x5d3e3  ldarg.0
0x5d3e4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5d3e9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5d3ee  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_IsSystemContext()
0x5d3f3  brtrue.s loc_5D400
0x5d3f5  ldloc.0
0x5d3f6  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x5d3fb  ldc.i4.0
0x5d3fc  ceq
0x5d3fe  br.s     loc_5D401
0x5d400  ldc.i4.0
0x5d401  box      [mscorlib]System.Boolean
0x5d406  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d40b  ldarg.2
0x5d40c  ldstr    aLayoutxml// "layoutxml"
0x5d411  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d416  stloc.1
0x5d417  ldarg.0
0x5d418  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Setup()
0x5d41d  brtrue.s loc_5D455
0x5d41f  ldloc.1
0x5d420  brfalse.s loc_5D455
0x5d422  ldloc.1
0x5d423  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x5d428  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5d42d  ldc.i4.0
0x5d42e  ble.s    loc_5D455
0x5d430  ldloc.1
0x5d431  ldstr    aGrid_0// "grid"
0x5d436  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d43b  ldstr    aObject// "object"
0x5d440  ldarg.0
0x5d441  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::objectTypeCode
0x5d446  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5d44b  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x5d450  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5d455  ldarg.0
0x5d456  ldarg.1
0x5d457  ldarg.2
0x5d458  ldstr    aFetchxml// "fetchxml"
0x5d45d  ldarg.3
0x5d45e  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::SetNullableXmlAttributeValue(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SavedQuery savedQuery, class [System.Xml]System.Xml.XmlNode savedQueryNode, string attributeName, bool isForUpdate)
0x5d463  ldarg.0
0x5d464  ldarg.1
0x5d465  ldarg.2
0x5d466  ldstr    aColumnsetxml// "columnsetxml"
0x5d46b  ldarg.3
0x5d46c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::SetNullableXmlAttributeValue(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SavedQuery savedQuery, class [System.Xml]System.Xml.XmlNode savedQueryNode, string attributeName, bool isForUpdate)
0x5d471  ldarg.0
0x5d472  ldarg.1
0x5d473  ldarg.2
0x5d474  ldstr    aLayoutxml// "layoutxml"
0x5d479  ldarg.3
0x5d47a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::SetNullableXmlAttributeValue(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SavedQuery savedQuery, class [System.Xml]System.Xml.XmlNode savedQueryNode, string attributeName, bool isForUpdate)
0x5d47f  ret
```
