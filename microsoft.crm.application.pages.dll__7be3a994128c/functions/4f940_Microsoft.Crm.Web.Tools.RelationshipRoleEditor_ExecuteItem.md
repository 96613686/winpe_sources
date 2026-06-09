# Microsoft.Crm.Web.Tools.RelationshipRoleEditor::ExecuteItem

- ea: `0x4f940`
- end: `0x4fa48`
- name: `Microsoft.Crm.Web.Tools.RelationshipRoleEditor::ExecuteItem`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x4f8d0`

## callees

- `0x4f940`
- `0x4fa50`

## string_xrefs

- `0x4f97e`: `DELETE`
- `0x4f971`: `CREATE`
- `0x4f990`: `dataxml`
- `0x4f9a9`: `dataxml`
- `0x4f99d`: `You must supply dataxml in the item node for a create action`
- `0x4f9fa`: `You must supply an object guid for the delete action`

## pseudocode

```c

```

## disassembly

```asm
0x4f940  ldstr    aRelationshipro_2// "relationshiprolemap"
0x4f945  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4f94a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4f94f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x4f954  stloc.0
0x4f955  ldarg.1
0x4f956  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4f95b  ldstr    aAction// "action"
0x4f960  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x4f965  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4f96a  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4f96f  stloc.1
0x4f970  ldloc.1
0x4f971  ldstr    aCreate_1// "CREATE"
0x4f976  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f97b  brtrue.s loc_4F98F
0x4f97d  ldloc.1
0x4f97e  ldstr    aDelete_0// "DELETE"
0x4f983  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f988  brtrue.s loc_4F9DA
0x4f98a  br       loc_4FA27
0x4f98f  ldarg.1
0x4f990  ldstr    aDataxml// "dataxml"
0x4f995  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x4f99a  ldnull
0x4f99b  cgt.un
0x4f99d  ldstr    aYouMustSupplyD// "You must supply dataxml in the item nod"...
0x4f9a2  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4f9a7  ldloc.0
0x4f9a8  ldarg.1
0x4f9a9  ldstr    aDataxml// "dataxml"
0x4f9ae  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x4f9b3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x4f9b8  ldstr    aRelationshipro_4// "<relationshiproleid>"
0x4f9bd  ldarg.2
0x4f9be  ldstr    aRelationshipro_5// "</relationshiproleid>"
0x4f9c3  call     string [mscorlib]System.String::Concat(string, string, string)
0x4f9c8  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendInnerXml(string, string)
0x4f9cd  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x4f9d2  ldloc.0
0x4f9d3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Create()
0x4f9d8  br.s     loc_4FA3C
0x4f9da  ldarg.0
0x4f9db  ldfld    bool Microsoft.Crm.Web.Tools.RelationshipRoleEditor::_isNew
0x4f9e0  brtrue.s loc_4FA3C
0x4f9e2  ldarg.1
0x4f9e3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4f9e8  ldstr    aId// "id"
0x4f9ed  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x4f9f2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4f9f7  ldnull
0x4f9f8  cgt.un
0x4f9fa  ldstr    aYouMustSupplyA// "You must supply an object guid for the "...
0x4f9ff  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4fa04  ldloc.0
0x4fa05  ldarg.1
0x4fa06  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4fa0b  ldstr    aId// "id"
0x4fa10  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x4fa15  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4fa1a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x4fa1f  ldloc.0
0x4fa20  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Delete()
0x4fa25  br.s     loc_4FA3C
0x4fa27  ldc.i4.0
0x4fa28  ldstr    aTheQueueItemAc// "The queue item action {0} is not a supp"...
0x4fa2d  ldc.i4.1
0x4fa2e  newarr   [mscorlib]System.Object
0x4fa33  dup
0x4fa34  ldc.i4.0
0x4fa35  ldloc.1
0x4fa36  stelem.ref
0x4fa37  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string, object[])
0x4fa3c  leave.s  loc_4FA47
0x4fa3e  pop
0x4fa3f  ldarg.0
0x4fa40  call     instance void Microsoft.Crm.Web.Tools.RelationshipRoleEditor::RecordError()
0x4fa45  leave.s  loc_4FA47
0x4fa47  ret
```
