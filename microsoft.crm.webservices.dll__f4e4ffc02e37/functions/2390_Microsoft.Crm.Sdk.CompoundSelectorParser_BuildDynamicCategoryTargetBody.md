# Microsoft.Crm.Sdk.CompoundSelectorParser::BuildDynamicCategoryTargetBody

- ea: `0x2390`
- end: `0x240d`
- name: `Microsoft.Crm.Sdk.CompoundSelectorParser::BuildDynamicCategoryTargetBody`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6ba0`
- `0x6e50`

## pseudocode

```c

```

## disassembly

```asm
0x2390  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSequence::.ctor()
0x2395  stloc.0
0x2396  ldarg.3
0x2397  ldloc.0
0x2398  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::set_Particle(class [System.Xml]System.Xml.Schema.XmlSchemaParticle)
0x239d  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x23a2  stloc.1
0x23a3  ldloc.0
0x23a4  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x23a9  ldloc.1
0x23aa  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x23af  pop
0x23b0  ldloc.1
0x23b1  ldstr    aEntity// "Entity"
0x23b6  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x23bb  ldloc.1
0x23bc  ldarg.s  4
0x23be  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x23c3  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x23c8  stloc.2
0x23c9  ldloc.0
0x23ca  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x23cf  ldloc.2
0x23d0  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x23d5  pop
0x23d6  ldarg.s  4
0x23d8  ldloca.s 3
0x23da  call     class [System.Xml]System.Xml.Schema.XmlSchemaComplexType Microsoft.Crm.Sdk.SchemaHelper::BuildArrayOf(class [System.Xml]System.Xml.XmlQualifiedName elementName, [out] string& arrayTypeName)
0x23df  stloc.s  4
0x23e1  ldarg.2
0x23e2  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Items()
0x23e7  ldloc.s  4
0x23e9  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x23ee  pop
0x23ef  ldloc.2
0x23f0  ldstr    aChildentities// "ChildEntities"
0x23f5  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x23fa  ldloc.2
0x23fb  ldloc.3
0x23fc  ldarg.1
0x23fd  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0x2402  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x2407  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x240c  ret
```
