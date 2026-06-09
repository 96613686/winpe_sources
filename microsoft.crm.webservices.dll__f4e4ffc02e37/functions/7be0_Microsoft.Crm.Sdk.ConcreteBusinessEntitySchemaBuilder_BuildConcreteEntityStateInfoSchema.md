# Microsoft.Crm.Sdk.ConcreteBusinessEntitySchemaBuilder::BuildConcreteEntityStateInfoSchema

- ea: `0x7be0`
- end: `0x7c82`
- name: `Microsoft.Crm.Sdk.ConcreteBusinessEntitySchemaBuilder::BuildConcreteEntityStateInfoSchema`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7c90`

## callees

- `0x6ba0`

## string_xrefs

- `0x7c5f`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0x7be0  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchema::.ctor()
0x7be5  dup
0x7be6  ldarg.0
0x7be7  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0x7bec  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchema::set_TargetNamespace(string)
0x7bf1  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexType::.ctor()
0x7bf6  stloc.0
0x7bf7  ldloc.0
0x7bf8  ldarg.1
0x7bf9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x7bfe  ldstr    aStateinfo// "StateInfo"
0x7c03  call     string [mscorlib]System.String::Concat(string, string)
0x7c08  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaType::set_Name(string)
0x7c0d  dup
0x7c0e  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Items()
0x7c13  ldloc.0
0x7c14  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x7c19  pop
0x7c1a  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSimpleContent::.ctor()
0x7c1f  stloc.1
0x7c20  ldloc.0
0x7c21  ldloc.1
0x7c22  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexType::set_ContentModel(class [System.Xml]System.Xml.Schema.XmlSchemaContentModel)
0x7c27  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSimpleContentExtension::.ctor()
0x7c2c  stloc.2
0x7c2d  ldloc.1
0x7c2e  ldloc.2
0x7c2f  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaContentModel::set_Content(class [System.Xml]System.Xml.Schema.XmlSchemaContent)
0x7c34  ldloc.2
0x7c35  ldarg.2
0x7c36  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaSimpleContentExtension::set_BaseTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x7c3b  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaAttribute::.ctor()
0x7c40  stloc.3
0x7c41  ldloc.2
0x7c42  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaSimpleContentExtension::get_Attributes()
0x7c47  ldloc.3
0x7c48  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x7c4d  pop
0x7c4e  ldloc.3
0x7c4f  ldstr    aFormattedvalue// "formattedvalue"
0x7c54  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaAttribute::set_Name(string)
0x7c59  ldloc.3
0x7c5a  ldstr    aString// "string"
0x7c5f  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7c64  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x7c69  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaAttribute::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x7c6e  ldarg.3
0x7c6f  ldloc.0
0x7c70  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaType::get_Name()
0x7c75  ldarg.0
0x7c76  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0x7c7b  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x7c80  stind.ref
0x7c81  ret
```
