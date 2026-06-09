# Microsoft.Crm.Sdk.MonikerSelectorParser::BuildDynamic_0

- ea: `0x1ff0`
- end: `0x2027`
- name: `Microsoft.Crm.Sdk.MonikerSelectorParser::BuildDynamic_0`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1fd0`
- `0x2080`
- `0x2a50`

## callees

- `0x1fa0`

## string_xrefs

- `0x2010`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0x1ff0  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x1ff5  stloc.0
0x1ff6  ldarg.0
0x1ff7  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x1ffc  ldloc.0
0x1ffd  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x2002  pop
0x2003  ldloc.0
0x2004  ldarg.2
0x2005  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x200a  ldloc.0
0x200b  ldstr    aString// "string"
0x2010  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x2015  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x201a  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x201f  ldarg.0
0x2020  ldarg.1
0x2021  call     void Microsoft.Crm.Sdk.MonikerSelectorParser::BuildConcrete(class [System.Xml]System.Xml.Schema.XmlSchemaGroupBase sequence, string idFieldName)
0x2026  ret
```
