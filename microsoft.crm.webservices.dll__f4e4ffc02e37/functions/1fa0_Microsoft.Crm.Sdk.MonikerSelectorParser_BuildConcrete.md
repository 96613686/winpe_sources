# Microsoft.Crm.Sdk.MonikerSelectorParser::BuildConcrete

- ea: `0x1fa0`
- end: `0x1fd0`
- name: `Microsoft.Crm.Sdk.MonikerSelectorParser::BuildConcrete`
- size: `48`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1ff0`
- `0x2060`
- `0x2820`
- `0x2a10`

## string_xrefs

- `0x1fc0`: `http://microsoft.com/wsdl/types/`

## pseudocode

```c

```

## disassembly

```asm
0x1fa0  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x1fa5  stloc.0
0x1fa6  ldarg.0
0x1fa7  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x1fac  ldloc.0
0x1fad  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x1fb2  pop
0x1fb3  ldloc.0
0x1fb4  ldarg.1
0x1fb5  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x1fba  ldloc.0
0x1fbb  ldstr    aGuid// "guid"
0x1fc0  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x1fc5  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x1fca  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x1fcf  ret
```
