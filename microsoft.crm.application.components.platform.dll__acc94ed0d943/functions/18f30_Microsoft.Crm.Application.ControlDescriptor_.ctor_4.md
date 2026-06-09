# Microsoft.Crm.Application.ControlDescriptor::.ctor_4

- ea: `0x18f30`
- end: `0x19067`
- name: `Microsoft.Crm.Application.ControlDescriptor::.ctor_4`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x170a0`

## callees

- `0x115b0`
- `0x18d90`
- `0x18f30`
- `0x193c0`
- `0x19680`
- `0x1b320`
- `0x1f780`

## string_xrefs

- `0x18f58`: `classid`
- `0x18f87`: `Control does not have an ID. Control's Outer Xml: `

## pseudocode

```c

```

## disassembly

```asm
0x18f30  ldarg.0
0x18f31  ldarg.1
0x18f32  ldstr    aId// "id"
0x18f37  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x18f3c  ldarg.1
0x18f3d  ldstr    aLabelid// "labelid"
0x18f42  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x18f47  ldarg.1
0x18f48  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_PreviousSibling()
0x18f4d  ldstr    aDescription_0// "description"
0x18f52  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x18f57  ldarg.1
0x18f58  ldstr    aClassid// "classid"
0x18f5d  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x18f62  ldarg.1
0x18f63  ldstr    aDatafieldname// "datafieldname"
0x18f68  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x18f6d  ldarg.2
0x18f6e  ldarg.3
0x18f6f  call     instance void Microsoft.Crm.Application.ControlDescriptor::.ctor(string id, string labelId, string controlLabel, string classId, string dataFieldName, string entityLogicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x18f74  ldarg.1
0x18f75  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x18f7a  ldstr    aId// "id"
0x18f7f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x18f84  ldnull
0x18f85  cgt.un
0x18f87  ldstr    aControlDoesNot// "Control does not have an ID. Control's "...
0x18f8c  ldarg.1
0x18f8d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x18f92  call     string [mscorlib]System.String::Concat(string, string)
0x18f97  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x18f9c  ldarg.0
0x18f9d  ldarg.1
0x18f9e  ldarg.3
0x18f9f  call     instance void Microsoft.Crm.Application.ControlDescriptor::GetControlParameters(class [System.Xml]System.Xml.XmlNode formNode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x18fa4  ldarg.0
0x18fa5  ldarg.1
0x18fa6  ldstr    aEventsEvent// "../events/event"
0x18fab  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x18fb0  ldnull
0x18fb1  newobj   instance void Microsoft.Crm.Application.EventCollections::.ctor(class [System.Xml]System.Xml.XmlNodeList nodes, class Microsoft.Crm.Application.FormDescriptor formDescriptor)
0x18fb6  stfld    class Microsoft.Crm.Application.EventCollections Microsoft.Crm.Application.ControlDescriptor::_events
0x18fbb  ldarg.0
0x18fbc  ldarg.1
0x18fbd  ldstr    aIsunbound// "isunbound"
0x18fc2  ldc.i4.0
0x18fc3  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x18fc8  stfld    bool Microsoft.Crm.Application.ControlDescriptor::_isUnbound
0x18fcd  ldarg.0
0x18fce  ldarg.1
0x18fcf  ldstr    aIsrequired// "isrequired"
0x18fd4  ldc.i4.0
0x18fd5  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x18fda  stfld    bool Microsoft.Crm.Application.ControlDescriptor::_isRequired
0x18fdf  ldarg.1
0x18fe0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x18fe5  brfalse.s loc_1900D
0x18fe7  ldarg.1
0x18fe8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x18fed  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x18ff2  brfalse.s loc_1900D
0x18ff4  ldarg.0
0x18ff5  ldarg.1
0x18ff6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x18ffb  ldstr    aVisible// "visible"
0x19000  ldc.i4.1
0x19001  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x19006  stfld    bool Microsoft.Crm.Application.ControlDescriptor::_visible
0x1900b  br.s     loc_1901F
0x1900d  ldarg.0
0x1900e  ldarg.1
0x1900f  ldstr    aVisible// "visible"
0x19014  ldc.i4.1
0x19015  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x1901a  stfld    bool Microsoft.Crm.Application.ControlDescriptor::_visible
0x1901f  ldarg.0
0x19020  ldfld    string Microsoft.Crm.Application.ControlDescriptor::_classId
0x19025  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1902a  ldstr    a00ad73daBd4d49// "{00AD73DA-BD4D-49C6-88A8-2F4F4CAD4A20}"
0x1902f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x19034  brfalse.s loc_19066
0x19036  ldarg.0
0x19037  ldfld    bool Microsoft.Crm.Application.ControlDescriptor::_isUnbound
0x1903c  brfalse.s loc_1904B
0x1903e  ldarg.0
0x1903f  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_DataFieldName()
0x19044  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19049  br.s     loc_1904C
0x1904b  ldc.i4.1
0x1904c  ldstr    aControlWithId// "Control with id: "
0x19051  ldarg.0
0x19052  call     instance string Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_Id()
0x19057  ldstr    aCannotHaveData// " cannot have datafieldname and isunboun"...
0x1905c  call     string [mscorlib]System.String::Concat(string, string, string)
0x19061  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x19066  ret
```
