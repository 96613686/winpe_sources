# Microsoft.Crm.Metadata.EntityService::UpdateExternalPartyOrgSettings

- ea: `0x321e0`
- end: `0x3258a`
- name: `Microsoft.Crm.Metadata.EntityService::UpdateExternalPartyOrgSettings`
- size: `938`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x31b10`

## callees

- `0x321e0`

## string_xrefs

- `0x322fd`: `ExternalChannelAccessEnabledEntity`
- `0x323b0`: `ExternalPartyParentRecord/ExternalChannelAccessEnabledEntity`

## pseudocode

```c

```

## disassembly

```asm
0x321e0  ldc.i4.0
0x321e1  stloc.0
0x321e2  ldstr    aOrganization// "Organization"
0x321e7  ldarg.2
0x321e8  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x321ed  stloc.1
0x321ee  ldloc.1
0x321ef  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x321f4  ldc.i4.2
0x321f5  newarr   [mscorlib]System.String
0x321fa  dup
0x321fb  ldc.i4.0
0x321fc  ldstr    aExternalpartye// "externalpartyentitysettings"
0x32201  stelem.ref
0x32202  dup
0x32203  ldc.i4.1
0x32204  ldstr    aExternalpartyc// "externalpartycorrelationkeys"
0x32209  stelem.ref
0x3220a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x3220f  ldnull
0x32210  stloc.2
0x32211  ldarg.2
0x32212  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x32217  ldstr    aOrganization// "Organization"
0x3221c  ldarg.2
0x3221d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x32222  stloc.3
0x32223  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrganizationService::.ctor()
0x32228  stloc.s  4
0x3222a  ldloc.s  4
0x3222c  ldloc.3
0x3222d  ldloc.1
0x3222e  ldarg.2
0x3222f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32234  stloc.2
0x32235  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x3223a  stloc.s  5
0x3223c  ldloc.s  5
0x3223e  ldnull
0x3223f  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x32244  ldloc.s  5
0x32246  ldloc.2
0x32247  ldstr    aExternalpartye// "externalpartyentitysettings"
0x3224c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x32251  castclass [mscorlib]System.String
0x32256  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x3225b  ldloc.s  5
0x3225d  ldstr    aExternalpartye_0// "/ExternalPartyEnabledEntities/ExternalP"...
0x32262  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x32267  stloc.s  6
0x32269  ldloc.s  6
0x3226b  brfalse  loc_3247D
0x32270  ldloc.s  6
0x32272  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x32277  stloc.s  9
0x32279  br       loc_3245A
0x3227e  ldloc.s  9
0x32280  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x32285  castclass [System.Xml]System.Xml.XmlNode
0x3228a  stloc.s  0xA
0x3228c  ldloc.s  0xA
0x3228e  ldstr    aEntitylogicaln_0// "EntityLogicalName"
0x32293  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x32298  stloc.s  0xB
0x3229a  ldloc.s  0xB
0x3229c  brfalse.s loc_322FB
0x3229e  ldloc.s  0xB
0x322a0  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x322a5  brfalse.s loc_322FB
0x322a7  ldloc.s  0xB
0x322a9  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x322ae  ldc.i4.0
0x322af  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x322b4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x322b9  brfalse.s loc_322FB
0x322bb  ldarg.1
0x322bc  ldloc.s  0xB
0x322be  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x322c3  ldc.i4.0
0x322c4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x322c9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x322ce  callvirt instance string [mscorlib]System.String::Trim()
0x322d3  callvirt instance string [mscorlib]System.String::ToLower()
0x322d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x322dd  brfalse.s loc_322FB
0x322df  ldloc.s  5
0x322e1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x322e6  ldc.i4.0
0x322e7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x322ec  ldloc.s  0xA
0x322ee  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x322f3  pop
0x322f4  ldc.i4.1
0x322f5  stloc.0
0x322f6  br       loc_3245A
0x322fb  ldloc.s  0xA
0x322fd  ldstr    aExternalchanne// "ExternalChannelAccessEnabledEntity"
0x32302  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x32307  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x3230c  stloc.s  0xC
0x3230e  br.s     loc_3237D
0x32310  ldloc.s  0xC
0x32312  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x32317  castclass [System.Xml]System.Xml.XmlNode
0x3231c  stloc.s  0xD
0x3231e  ldloc.s  0xD
0x32320  ldstr    aEntitylogicaln_0// "EntityLogicalName"
0x32325  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3232a  stloc.s  0xE
0x3232c  ldloc.s  0xE
0x3232e  brfalse.s loc_3237D
0x32330  ldloc.s  0xE
0x32332  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x32337  brfalse.s loc_3237D
0x32339  ldloc.s  0xE
0x3233b  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x32340  ldc.i4.0
0x32341  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x32346  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x3234b  brfalse.s loc_3237D
0x3234d  ldarg.1
0x3234e  ldloc.s  0xE
0x32350  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x32355  ldc.i4.0
0x32356  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x3235b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x32360  callvirt instance string [mscorlib]System.String::Trim()
0x32365  callvirt instance string [mscorlib]System.String::ToLower()
0x3236a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3236f  brfalse.s loc_3237D
0x32371  ldloc.s  0xA
0x32373  ldloc.s  0xD
0x32375  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x3237a  pop
0x3237b  ldc.i4.1
0x3237c  stloc.0
0x3237d  ldloc.s  0xC
0x3237f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32384  brtrue.s loc_32310
0x32386  leave.s  loc_3239D
0x32388  ldloc.s  0xC
0x3238a  isinst   [mscorlib]System.IDisposable
0x3238f  stloc.s  0xF
0x32391  ldloc.s  0xF
0x32393  brfalse.s loc_3239C
0x32395  ldloc.s  0xF
0x32397  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3239c  endfinally
0x3239d  ldloc.s  0xA
0x3239f  ldstr    aExternalpartyp// "ExternalPartyParentRecord"
0x323a4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x323a9  brfalse  loc_3245A
0x323ae  ldloc.s  0xA
0x323b0  ldstr    aExternalpartyp_0// "ExternalPartyParentRecord/ExternalChann"...
0x323b5  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x323ba  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x323bf  stloc.s  0xC
0x323c1  br.s     loc_3243A
0x323c3  ldloc.s  0xC
0x323c5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x323ca  castclass [System.Xml]System.Xml.XmlNode
0x323cf  stloc.s  0x10
0x323d1  ldloc.s  0x10
0x323d3  ldstr    aEntitylogicaln_0// "EntityLogicalName"
0x323d8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x323dd  stloc.s  0x11
0x323df  ldloc.s  0x11
0x323e1  brfalse.s loc_3243A
0x323e3  ldloc.s  0x11
0x323e5  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x323ea  brfalse.s loc_3243A
0x323ec  ldloc.s  0x11
0x323ee  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x323f3  ldc.i4.0
0x323f4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x323f9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x323fe  brfalse.s loc_3243A
0x32400  ldarg.1
0x32401  ldloc.s  0x11
0x32403  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x32408  ldc.i4.0
0x32409  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x3240e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x32413  callvirt instance string [mscorlib]System.String::Trim()
0x32418  callvirt instance string [mscorlib]System.String::ToLower()
0x3241d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x32422  brfalse.s loc_3243A
0x32424  ldloc.s  0xA
0x32426  ldstr    aExternalpartyp// "ExternalPartyParentRecord"
0x3242b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x32430  ldloc.s  0x10
0x32432  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x32437  pop
0x32438  ldc.i4.1
0x32439  stloc.0
0x3243a  ldloc.s  0xC
0x3243c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32441  brtrue.s loc_323C3
0x32443  leave.s  loc_3245A
0x32445  ldloc.s  0xC
0x32447  isinst   [mscorlib]System.IDisposable
0x3244c  stloc.s  0xF
0x3244e  ldloc.s  0xF
0x32450  brfalse.s loc_32459
0x32452  ldloc.s  0xF
0x32454  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32459  endfinally
0x3245a  ldloc.s  9
0x3245c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32461  brtrue   loc_3227E
0x32466  leave.s  loc_3247D
0x32468  ldloc.s  9
0x3246a  isinst   [mscorlib]System.IDisposable
0x3246f  stloc.s  0xF
0x32471  ldloc.s  0xF
0x32473  brfalse.s loc_3247C
0x32475  ldloc.s  0xF
0x32477  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3247c  endfinally
0x3247d  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x32482  stloc.s  7
0x32484  ldloc.s  7
0x32486  ldloc.2
0x32487  ldstr    aExternalpartyc// "externalpartycorrelationkeys"
0x3248c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x32491  castclass [mscorlib]System.String
0x32496  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x3249b  ldloc.s  7
0x3249d  ldstr    aExternalpartye_1// "/ExternalPartyEntitiesCorrelationKeys/E"...
0x324a2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x324a7  stloc.s  8
0x324a9  ldloc.s  8
0x324ab  brfalse  loc_32556
0x324b0  ldloc.s  8
0x324b2  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x324b7  stloc.s  9
0x324b9  br.s     loc_32533
0x324bb  ldloc.s  9
0x324bd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x324c2  castclass [System.Xml]System.Xml.XmlNode
0x324c7  stloc.s  0x12
0x324c9  ldloc.s  0x12
0x324cb  ldstr    aEntitylogicaln_0// "EntityLogicalName"
0x324d0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x324d5  stloc.s  0x13
0x324d7  ldloc.s  0x13
0x324d9  brfalse.s loc_32533
0x324db  ldloc.s  0x13
0x324dd  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x324e2  brfalse.s loc_32533
0x324e4  ldloc.s  0x13
0x324e6  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x324eb  ldc.i4.0
0x324ec  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x324f1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x324f6  brfalse.s loc_32533
0x324f8  ldarg.1
0x324f9  ldloc.s  0x13
0x324fb  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x32500  ldc.i4.0
0x32501  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x32506  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x3250b  callvirt instance string [mscorlib]System.String::Trim()
0x32510  callvirt instance string [mscorlib]System.String::ToLower()
0x32515  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3251a  brfalse.s loc_32533
0x3251c  ldloc.s  7
0x3251e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x32523  ldc.i4.0
0x32524  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x32529  ldloc.s  0x12
0x3252b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x32530  pop
0x32531  ldc.i4.1
0x32532  stloc.0
0x32533  ldloc.s  9
0x32535  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3253a  brtrue   loc_324BB
0x3253f  leave.s  loc_32556
0x32541  ldloc.s  9
0x32543  isinst   [mscorlib]System.IDisposable
0x32548  stloc.s  0xF
0x3254a  ldloc.s  0xF
0x3254c  brfalse.s loc_32555
0x3254e  ldloc.s  0xF
0x32550  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32555  endfinally
0x32556  ldloc.0
0x32557  brfalse.s loc_32586
0x32559  ldloc.2
0x3255a  ldstr    aExternalpartye// "externalpartyentitysettings"
0x3255f  ldloc.s  5
0x32561  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x32566  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3256b  ldloc.2
0x3256c  ldstr    aExternalpartyc// "externalpartycorrelationkeys"
0x32571  ldloc.s  7
0x32573  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x32578  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3257d  ldloc.s  4
  ... truncated ...
```
