# Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::AddChannelAccessProfilePrivileges

- ea: `0x2c2c0`
- end: `0x2c3cb`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::AddChannelAccessProfilePrivileges`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x2bf80`

## callees

- `0x2c2c0`

## string_xrefs

- `0x2c2ff`: `channelaccessprofileid`
- `0x2c2c0`: `ChannelAccessProfileEntityAccessLevel`
- `0x2c2cc`: `ChannelAccessProfileEntityAccessLevel`
- `0x2c2e6`: `entityaccesslevelid`
- `0x2c364`: `entityaccesslevelid`
- `0x2c2ee`: `entityaccessleveldepthmask`
- `0x2c385`: `entityaccessleveldepthmask`
- `0x2c31a`: `ChannelAccessProfilePrivileges`
- `0x2c34f`: `ChannelAccessProfilePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x2c2c0  ldstr    aChannelaccessp_7// "ChannelAccessProfileEntityAccessLevel"
0x2c2c5  ldarg.2
0x2c2c6  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2c2cb  stloc.0
0x2c2cc  ldstr    aChannelaccessp_7// "ChannelAccessProfileEntityAccessLevel"
0x2c2d1  ldarg.2
0x2c2d2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2c2d7  stloc.1
0x2c2d8  ldloc.1
0x2c2d9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2c2de  ldc.i4.2
0x2c2df  newarr   [mscorlib]System.String
0x2c2e4  dup
0x2c2e5  ldc.i4.0
0x2c2e6  ldstr    aEntityaccessle// "entityaccesslevelid"
0x2c2eb  stelem.ref
0x2c2ec  dup
0x2c2ed  ldc.i4.1
0x2c2ee  ldstr    aEntityaccessle_0// "entityaccessleveldepthmask"
0x2c2f3  stelem.ref
0x2c2f4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2c2f9  ldloc.1
0x2c2fa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2c2ff  ldstr    aChannelaccessp_1// "channelaccessprofileid"
0x2c304  ldc.i4.0
0x2c305  ldarg.1
0x2c306  box      [mscorlib]System.Guid
0x2c30b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2c310  pop
0x2c311  ldloc.0
0x2c312  ldloc.1
0x2c313  ldarg.2
0x2c314  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2c319  ldarg.3
0x2c31a  ldstr    aChannelaccessp_8// "ChannelAccessProfilePrivileges"
0x2c31f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2c324  stloc.3
0x2c325  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2c32a  stloc.s  4
0x2c32c  br.s     loc_2C3A1
0x2c32e  ldloc.s  4
0x2c330  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2c335  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2c33a  stloc.s  5
0x2c33c  ldarg.0
0x2c33d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::_context
0x2c342  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2c347  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IPrivilegeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Privileges()
0x2c34c  stloc.s  6
0x2c34e  ldarg.3
0x2c34f  ldstr    aChannelaccessp_9// "ChannelAccessProfilePrivilege"
0x2c354  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2c359  stloc.2
0x2c35a  ldloc.2
0x2c35b  ldstr    aName// "name"
0x2c360  ldloc.s  6
0x2c362  ldloc.s  5
0x2c364  ldstr    aEntityaccessle// "entityaccesslevelid"
0x2c369  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2c36e  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege>::get_Item(!!T0)
0x2c373  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Name()
0x2c378  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x2c37d  ldloc.2
0x2c37e  ldstr    aLevel// "level"
0x2c383  ldloc.s  5
0x2c385  ldstr    aEntityaccessle_0// "entityaccessleveldepthmask"
0x2c38a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2c38f  callvirt instance string [mscorlib]System.Object::ToString()
0x2c394  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x2c399  ldloc.3
0x2c39a  ldloc.2
0x2c39b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2c3a0  pop
0x2c3a1  ldloc.s  4
0x2c3a3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2c3a8  brtrue.s loc_2C32E
0x2c3aa  leave.s  loc_2C3C1
0x2c3ac  ldloc.s  4
0x2c3ae  isinst   [mscorlib]System.IDisposable
0x2c3b3  stloc.s  7
0x2c3b5  ldloc.s  7
0x2c3b7  brfalse.s loc_2C3C0
0x2c3b9  ldloc.s  7
0x2c3bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c3c0  endfinally
0x2c3c1  ldarg.s  4
0x2c3c3  ldloc.3
0x2c3c4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2c3c9  pop
0x2c3ca  ret
```
