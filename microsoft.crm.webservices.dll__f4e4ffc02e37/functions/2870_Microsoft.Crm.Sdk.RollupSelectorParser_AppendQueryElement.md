# Microsoft.Crm.Sdk.RollupSelectorParser::AppendQueryElement

- ea: `0x2870`
- end: `0x28a4`
- name: `Microsoft.Crm.Sdk.RollupSelectorParser::AppendQueryElement`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2820`
- `0x2850`

## string_xrefs

- `0x2894`: `http://schemas.microsoft.com/crm/2006/Query`

## pseudocode

```c

```

## disassembly

```asm
0x2870  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x2875  stloc.0
0x2876  ldarg.1
0x2877  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x287c  ldloc.0
0x287d  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x2882  pop
0x2883  ldloc.0
0x2884  ldstr    aQuery// "Query"
0x2889  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x288e  ldloc.0
0x288f  ldstr    aQuerybase// "QueryBase"
0x2894  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/crm/2006/Q"...
0x2899  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x289e  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x28a3  ret
```
