# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipDataConverter::CanConvert

- ea: `0xa4c0`
- end: `0xa525`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipDataConverter::CanConvert`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xaf20`

## callees

- `0xa4c0`

## pseudocode

```c

```

## disassembly

```asm
0xa4c0  ldarg.0
0xa4c1  ldstr    aType// "type"
0xa4c6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xa4cb  stloc.0
0xa4cc  ldloc.0
0xa4cd  brfalse.s loc_A523
0xa4cf  ldloc.0
0xa4d0  ldstr    aName// "name"
0xa4d5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xa4da  brfalse.s loc_A523
0xa4dc  ldloc.0
0xa4dd  ldstr    aName// "name"
0xa4e2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xa4e7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa4ec  ldstr    aLookup// "lookup"
0xa4f1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4f6  brtrue.s loc_A514
0xa4f8  ldloc.0
0xa4f9  ldstr    aName// "name"
0xa4fe  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xa503  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa508  ldstr    aCustomer// "customer"
0xa50d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa512  brfalse.s loc_A523
0xa514  ldloc.0
0xa515  ldstr    aRelationship// "relationship"
0xa51a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xa51f  brfalse.s loc_A523
0xa521  ldc.i4.1
0xa522  ret
0xa523  ldc.i4.0
0xa524  ret
```
