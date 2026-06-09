# Microsoft.Crm.Metadata.AttributeService::UpdateExternalPartyOrgSettings

- ea: `0x1b450`
- end: `0x1b973`
- name: `Microsoft.Crm.Metadata.AttributeService::UpdateExternalPartyOrgSettings`
- size: `1315`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1b070`

## callees

- `0x1b450`

## string_xrefs

- `0x1b4fe`: `ExternalChannelAccessEnabledEntity`
- `0x1b6d1`: `ExternalPartyParentRecord/ExternalChannelAccessEnabledEntity`

## pseudocode

```c

```

## disassembly

```asm
0x1b450  ldc.i4.0
0x1b451  stloc.0
0x1b452  ldstr    aOrganization// "Organization"
0x1b457  ldarg.3
0x1b458  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1b45d  stloc.1
0x1b45e  ldloc.1
0x1b45f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1b464  ldc.i4.2
0x1b465  newarr   [mscorlib]System.String
0x1b46a  dup
0x1b46b  ldc.i4.0
0x1b46c  ldstr    aExternalpartye// "externalpartyentitysettings"
0x1b471  stelem.ref
0x1b472  dup
0x1b473  ldc.i4.1
0x1b474  ldstr    aExternalpartyc// "externalpartycorrelationkeys"
0x1b479  stelem.ref
0x1b47a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1b47f  ldnull
0x1b480  stloc.2
0x1b481  ldarg.3
0x1b482  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1b487  ldstr    aOrganization// "Organization"
0x1b48c  ldarg.3
0x1b48d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b492  stloc.3
0x1b493  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrganizationService::.ctor()
0x1b498  stloc.s  4
0x1b49a  ldloc.s  4
0x1b49c  ldloc.3
0x1b49d  ldloc.1
0x1b49e  ldarg.3
0x1b49f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1b4a4  stloc.2
0x1b4a5  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1b4aa  stloc.s  5
0x1b4ac  ldloc.s  5
0x1b4ae  ldnull
0x1b4af  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x1b4b4  ldloc.s  5
0x1b4b6  ldloc.2
0x1b4b7  ldstr    aExternalpartye// "externalpartyentitysettings"
0x1b4bc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b4c1  castclass [mscorlib]System.String
0x1b4c6  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x1b4cb  ldloc.s  5
0x1b4cd  ldstr    aExternalpartye_0// "/ExternalPartyEnabledEntities/ExternalP"...
0x1b4d2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1b4d7  stloc.s  6
0x1b4d9  ldloc.s  6
0x1b4db  brfalse  loc_1B7FD
0x1b4e0  ldloc.s  6
0x1b4e2  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1b4e7  stloc.s  9
0x1b4e9  br       loc_1B7DA
0x1b4ee  ldloc.s  9
0x1b4f0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1b4f5  castclass [System.Xml]System.Xml.XmlNode
0x1b4fa  stloc.s  0xA
0x1b4fc  ldloc.s  0xA
0x1b4fe  ldstr    aExternalchanne// "ExternalChannelAccessEnabledEntity"
0x1b503  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1b508  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1b50d  stloc.s  0xC
0x1b50f  br       loc_1B5DA
0x1b514  ldloc.s  0xC
0x1b516  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1b51b  castclass [System.Xml]System.Xml.XmlNode
0x1b520  stloc.s  0xD
0x1b522  ldloc.s  0xD
0x1b524  ldstr    aEntitylogicaln_0// "EntityLogicalName"
0x1b529  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1b52e  stloc.s  0xE
0x1b530  ldloc.s  0xD
0x1b532  ldstr    aAssociatedfiel// "AssociatedField"
0x1b537  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1b53c  stloc.s  0xF
0x1b53e  ldloc.s  0xF
0x1b540  brfalse  loc_1B5DA
0x1b545  ldloc.s  0xF
0x1b547  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x1b54c  brfalse  loc_1B5DA
0x1b551  ldloc.s  0xF
0x1b553  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b558  ldc.i4.0
0x1b559  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b55e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b563  brfalse.s loc_1B5DA
0x1b565  ldarg.1
0x1b566  ldloc.s  0xF
0x1b568  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b56d  ldc.i4.0
0x1b56e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b573  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b578  callvirt instance string [mscorlib]System.String::Trim()
0x1b57d  callvirt instance string [mscorlib]System.String::ToLower()
0x1b582  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b587  brfalse.s loc_1B5DA
0x1b589  ldloc.s  0xE
0x1b58b  brfalse.s loc_1B5DA
0x1b58d  ldloc.s  0xE
0x1b58f  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x1b594  brfalse.s loc_1B5DA
0x1b596  ldloc.s  0xE
0x1b598  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b59d  ldc.i4.0
0x1b59e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b5a3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b5a8  brfalse.s loc_1B5DA
0x1b5aa  ldarg.2
0x1b5ab  ldloc.s  0xE
0x1b5ad  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b5b2  ldc.i4.0
0x1b5b3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b5b8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b5bd  callvirt instance string [mscorlib]System.String::Trim()
0x1b5c2  callvirt instance string [mscorlib]System.String::ToLower()
0x1b5c7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b5cc  brfalse.s loc_1B5DA
0x1b5ce  ldloc.s  0xA
0x1b5d0  ldloc.s  0xD
0x1b5d2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x1b5d7  pop
0x1b5d8  ldc.i4.1
0x1b5d9  stloc.0
0x1b5da  ldloc.s  0xC
0x1b5dc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b5e1  brtrue   loc_1B514
0x1b5e6  leave.s  loc_1B5FD
0x1b5e8  ldloc.s  0xC
0x1b5ea  isinst   [mscorlib]System.IDisposable
0x1b5ef  stloc.s  0x10
0x1b5f1  ldloc.s  0x10
0x1b5f3  brfalse.s loc_1B5FC
0x1b5f5  ldloc.s  0x10
0x1b5f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b5fc  endfinally
0x1b5fd  ldloc.s  0xA
0x1b5ff  ldstr    aExternalpartyp// "ExternalPartyParentRecord"
0x1b604  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1b609  stloc.s  0xB
0x1b60b  ldloc.s  0xB
0x1b60d  brfalse  loc_1B7DA
0x1b612  ldloc.s  0xA
0x1b614  ldstr    aEntitylogicaln_0// "EntityLogicalName"
0x1b619  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1b61e  stloc.s  0x11
0x1b620  ldloc.s  0xB
0x1b622  ldstr    aFieldlogicalna// "FieldLogicalName"
0x1b627  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1b62c  stloc.s  0x12
0x1b62e  ldloc.s  0x12
0x1b630  brfalse  loc_1B6CF
0x1b635  ldloc.s  0x12
0x1b637  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x1b63c  brfalse  loc_1B6CF
0x1b641  ldloc.s  0x12
0x1b643  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b648  ldc.i4.0
0x1b649  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b64e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b653  brfalse.s loc_1B6CF
0x1b655  ldarg.1
0x1b656  ldloc.s  0x12
0x1b658  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b65d  ldc.i4.0
0x1b65e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b663  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b668  callvirt instance string [mscorlib]System.String::Trim()
0x1b66d  callvirt instance string [mscorlib]System.String::ToLower()
0x1b672  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b677  brfalse.s loc_1B6CF
0x1b679  ldloc.s  0x11
0x1b67b  brfalse.s loc_1B6CF
0x1b67d  ldloc.s  0x11
0x1b67f  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x1b684  brfalse.s loc_1B6CF
0x1b686  ldloc.s  0x11
0x1b688  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b68d  ldc.i4.0
0x1b68e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b693  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b698  brfalse.s loc_1B6CF
0x1b69a  ldarg.2
0x1b69b  ldloc.s  0x11
0x1b69d  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b6a2  ldc.i4.0
0x1b6a3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b6a8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b6ad  callvirt instance string [mscorlib]System.String::Trim()
0x1b6b2  callvirt instance string [mscorlib]System.String::ToLower()
0x1b6b7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b6bc  brfalse.s loc_1B6CF
0x1b6be  ldloc.s  0xA
0x1b6c0  ldloc.s  0xB
0x1b6c2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x1b6c7  pop
0x1b6c8  ldc.i4.1
0x1b6c9  stloc.0
0x1b6ca  br       loc_1B7DA
0x1b6cf  ldloc.s  0xA
0x1b6d1  ldstr    aExternalpartyp_0// "ExternalPartyParentRecord/ExternalChann"...
0x1b6d6  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1b6db  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1b6e0  stloc.s  0xC
0x1b6e2  br       loc_1B7B7
0x1b6e7  ldloc.s  0xC
0x1b6e9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1b6ee  castclass [System.Xml]System.Xml.XmlNode
0x1b6f3  stloc.s  0x13
0x1b6f5  ldloc.s  0x13
0x1b6f7  ldstr    aEntitylogicaln_0// "EntityLogicalName"
0x1b6fc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1b701  stloc.s  0x14
0x1b703  ldloc.s  0x13
0x1b705  ldstr    aAssociatedfiel// "AssociatedField"
0x1b70a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1b70f  stloc.s  0x15
0x1b711  ldloc.s  0x15
0x1b713  brfalse  loc_1B7B7
0x1b718  ldloc.s  0x15
0x1b71a  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x1b71f  brfalse  loc_1B7B7
0x1b724  ldloc.s  0x15
0x1b726  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b72b  ldc.i4.0
0x1b72c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b731  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b736  brfalse.s loc_1B7B7
0x1b738  ldarg.1
0x1b739  ldloc.s  0x15
0x1b73b  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b740  ldc.i4.0
0x1b741  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b746  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b74b  callvirt instance string [mscorlib]System.String::Trim()
0x1b750  callvirt instance string [mscorlib]System.String::ToLower()
0x1b755  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b75a  brfalse.s loc_1B7B7
0x1b75c  ldloc.s  0x14
0x1b75e  brfalse.s loc_1B7B7
0x1b760  ldloc.s  0x14
0x1b762  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x1b767  brfalse.s loc_1B7B7
0x1b769  ldloc.s  0x14
0x1b76b  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b770  ldc.i4.0
0x1b771  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b776  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b77b  brfalse.s loc_1B7B7
0x1b77d  ldarg.2
0x1b77e  ldloc.s  0x14
0x1b780  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b785  ldc.i4.0
0x1b786  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1b78b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1b790  callvirt instance string [mscorlib]System.String::Trim()
0x1b795  callvirt instance string [mscorlib]System.String::ToLower()
0x1b79a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b79f  brfalse.s loc_1B7B7
0x1b7a1  ldloc.s  0xA
0x1b7a3  ldstr    aExternalpartyp// "ExternalPartyParentRecord"
0x1b7a8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1b7ad  ldloc.s  0x13
0x1b7af  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x1b7b4  pop
0x1b7b5  ldc.i4.1
0x1b7b6  stloc.0
0x1b7b7  ldloc.s  0xC
0x1b7b9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b7be  brtrue   loc_1B6E7
0x1b7c3  leave.s  loc_1B7DA
0x1b7c5  ldloc.s  0xC
0x1b7c7  isinst   [mscorlib]System.IDisposable
0x1b7cc  stloc.s  0x10
0x1b7ce  ldloc.s  0x10
0x1b7d0  brfalse.s loc_1B7D9
0x1b7d2  ldloc.s  0x10
0x1b7d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b7d9  endfinally
0x1b7da  ldloc.s  9
0x1b7dc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b7e1  brtrue   loc_1B4EE
0x1b7e6  leave.s  loc_1B7FD
0x1b7e8  ldloc.s  9
0x1b7ea  isinst   [mscorlib]System.IDisposable
0x1b7ef  stloc.s  0x10
0x1b7f1  ldloc.s  0x10
0x1b7f3  brfalse.s loc_1B7FC
0x1b7f5  ldloc.s  0x10
0x1b7f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b7fc  endfinally
0x1b7fd  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1b802  stloc.s  7
0x1b804  ldloc.s  7
0x1b806  ldnull
0x1b807  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x1b80c  ldloc.s  7
0x1b80e  ldloc.2
  ... truncated ...
```
