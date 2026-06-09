# Microsoft.Crm.Tools.ImportExportPublish.ImportSyncAttributeMappingsProfileHandler::SetSyncMappingFiledsFromXmlNode

- ea: `0x62dd0`
- end: `0x62efc`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSyncAttributeMappingsProfileHandler::SetSyncMappingFiledsFromXmlNode`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x62c00`

## callees

- `0x464d0`
- `0x62dd0`
- `0x63500`

## string_xrefs

- `0x62de0`: `iscomputed`
- `0x62e66`: `iscomputed`
- `0x62e85`: `iscomputed`

## pseudocode

```c

```

## disassembly

```asm
0x62dd0  ldc.i4.5
0x62dd1  newarr   [mscorlib]System.String
0x62dd6  dup
0x62dd7  ldc.i4.0
0x62dd8  ldstr    aEntityname_0// "entityname"
0x62ddd  stelem.ref
0x62dde  dup
0x62ddf  ldc.i4.1
0x62de0  ldstr    aIscomputed// "iscomputed"
0x62de5  stelem.ref
0x62de6  dup
0x62de7  ldc.i4.2
0x62de8  ldstr    aAllowedsyncdir// "allowedsyncdirection"
0x62ded  stelem.ref
0x62dee  dup
0x62def  ldc.i4.3
0x62df0  ldstr    aAttributecrmdi// "attributecrmdisplaynames"
0x62df5  stelem.ref
0x62df6  dup
0x62df7  ldc.i4.4
0x62df8  ldstr    aAttributeexcha// "attributeexchangedisplaynames"
0x62dfd  stelem.ref
0x62dfe  stloc.0
0x62dff  ldarg.0
0x62e00  ldarg.1
0x62e01  ldarg.2
0x62e02  ldloc.0
0x62e03  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::InitializeEntity(class [System.Xml]System.Xml.XmlNode entityNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, string[] excludedNodes)
0x62e08  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x62e0d  stloc.1
0x62e0e  ldloca.s 2
0x62e10  ldarg.1
0x62e11  ldstr    aSyncattributem_9// "syncattributemappingidunique"
0x62e16  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x62e1b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62e20  call     instance void [mscorlib]System.Guid::.ctor(string)
0x62e25  ldarg.0
0x62e26  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportSyncAttributeMappingsProfileHandler::parentAttributeMappings
0x62e2b  ldloc.2
0x62e2c  ldloca.s 1
0x62e2e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::TryGetValue(var<u1>, !!T0)
0x62e33  pop
0x62e34  ldarg.2
0x62e35  ldstr    aParentsyncattr// "parentsyncattributemappingid"
0x62e3a  ldloc.1
0x62e3b  box      [mscorlib]System.Guid
0x62e40  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x62e45  ldstr    aSyncattributem_8// "SyncAttributeMapping"
0x62e4a  ldarg.3
0x62e4b  call     string class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SyncAttributeMappingServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::GetEntityTypeCodeAttributeName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x62e50  stloc.3
0x62e51  ldarg.2
0x62e52  ldloc.3
0x62e53  ldarg.0
0x62e54  ldarg.1
0x62e55  ldarg.3
0x62e56  call     instance int32 Microsoft.Crm.Tools.ImportExportPublish.ImportSyncAttributeMappingsProfileHandler::GetEntityTypeCode(class [System.Xml]System.Xml.XmlNode syncAttributeMappingNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x62e5b  box      [mscorlib]System.Int32
0x62e60  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x62e65  ldarg.1
0x62e66  ldstr    aIscomputed// "iscomputed"
0x62e6b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x62e70  stloc.s  4
0x62e72  ldloc.s  4
0x62e74  brfalse.s loc_62EA5
0x62e76  ldloc.s  4
0x62e78  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62e7d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x62e82  brtrue.s loc_62EA5
0x62e84  ldarg.2
0x62e85  ldstr    aIscomputed// "iscomputed"
0x62e8a  ldloc.s  4
0x62e8c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62e91  ldstr    a1// "1"
0x62e96  call     bool [mscorlib]System.String::Equals(string, string)
0x62e9b  box      [mscorlib]System.Boolean
0x62ea0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x62ea5  ldarg.2
0x62ea6  ldstr    aSyncdirection// "syncdirection"
0x62eab  ldarg.2
0x62eac  ldstr    aDefaultsyncdir// "defaultsyncdirection"
0x62eb1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x62eb6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x62ebb  ldarg.1
0x62ebc  ldstr    aAllowedsyncdir// "allowedsyncdirection"
0x62ec1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x62ec6  stloc.s  4
0x62ec8  ldloc.s  4
0x62eca  brfalse.s loc_62EFB
0x62ecc  ldloc.s  4
0x62ece  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62ed3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x62ed8  brtrue.s loc_62EFB
0x62eda  ldarg.2
0x62edb  ldstr    aAllowedsyncdir// "allowedsyncdirection"
0x62ee0  ldloc.s  4
0x62ee2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62ee7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62eec  call     unsigned int8 [mscorlib]System.Byte::Parse(string, class [mscorlib]System.IFormatProvider)
0x62ef1  box      [mscorlib]System.Byte
0x62ef6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x62efb  ret
```
