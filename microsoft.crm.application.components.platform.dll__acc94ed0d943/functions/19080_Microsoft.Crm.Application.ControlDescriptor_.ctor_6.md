# Microsoft.Crm.Application.ControlDescriptor::.ctor_6

- ea: `0x19080`
- end: `0x193b2`
- name: `Microsoft.Crm.Application.ControlDescriptor::.ctor_6`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x171d0`
- `0x19070`

## callees

- `0x11590`
- `0x115b0`
- `0x19080`
- `0x193c0`
- `0x19620`
- `0x19680`
- `0x19690`
- `0x196c0`
- `0x196e0`
- `0x19720`
- `0x19840`
- `0x1b260`
- `0x1b320`
- `0x1b6a0`
- `0x1c0e0`
- `0x1f6a0`
- `0x1f730`
- `0x1f780`
- `0x1f790`
- `0x4b9e0`

## string_xrefs

- `0x190f8`: `classid`
- `0x19144`: `classid`
- `0x19105`: `ClassId is not set on the following control: `

## pseudocode

```c

```

## disassembly

```asm
0x19080  ldarg.0
0x19081  ldc.i4.m1
0x19082  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.FormControlType Microsoft.Crm.Application.ControlDescriptor::_controlType
0x19087  ldarg.0
0x19088  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1908d  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.ControlDescriptor::_labelid
0x19092  ldarg.0
0x19093  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19098  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.ControlDescriptor::_uniqueId
0x1909d  ldarg.0
0x1909e  ldc.i4.1
0x1909f  stfld    bool Microsoft.Crm.Application.ControlDescriptor::_visible
0x190a4  ldarg.0
0x190a5  ldsfld   string [mscorlib]System.String::Empty
0x190aa  stfld    string Microsoft.Crm.Application.ControlDescriptor::_portalDomain
0x190af  ldarg.0
0x190b0  ldarg.1
0x190b1  ldstr    aLabelsLabel// "labels/label"
0x190b6  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x190bb  newobj   instance void Microsoft.Crm.Application.LabelCollection::.ctor(class [System.Xml]System.Xml.XmlNodeList nodes)
0x190c0  ldc.i4.1
0x190c1  ldarg.1
0x190c2  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormPartWithLabelDescriptor::GetLabelIdFromControlNode(class [System.Xml]System.Xml.XmlNode formXmlControlNode)
0x190c7  ldarg.s  5
0x190c9  ldarg.s  6
0x190cb  call     instance void Microsoft.Crm.Application.FormPartWithLabelDescriptor::.ctor(class Microsoft.Crm.Application.LabelCollection labels, bool canHaveMultipleLabels, valuetype [mscorlib]System.Guid labelId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [opt] bool insertUserLabel)
0x190d0  ldarg.0
0x190d1  ldarg.s  5
0x190d3  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.ControlDescriptor::_context
0x190d8  ldarg.0
0x190d9  ldarg.0
0x190da  ldarg.1
0x190db  ldarg.3
0x190dc  call     instance string Microsoft.Crm.Application.ControlDescriptor::GetControlId(class [System.Xml]System.Xml.XmlNode controlNode, class Microsoft.Crm.Application.FormDescriptor formDescriptor)
0x190e1  call     instance void Microsoft.Crm.Application.FormPartWithLabelDescriptor::set_Id(string value)
0x190e6  ldarg.0
0x190e7  ldarg.0
0x190e8  call     instance string Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_Id()
0x190ed  call     instance void Microsoft.Crm.Application.ControlDescriptor::set_ID(string value)
0x190f2  ldarg.1
0x190f3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x190f8  ldstr    aClassid// "classid"
0x190fd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x19102  ldnull
0x19103  cgt.un
0x19105  ldstr    aClassidIsNotSe// "ClassId is not set on the following con"...
0x1910a  ldarg.0
0x1910b  call     instance string Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_Id()
0x19110  call     string [mscorlib]System.String::Concat(string, string)
0x19115  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x1911a  ldarg.1
0x1911b  ldstr    aLabelid// "labelid"
0x19120  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x19125  stloc.0
0x19126  ldloc.0
0x19127  brtrue.s loc_19136
0x19129  ldarg.0
0x1912a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1912f  call     instance void Microsoft.Crm.Application.ControlDescriptor::set_LabelId(valuetype [mscorlib]System.Guid value)
0x19134  br.s     loc_19142
0x19136  ldarg.0
0x19137  ldloc.0
0x19138  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1913d  call     instance void Microsoft.Crm.Application.ControlDescriptor::set_LabelId(valuetype [mscorlib]System.Guid value)
0x19142  ldarg.0
0x19143  ldarg.1
0x19144  ldstr    aClassid// "classid"
0x19149  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x1914e  stfld    string Microsoft.Crm.Application.ControlDescriptor::_classId
0x19153  ldarg.0
0x19154  ldarg.0
0x19155  ldfld    string Microsoft.Crm.Application.ControlDescriptor::_classId
0x1915a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1915f  call     valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.FormControlType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.FormControlClassId::GetControlType(valuetype [mscorlib]System.Guid)
0x19164  call     instance void Microsoft.Crm.Application.ControlDescriptor::set_ControlType(valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.FormControlType value)
0x19169  ldarg.0
0x1916a  ldarg.1
0x1916b  ldstr    aDisabled// "disabled"
0x19170  ldc.i4.0
0x19171  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x19176  stfld    bool Microsoft.Crm.Application.ControlDescriptor::_disabled
0x1917b  ldarg.0
0x1917c  ldarg.1
0x1917d  ldstr    aVisible// "visible"
0x19182  ldc.i4.1
0x19183  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x19188  stfld    bool Microsoft.Crm.Application.ControlDescriptor::_visible
0x1918d  ldarg.0
0x1918e  ldfld    bool Microsoft.Crm.Application.ControlDescriptor::_visible
0x19193  brfalse.s loc_191C1
0x19195  ldarg.1
0x19196  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x1919b  brfalse.s loc_191C1
0x1919d  ldarg.1
0x1919e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x191a3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x191a8  brfalse.s loc_191C1
0x191aa  ldarg.0
0x191ab  ldarg.1
0x191ac  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x191b1  ldstr    aVisible// "visible"
0x191b6  ldc.i4.1
0x191b7  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x191bc  stfld    bool Microsoft.Crm.Application.ControlDescriptor::_visible
0x191c1  ldarg.0
0x191c2  ldarg.1
0x191c3  ldstr    aIsunbound// "isunbound"
0x191c8  ldc.i4.0
0x191c9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x191ce  stfld    bool Microsoft.Crm.Application.ControlDescriptor::_isUnbound
0x191d3  ldarg.0
0x191d4  ldarg.1
0x191d5  ldstr    aIsrequired// "isrequired"
0x191da  ldc.i4.0
0x191db  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x191e0  stfld    bool Microsoft.Crm.Application.ControlDescriptor::_isRequired
0x191e5  ldarg.0
0x191e6  ldarg.s  4
0x191e8  stfld    class Microsoft.Crm.Application.CellDescriptor Microsoft.Crm.Application.ControlDescriptor::_parentCellDescriptor
0x191ed  ldarg.1
0x191ee  ldstr    aDatafieldname// "datafieldname"
0x191f3  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x191f8  stloc.1
0x191f9  ldarg.0
0x191fa  ldfld    string Microsoft.Crm.Application.ControlDescriptor::_classId
0x191ff  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x19204  ldstr    a00ad73daBd4d49// "{00AD73DA-BD4D-49C6-88A8-2F4F4CAD4A20}"
0x19209  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1920e  brtrue.s loc_19227
0x19210  ldarg.0
0x19211  ldfld    string Microsoft.Crm.Application.ControlDescriptor::_classId
0x19216  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1921b  ldstr    a39354e4a50154d// "{39354E4A-5015-4D74-8031-EA9EB73A1322}"
0x19220  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19225  brfalse.s loc_1925B
0x19227  ldarg.1
0x19228  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_PreviousSibling()
0x1922d  brfalse.s loc_1925B
0x1922f  ldarg.1
0x19230  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_PreviousSibling()
0x19235  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x1923a  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Parse(string)
0x1923f  stloc.3
0x19240  ldarg.0
0x19241  ldloc.3
0x19242  ldstr    aDescription_0// "description"
0x19247  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x1924c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x19251  call     string [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x19256  stfld    string Microsoft.Crm.Application.ControlDescriptor::_label
0x1925b  ldarg.1
0x1925c  ldstr    aUniqueid// "uniqueid"
0x19261  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x19266  stloc.2
0x19267  ldloc.2
0x19268  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1926d  brfalse.s loc_1927C
0x1926f  ldarg.0
0x19270  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19275  call     instance void Microsoft.Crm.Application.ControlDescriptor::set_UniqueId(valuetype [mscorlib]System.Guid value)
0x1927a  br.s     loc_19288
0x1927c  ldarg.0
0x1927d  ldloc.2
0x1927e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x19283  call     instance void Microsoft.Crm.Application.ControlDescriptor::set_UniqueId(valuetype [mscorlib]System.Guid value)
0x19288  ldarg.0
0x19289  ldfld    string Microsoft.Crm.Application.ControlDescriptor::_classId
0x1928e  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x19293  ldstr    a00ad73daBd4d49// "{00AD73DA-BD4D-49C6-88A8-2F4F4CAD4A20}"
0x19298  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1929d  brfalse  loc_19382
0x192a2  ldloc.1
0x192a3  brfalse  loc_19352
0x192a8  ldarg.2
0x192a9  brfalse  loc_19352
0x192ae  ldarg.0
0x192af  ldloc.1
0x192b0  call     instance void Microsoft.Crm.Application.ControlDescriptor::set_DataFieldName(string value)
0x192b5  ldarg.1
0x192b6  ldstr    aRelationship// "relationship"
0x192bb  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x192c0  stloc.s  4
0x192c2  ldloc.s  4
0x192c4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x192c9  brfalse.s loc_192F8
0x192cb  ldarg.2
0x192cc  ldloc.1
0x192cd  ldc.i4.1
0x192ce  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x192d3  ldnull
0x192d4  cgt.un
0x192d6  ldstr    aAttributemetad// "AttributeMetadata not found for datafie"...
0x192db  ldc.i4.1
0x192dc  newarr   [mscorlib]System.Object
0x192e1  dup
0x192e2  ldc.i4.0
0x192e3  ldloc.1
0x192e4  stelem.ref
0x192e5  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message, object[] args)
0x192ea  ldarg.0
0x192eb  ldarg.2
0x192ec  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x192f1  stfld    int32 Microsoft.Crm.Application.ControlDescriptor::_entityTypeCode
0x192f6  br.s     loc_19352
0x192f8  ldloc.s  4
0x192fa  ldarg.s  5
0x192fc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Application.Utility.FormDescriptorUtility::GetRelationship(string relationshipName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x19301  stloc.s  5
0x19303  ldloc.s  5
0x19305  ldnull
0x19306  cgt.un
0x19308  ldstr    aRelationshipNo// "Relationship not correct for datafieldn"...
0x1930d  ldc.i4.1
0x1930e  newarr   [mscorlib]System.Object
0x19313  dup
0x19314  ldc.i4.0
0x19315  ldloc.1
0x19316  stelem.ref
0x19317  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message, object[] args)
0x1931c  ldloc.s  5
0x1931e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x19323  stloc.s  6
0x19325  ldloc.s  6
0x19327  ldloc.1
0x19328  ldc.i4.1
0x19329  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1932e  ldnull
0x1932f  cgt.un
0x19331  ldstr    aAttributemetad// "AttributeMetadata not found for datafie"...
0x19336  ldc.i4.1
0x19337  newarr   [mscorlib]System.Object
0x1933c  dup
0x1933d  ldc.i4.0
0x1933e  ldloc.1
0x1933f  stelem.ref
0x19340  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message, object[] args)
0x19345  ldarg.0
0x19346  ldloc.s  6
0x19348  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1934d  stfld    int32 Microsoft.Crm.Application.ControlDescriptor::_entityTypeCode
0x19352  ldarg.0
0x19353  ldfld    bool Microsoft.Crm.Application.ControlDescriptor::_isUnbound
0x19358  brfalse.s loc_19367
0x1935a  ldarg.0
0x1935b  call     instance string Microsoft.Crm.Application.ControlDescriptor::get_DataFieldName()
0x19360  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19365  br.s     loc_19368
0x19367  ldc.i4.1
0x19368  ldstr    aControlWithId// "Control with id: "
0x1936d  ldarg.0
0x1936e  call     instance string Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_Id()
0x19373  ldstr    aCannotHaveData// " cannot have datafieldname and isunboun"...
0x19378  call     string [mscorlib]System.String::Concat(string, string, string)
0x1937d  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x19382  ldarg.0
0x19383  ldarg.1
0x19384  ldstr    aEventsEvent// "../events/event"
0x19389  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1938e  ldarg.3
0x1938f  newobj   instance void Microsoft.Crm.Application.EventCollections::.ctor(class [System.Xml]System.Xml.XmlNodeList nodes, class Microsoft.Crm.Application.FormDescriptor formDescriptor)
0x19394  stfld    class Microsoft.Crm.Application.EventCollections Microsoft.Crm.Application.ControlDescriptor::_events
0x19399  ldarg.0
0x1939a  ldarg.1
0x1939b  ldarg.s  5
0x1939d  call     instance void Microsoft.Crm.Application.ControlDescriptor::GetControlParameters(class [System.Xml]System.Xml.XmlNode formNode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x193a2  ldarg.3
0x193a3  brfalse.s loc_193B1
0x193a5  ldarg.3
0x193a6  callvirt instance class Microsoft.Crm.Application.ControlCollection Microsoft.Crm.Application.FormDescriptor::get_Controls()
0x193ab  ldarg.0
0x193ac  callvirt instance void Microsoft.Crm.Application.ControlCollection::Add(class Microsoft.Crm.Application.ControlDescriptor control)
0x193b1  ret
```
