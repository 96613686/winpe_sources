# Microsoft.Crm.Sdk.SchemaHelper::BuildEnum

- ea: `0x6de0`
- end: `0x6e44`
- name: `Microsoft.Crm.Sdk.SchemaHelper::BuildEnum`
- size: `100`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7870`
- `0x7b70`
- `0x7df0`

## callees

- `0x6de0`

## string_xrefs

- `0x6e00`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0x6de0  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSimpleType::.ctor()
0x6de5  stloc.0
0x6de6  ldloc.0
0x6de7  ldarg.0
0x6de8  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaType::set_Name(string)
0x6ded  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeRestriction::.ctor()
0x6df2  stloc.1
0x6df3  ldloc.0
0x6df4  ldloc.1
0x6df5  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaSimpleType::set_Content(class [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeContent)
0x6dfa  ldloc.1
0x6dfb  ldstr    aString// "string"
0x6e00  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x6e05  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x6e0a  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeRestriction::set_BaseTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x6e0f  ldarg.1
0x6e10  stloc.2
0x6e11  ldc.i4.0
0x6e12  stloc.3
0x6e13  br.s     loc_6E3C
0x6e15  ldloc.2
0x6e16  ldloc.3
0x6e17  ldelem.ref
0x6e18  stloc.s  4
0x6e1a  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaEnumerationFacet::.ctor()
0x6e1f  stloc.s  5
0x6e21  ldloc.1
0x6e22  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_Facets()
0x6e27  ldloc.s  5
0x6e29  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x6e2e  pop
0x6e2f  ldloc.s  5
0x6e31  ldloc.s  4
0x6e33  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaFacet::set_Value(string)
0x6e38  ldloc.3
0x6e39  ldc.i4.1
0x6e3a  add
0x6e3b  stloc.3
0x6e3c  ldloc.3
0x6e3d  ldloc.2
0x6e3e  ldlen
0x6e3f  conv.i4
0x6e40  blt.s    loc_6E15
0x6e42  ldloc.0
0x6e43  ret
```
