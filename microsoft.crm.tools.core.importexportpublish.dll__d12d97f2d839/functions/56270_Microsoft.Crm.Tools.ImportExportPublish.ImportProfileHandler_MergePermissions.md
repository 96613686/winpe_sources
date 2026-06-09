# Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::MergePermissions

- ea: `0x56270`
- end: `0x566ce`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::MergePermissions`
- size: `1118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x55ee0`

## callees

- `0x56150`
- `0x56270`
- `0x566d0`
- `0x686f0`

## string_xrefs

- `0x563c2`: `fieldsecurityprofileid`
- `0x56330`: `CanRead`
- `0x56428`: `CanRead`
- `0x56329`: `canread`
- `0x56421`: `canread`
- `0x56352`: `CanUpdate`
- `0x5644a`: `CanUpdate`
- `0x5634b`: `canupdate`
- `0x56443`: `canupdate`
- `0x56374`: `CanCreate`
- `0x5646c`: `CanCreate`
- `0x5636d`: `cancreate`
- `0x56465`: `cancreate`
- `0x56613`: `/importexportxml/FieldSecurityProfiles/FieldSecurityProfile[@id='{0}']`
- `0x56684`: `/importexportxml/FieldSecurityProfiles/FieldSecurityProfile[@id='{0}']`

## pseudocode

```c

```

## disassembly

```asm
0x56270  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x56275  stloc.0
0x56276  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5627b  stloc.1
0x5627c  ldarg.1
0x5627d  ldstr    aFieldpermissio_1// "FieldPermissions/FieldPermission"
0x56282  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x56287  stloc.2
0x56288  ldloc.2
0x56289  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5628e  stloc.3
0x5628f  br       loc_564FC
0x56294  ldloc.3
0x56295  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5629a  castclass [System.Xml]System.Xml.XmlNode
0x5629f  stloc.s  4
0x562a1  ldarg.2
0x562a2  ldloc.s  4
0x562a4  ldstr    aEntityname// "EntityName"
0x562a9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x562ae  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x562b3  ldc.i4.1
0x562b4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x562b9  stloc.s  5
0x562bb  ldnull
0x562bc  stloc.s  6
0x562be  ldloc.s  5
0x562c0  brfalse.s loc_562E1
0x562c2  ldloc.s  5
0x562c4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x562c9  ldloc.s  4
0x562cb  ldstr    aAttributename// "AttributeName"
0x562d0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x562d5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x562da  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x562df  stloc.s  6
0x562e1  ldloc.s  4
0x562e3  ldstr    aEntityname// "EntityName"
0x562e8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x562ed  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x562f2  ldstr    asc_CD6F2// ":"
0x562f7  ldloc.s  4
0x562f9  ldstr    aAttributename// "AttributeName"
0x562fe  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x56303  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x56308  call     string [mscorlib]System.String::Concat(string, string, string)
0x5630d  stloc.s  7
0x5630f  ldarg.3
0x56310  ldloc.s  7
0x56312  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission>::ContainsKey(var<u1>)
0x56317  brfalse  loc_563A0
0x5631c  ldarg.3
0x5631d  ldloc.s  7
0x5631f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission>::get_Item(void)
0x56324  stloc.s  8
0x56326  ldarg.0
0x56327  ldloc.s  8
0x56329  ldstr    aCanread_0// "canread"
0x5632e  ldloc.s  4
0x56330  ldstr    aCanread// "CanRead"
0x56335  ldloc.s  6
0x56337  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForRead()
0x5633c  ldloc.s  6
0x5633e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForRead()
0x56343  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::SetPermission(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission permission, string permissionName, class [System.Xml]System.Xml.XmlNode permissionNode, string permissionNodeName, bool validFor, bool canBeSecuredFor)
0x56348  ldarg.0
0x56349  ldloc.s  8
0x5634b  ldstr    aCanupdate_0// "canupdate"
0x56350  ldloc.s  4
0x56352  ldstr    aCanupdate// "CanUpdate"
0x56357  ldloc.s  6
0x56359  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0x5635e  ldloc.s  6
0x56360  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForUpdate()
0x56365  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::SetPermission(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission permission, string permissionName, class [System.Xml]System.Xml.XmlNode permissionNode, string permissionNodeName, bool validFor, bool canBeSecuredFor)
0x5636a  ldarg.0
0x5636b  ldloc.s  8
0x5636d  ldstr    aCancreate_0// "cancreate"
0x56372  ldloc.s  4
0x56374  ldstr    aCancreate// "CanCreate"
0x56379  ldloc.s  6
0x5637b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0x56380  ldloc.s  6
0x56382  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForCreate()
0x56387  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::SetPermission(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission permission, string permissionName, class [System.Xml]System.Xml.XmlNode permissionNode, string permissionNodeName, bool validFor, bool canBeSecuredFor)
0x5638c  ldarg.s  4
0x5638e  ldloc.s  8
0x56390  ldarg.0
0x56391  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::_context
0x56396  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5639b  br       loc_564FC
0x563a0  ldloc.s  6
0x563a2  brfalse  loc_564CA
0x563a7  ldloc.s  6
0x563a9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x563ae  brfalse  loc_56496
0x563b3  ldarg.0
0x563b4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::_context
0x563b9  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x563be  stloc.s  9
0x563c0  ldloc.s  9
0x563c2  ldstr    aFieldsecurityp_0// "fieldsecurityprofileid"
0x563c7  ldarg.s  5
0x563c9  box      [mscorlib]System.Guid
0x563ce  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x563d3  ldloc.s  9
0x563d5  ldstr    aFieldpermissio_0// "fieldpermissionid"
0x563da  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x563df  box      [mscorlib]System.Guid
0x563e4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x563e9  ldloc.s  9
0x563eb  ldstr    aEntityname_0// "entityname"
0x563f0  ldloc.s  5
0x563f2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x563f7  box      [mscorlib]System.Int32
0x563fc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x56401  ldloc.s  9
0x56403  ldstr    aAttributelogic_0// "attributelogicalname"
0x56408  ldloc.s  4
0x5640a  ldstr    aAttributename// "AttributeName"
0x5640f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x56414  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x56419  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5641e  ldarg.0
0x5641f  ldloc.s  9
0x56421  ldstr    aCanread_0// "canread"
0x56426  ldloc.s  4
0x56428  ldstr    aCanread// "CanRead"
0x5642d  ldloc.s  6
0x5642f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForRead()
0x56434  ldloc.s  6
0x56436  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForRead()
0x5643b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::SetPermission(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission permission, string permissionName, class [System.Xml]System.Xml.XmlNode permissionNode, string permissionNodeName, bool validFor, bool canBeSecuredFor)
0x56440  ldarg.0
0x56441  ldloc.s  9
0x56443  ldstr    aCanupdate_0// "canupdate"
0x56448  ldloc.s  4
0x5644a  ldstr    aCanupdate// "CanUpdate"
0x5644f  ldloc.s  6
0x56451  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0x56456  ldloc.s  6
0x56458  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForUpdate()
0x5645d  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::SetPermission(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission permission, string permissionName, class [System.Xml]System.Xml.XmlNode permissionNode, string permissionNodeName, bool validFor, bool canBeSecuredFor)
0x56462  ldarg.0
0x56463  ldloc.s  9
0x56465  ldstr    aCancreate_0// "cancreate"
0x5646a  ldloc.s  4
0x5646c  ldstr    aCancreate// "CanCreate"
0x56471  ldloc.s  6
0x56473  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0x56478  ldloc.s  6
0x5647a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForCreate()
0x5647f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::SetPermission(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission permission, string permissionName, class [System.Xml]System.Xml.XmlNode permissionNode, string permissionNodeName, bool validFor, bool canBeSecuredFor)
0x56484  ldarg.s  4
0x56486  ldloc.s  9
0x56488  ldarg.0
0x56489  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::_context
0x5648e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x56493  pop
0x56494  br.s     loc_564FC
0x56496  ldloc.1
0x56497  ldloc.s  4
0x56499  ldstr    aEntityname// "EntityName"
0x5649e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x564a3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x564a8  ldstr    asc_CD6F2// ":"
0x564ad  ldloc.s  4
0x564af  ldstr    aAttributename// "AttributeName"
0x564b4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x564b9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x564be  call     string [mscorlib]System.String::Concat(string, string, string)
0x564c3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x564c8  br.s     loc_564FC
0x564ca  ldloc.0
0x564cb  ldloc.s  4
0x564cd  ldstr    aEntityname// "EntityName"
0x564d2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x564d7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x564dc  ldstr    asc_CD6F2// ":"
0x564e1  ldloc.s  4
0x564e3  ldstr    aAttributename// "AttributeName"
0x564e8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x564ed  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x564f2  call     string [mscorlib]System.String::Concat(string, string, string)
0x564f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x564fc  ldloc.3
0x564fd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x56502  brtrue   loc_56294
0x56507  leave.s  loc_5651D
0x56509  ldloc.3
0x5650a  isinst   [mscorlib]System.IDisposable
0x5650f  stloc.s  0xA
0x56511  ldloc.s  0xA
0x56513  brfalse.s loc_5651C
0x56515  ldloc.s  0xA
0x56517  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5651c  endfinally
0x5651d  ldarg.3
0x5651e  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission>::GetEnumerator()
0x56523  stloc.s  0xB
0x56525  br       loc_565C3
0x5652a  ldloca.s 0xB
0x5652c  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission>::get_Current()
0x56531  stloc.s  0xC
0x56533  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x56538  ldstr    aFieldpermissio_2// "FieldPermissions/FieldPermission[Entity"...
0x5653d  ldc.i4.2
0x5653e  newarr   [mscorlib]System.Object
0x56543  dup
0x56544  ldc.i4.0
0x56545  ldarg.2
0x56546  ldloca.s 0xC
0x56548  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission>::get_Value()
0x5654d  ldstr    aEntityname_0// "entityname"
0x56552  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x56557  unbox.any [mscorlib]System.Int32
0x5655c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x56561  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x56566  stelem.ref
0x56567  dup
0x56568  ldc.i4.1
0x56569  ldloca.s 0xC
0x5656b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission>::get_Value()
0x56570  ldstr    aAttributelogic_0// "attributelogicalname"
0x56575  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5657a  stelem.ref
0x5657b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x56580  stloc.s  0xD
0x56582  ldarg.1
0x56583  ldloc.s  0xD
0x56585  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5658a  brtrue.s loc_565C3
0x5658c  ldloca.s 0xC
0x5658e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission>::get_Value()
0x56593  ldstr    aFieldpermissio_0// "fieldpermissionid"
0x56598  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5659d  unbox.any [mscorlib]System.Guid
0x565a2  ldstr    aFieldpermissio// "FieldPermission"
0x565a7  ldarg.0
0x565a8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::_context
0x565ad  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x565b2  stloc.s  0xE
0x565b4  ldarg.s  4
0x565b6  ldloc.s  0xE
0x565b8  ldarg.0
0x565b9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::_context
0x565be  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x565c3  ldloca.s 0xB
0x565c5  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission>::MoveNext()
0x565ca  brtrue   loc_5652A
0x565cf  leave.s  loc_565DF
0x565d1  ldloca.s 0xB
0x565d3  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission>
0x565d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x565de  endfinally
0x565df  ldloc.0
0x565e0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x565e5  ldc.i4.0
0x565e6  ble.s    loc_56650
0x565e8  ldc.i4.1
0x565e9  newarr   [mscorlib]System.String
0x565ee  stloc.s  0xF
0x565f0  ldloc.s  0xF
0x565f2  ldc.i4.0
0x565f3  ldarg.0
0x565f4  ldloc.0
0x565f5  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::ConvertToString(class [mscorlib]System.Collections.Generic.List`1<string> list)
0x565fa  stelem.ref
0x565fb  ldc.i4   0x80048064
0x56600  ldloc.s  0xF
0x56602  stloc.s  0x10
0x56604  ldloc.s  0x10
0x56606  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x5660b  throw
0x5660c  stloc.s  0x11
0x5660e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x56613  ldstr    aImportexportxm_136// "/importexportxml/FieldSecurityProfiles/"...
0x56618  ldc.i4.1
0x56619  newarr   [mscorlib]System.Object
0x5661e  dup
0x5661f  ldc.i4.0
0x56620  ldarg.0
0x56621  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::_id
0x56626  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5662b  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x56630  stelem.ref
0x56631  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x56636  stloc.s  0x12
0x56638  ldarg.0
0x56639  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x5663e  ldloc.s  0x12
0x56640  ldstr    aWarning// "warning"
0x56645  ldloc.s  0x11
0x56647  ldc.i4.0
0x56648  ldc.i4.0
0x56649  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x5664e  leave.s  loc_56650
0x56650  ldloc.1
0x56651  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x56656  ldc.i4.0
  ... truncated ...
```
