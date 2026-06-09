# Microsoft.Crm.Sdk.CompoundSelectorParser::BuildConcreteCategoryTargetBody

- ea: `0x22c0`
- end: `0x2384`
- name: `Microsoft.Crm.Sdk.CompoundSelectorParser::BuildConcreteCategoryTargetBody`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x2410`
- `0x6b60`
- `0x6ba0`
- `0x6e50`
- `0x86a0`

## pseudocode

```c

```

## disassembly

```asm
0x22c0  ldarg.0
0x22c1  ldarg.s  4
0x22c3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x22c8  call     instance string Microsoft.Crm.Sdk.CompoundSelectorParser::GetSubEntityName(string parentEntityPlatformName)
0x22cd  stloc.0
0x22ce  ldarg.1
0x22cf  callvirt instance class Microsoft.Crm.Sdk.ServiceDescription Microsoft.Crm.Sdk.SchemaContext::get_ServiceDescription()
0x22d4  ldloc.0
0x22d5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Sdk.ServiceDescription::GetEntityByEntityName(string entityName)
0x22da  stloc.1
0x22db  ldloc.1
0x22dc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x22e1  ldarg.1
0x22e2  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0x22e7  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x22ec  ldloca.s 2
0x22ee  call     class [System.Xml]System.Xml.Schema.XmlSchemaComplexType Microsoft.Crm.Sdk.SchemaHelper::BuildArrayOf(class [System.Xml]System.Xml.XmlQualifiedName elementName, [out] string& arrayTypeName)
0x22f3  stloc.3
0x22f4  ldarg.2
0x22f5  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Items()
0x22fa  ldloc.3
0x22fb  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x2300  pop
0x2301  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSequence::.ctor()
0x2306  stloc.s  4
0x2308  ldarg.3
0x2309  ldloc.s  4
0x230b  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::set_Particle(class [System.Xml]System.Xml.Schema.XmlSchemaParticle)
0x2310  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x2315  stloc.s  5
0x2317  ldloc.s  4
0x2319  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x231e  ldloc.s  5
0x2320  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x2325  pop
0x2326  ldloc.s  5
0x2328  ldarg.s  4
0x232a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x232f  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x2334  ldloc.s  5
0x2336  ldarg.s  4
0x2338  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x233d  ldarg.1
0x233e  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0x2343  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x2348  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x234d  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x2352  stloc.s  6
0x2354  ldloc.s  4
0x2356  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x235b  ldloc.s  6
0x235d  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x2362  pop
0x2363  ldloc.s  6
0x2365  ldloc.1
0x2366  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CollectionName()
0x236b  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x2370  ldloc.s  6
0x2372  ldloc.2
0x2373  ldarg.1
0x2374  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0x2379  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x237e  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x2383  ret
```
