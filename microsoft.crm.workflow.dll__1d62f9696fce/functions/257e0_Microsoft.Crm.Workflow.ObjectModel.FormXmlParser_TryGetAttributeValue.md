# Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::TryGetAttributeValue

- ea: `0x257e0`
- end: `0x2580b`
- name: `Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::TryGetAttributeValue`
- size: `43`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x25220`
- `0x253d0`
- `0x256c0`
- `0x25700`
- `0x25750`
- `0x25790`
- `0x257b0`

## callees

- `0x257e0`

## pseudocode

```c

```

## disassembly

```asm
0x257e0  ldarg.1
0x257e1  brtrue.s loc_257E9
0x257e3  ldsfld   string [mscorlib]System.String::Empty
0x257e8  ret
0x257e9  ldarg.1
0x257ea  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x257ef  ldarg.2
0x257f0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x257f5  stloc.0
0x257f6  ldloc.0
0x257f7  brfalse.s loc_25805
0x257f9  ldloc.0
0x257fa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x257ff  callvirt instance string [mscorlib]System.String::Trim()
0x25804  ret
0x25805  ldsfld   string [mscorlib]System.String::Empty
0x2580a  ret
```
