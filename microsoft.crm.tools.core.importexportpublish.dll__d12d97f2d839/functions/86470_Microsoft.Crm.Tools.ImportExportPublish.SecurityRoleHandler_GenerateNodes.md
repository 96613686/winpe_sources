# Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::GenerateNodes

- ea: `0x86470`
- end: `0x8670e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::GenerateNodes`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x861e0`

## callees

- `0x391e0`
- `0x39940`
- `0x39ac0`
- `0x3a470`
- `0x86470`
- `0x86720`
- `0x96600`
- `0x96660`
- `0x966b0`

## string_xrefs

- `0x86559`: `securityRole`
- `0x864a9`: `privilegeid`
- `0x864d5`: `privilegeid`
- `0x86606`: `privilegeid`
- `0x8656f`: `RolePrivileges`
- `0x865d9`: `RolePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x86470  ldarg.s  4
0x86472  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::Clone()
0x86477  stloc.0
0x86478  ldarg.1
0x86479  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x8647e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::.ctor(int32)
0x86483  stloc.1
0x86484  ldc.i4.0
0x86485  stloc.2
0x86486  ldarg.1
0x86487  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x8648c  stloc.s  7
0x8648e  br       loc_86523
0x86493  ldloc.s  7
0x86495  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8649a  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x8649f  stloc.s  8
0x864a1  ldarg.0
0x864a2  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::privileges
0x864a7  ldloc.s  8
0x864a9  ldstr    aPrivilegeid// "privilegeid"
0x864ae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x864b3  unbox.any [mscorlib]System.Guid
0x864b8  stloc.s  9
0x864ba  ldloca.s 9
0x864bc  ldstr    aB// "B"
0x864c1  call     instance string [mscorlib]System.Guid::ToString(string)
0x864c6  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x864cb  brfalse.s loc_8651F
0x864cd  ldarg.0
0x864ce  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::privileges
0x864d3  ldloc.s  8
0x864d5  ldstr    aPrivilegeid// "privilegeid"
0x864da  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x864df  unbox.any [mscorlib]System.Guid
0x864e4  stloc.s  9
0x864e6  ldloca.s 9
0x864e8  ldstr    aB// "B"
0x864ed  call     instance string [mscorlib]System.Guid::ToString(string)
0x864f2  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x864f7  callvirt instance string [mscorlib]System.Object::ToString()
0x864fc  stloc.s  0xA
0x864fe  ldloc.s  0xA
0x86500  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x86505  ldstr    aPrvgomobile// "prvgomobile"
0x8650a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8650f  brtrue.s loc_86523
0x86511  ldloc.1
0x86512  ldloc.s  0xA
0x86514  ldloc.2
0x86515  newobj   instance void Item::.ctor(string key, int32 index)
0x8651a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::Add(var<u1>)
0x8651f  ldloc.2
0x86520  ldc.i4.1
0x86521  add
0x86522  stloc.2
0x86523  ldloc.s  7
0x86525  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8652a  brtrue   loc_86493
0x8652f  leave.s  loc_86546
0x86531  ldloc.s  7
0x86533  isinst   [mscorlib]System.IDisposable
0x86538  stloc.s  0xB
0x8653a  ldloc.s  0xB
0x8653c  brfalse.s loc_86545
0x8653e  ldloc.s  0xB
0x86540  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x86545  endfinally
0x86546  ldarg.s  5
0x86548  ldstr    aIsmanaged// "ismanaged"
0x8654d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x86552  unbox.any [mscorlib]System.Boolean
0x86557  stloc.3
0x86558  ldarg.0
0x86559  ldstr    aSecurityrole// "securityRole"
0x8655e  ldarg.2
0x8655f  ldarg.s  4
0x86561  ldarg.s  5
0x86563  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x86568  ldloc.3
0x86569  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x8656e  ldarg.2
0x8656f  ldstr    aRoleprivileges// "RolePrivileges"
0x86574  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x86579  stloc.s  4
0x8657b  ldarg.s  4
0x8657d  ldloc.s  4
0x8657f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x86584  pop
0x86585  ldc.i4.0
0x86586  stloc.s  5
0x86588  ldloc.1
0x86589  newobj   instance void ListComparer::.ctor()
0x8658e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::Sort(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x86593  ldloc.1
0x86594  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Item>::GetEnumerator()
0x86599  stloc.s  0xC
0x8659b  br       loc_86657
0x865a0  ldloca.s 0xC
0x865a2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>::get_Current()
0x865a7  stloc.s  0xD
0x865a9  ldarg.1
0x865aa  ldloc.s  0xD
0x865ac  callvirt instance int32 Item::get_Index()
0x865b1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x865b6  stloc.s  0xE
0x865b8  ldloc.s  0xE
0x865ba  ldstr    aSolutionid// "solutionid"
0x865bf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x865c4  unbox.any [mscorlib]System.Guid
0x865c9  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x865ce  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x865d3  brfalse.s loc_865D8
0x865d5  ldc.i4.1
0x865d6  stloc.s  5
0x865d8  ldarg.2
0x865d9  ldstr    aRoleprivilege// "RolePrivilege"
0x865de  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x865e3  stloc.s  0xF
0x865e5  ldarg.3
0x865e6  ldarg.0
0x865e7  ldloc.s  0xE
0x865e9  call     instance int32 Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::GetDepthMask(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity rolePrivilege)
0x865ee  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::GetDepth(int32)
0x865f3  stloc.s  0x10
0x865f5  ldarg.0
0x865f6  ldarg.2
0x865f7  ldloc.s  0xF
0x865f9  ldstr    aName// "name"
0x865fe  ldarg.0
0x865ff  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::privileges
0x86604  ldloc.s  0xE
0x86606  ldstr    aPrivilegeid// "privilegeid"
0x8660b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x86610  unbox.any [mscorlib]System.Guid
0x86615  stloc.s  9
0x86617  ldloca.s 9
0x86619  ldstr    aB// "B"
0x8661e  call     instance string [mscorlib]System.Guid::ToString(string)
0x86623  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x86628  callvirt instance string [mscorlib]System.Object::ToString()
0x8662d  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributeNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x86632  ldarg.0
0x86633  ldarg.2
0x86634  ldloc.s  0xF
0x86636  ldstr    aLevel// "level"
0x8663b  ldloca.s 0x10
0x8663d  constrained. [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth
0x86643  callvirt instance string [mscorlib]System.Object::ToString()
0x86648  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributeNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x8664d  ldloc.s  4
0x8664f  ldloc.s  0xF
0x86651  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x86656  pop
0x86657  ldloca.s 0xC
0x86659  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>::MoveNext()
0x8665e  brtrue   loc_865A0
0x86663  leave.s  loc_86673
0x86665  ldloca.s 0xC
0x86667  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>
0x8666d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x86672  endfinally
0x86673  ldarg.2
0x86674  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x86679  ldstr    aRoles// "Roles"
0x8667e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x86683  stloc.s  6
0x86685  ldloc.s  5
0x86687  brtrue.s loc_866AE
0x86689  ldarg.s  5
0x8668b  ldstr    aSolutionid// "solutionid"
0x86690  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x86695  unbox.any [mscorlib]System.Guid
0x8669a  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x8669f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x866a4  brtrue.s loc_866AE
0x866a6  ldarg.0
0x866a7  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x866ac  brfalse.s loc_866B9
0x866ae  ldloc.s  6
0x866b0  ldarg.s  4
0x866b2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x866b7  pop
0x866b8  ret
0x866b9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x866be  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x866c3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SolutionSegmentation()
0x866c8  ldarg.0
0x866c9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::exc
0x866ce  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x866d3  brfalse.s loc_8670D
0x866d5  ldarg.2
0x866d6  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::IsSolutionUnmanaged(class [System.Xml]System.Xml.XmlDocument importDocument)
0x866db  brfalse.s loc_8670D
0x866dd  ldarg.2
0x866de  ldstr    aUnmodified// "unmodified"
0x866e3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x866e8  stloc.s  0x11
0x866ea  ldloc.s  0x11
0x866ec  ldstr    a1// "1"
0x866f1  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x866f6  ldloc.0
0x866f7  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x866fc  ldloc.s  0x11
0x866fe  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x86703  pop
0x86704  ldloc.s  6
0x86706  ldloc.0
0x86707  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x8670c  pop
0x8670d  ret
```
