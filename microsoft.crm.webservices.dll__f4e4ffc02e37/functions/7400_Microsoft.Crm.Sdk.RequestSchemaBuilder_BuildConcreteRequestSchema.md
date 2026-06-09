# Microsoft.Crm.Sdk.RequestSchemaBuilder::BuildConcreteRequestSchema

- ea: `0x7400`
- end: `0x7512`
- name: `Microsoft.Crm.Sdk.RequestSchemaBuilder::BuildConcreteRequestSchema`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x72c0`

## callees

- `0x5d40`
- `0x5d60`
- `0x5d70`
- `0x5f20`
- `0x5fb0`
- `0x5fc0`
- `0x65b0`
- `0x6da0`
- `0x7400`

## string_xrefs

- `0x74f9`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0x7400  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexType::.ctor()
0x7405  stloc.0
0x7406  ldloc.0
0x7407  ldarg.3
0x7408  callvirt instance string Microsoft.Crm.Sdk.RequestDescription::get_PublicName()
0x740d  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaType::set_Name(string)
0x7412  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContent::.ctor()
0x7417  stloc.1
0x7418  ldloc.0
0x7419  ldloc.1
0x741a  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexType::set_ContentModel(class [System.Xml]System.Xml.Schema.XmlSchemaContentModel)
0x741f  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::.ctor()
0x7424  stloc.2
0x7425  ldloc.1
0x7426  ldloc.2
0x7427  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaContentModel::set_Content(class [System.Xml]System.Xml.Schema.XmlSchemaContent)
0x742c  ldloc.2
0x742d  ldarg.2
0x742e  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::set_BaseTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x7433  ldarg.3
0x7434  callvirt instance class Microsoft.Crm.Sdk.RequestFieldDescription[] Microsoft.Crm.Sdk.RequestDescription::get_Fields()
0x7439  ldlen
0x743a  brfalse  loc_74C4
0x743f  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSequence::.ctor()
0x7444  stloc.3
0x7445  ldloc.2
0x7446  ldloc.3
0x7447  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::set_Particle(class [System.Xml]System.Xml.Schema.XmlSchemaParticle)
0x744c  ldc.i4.0
0x744d  stloc.s  4
0x744f  br.s     loc_74B8
0x7451  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x7456  stloc.s  5
0x7458  ldloc.3
0x7459  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x745e  ldloc.s  5
0x7460  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x7465  pop
0x7466  ldloc.s  5
0x7468  ldarg.3
0x7469  callvirt instance class Microsoft.Crm.Sdk.RequestFieldDescription[] Microsoft.Crm.Sdk.RequestDescription::get_Fields()
0x746e  ldloc.s  4
0x7470  ldelem.ref
0x7471  callvirt instance string Microsoft.Crm.Sdk.RequestFieldDescription::get_PublicName()
0x7476  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x747b  ldarg.3
0x747c  callvirt instance class Microsoft.Crm.Sdk.RequestFieldDescription[] Microsoft.Crm.Sdk.RequestDescription::get_Fields()
0x7481  ldloc.s  4
0x7483  ldelem.ref
0x7484  callvirt instance bool Microsoft.Crm.Sdk.RequestFieldDescription::get_Optional()
0x7489  brfalse.s loc_7493
0x748b  ldloc.s  5
0x748d  ldc.i4.1
0x748e  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_IsNillable(bool)
0x7493  ldarg.3
0x7494  callvirt instance class Microsoft.Crm.Sdk.RequestFieldDescription[] Microsoft.Crm.Sdk.RequestDescription::get_Fields()
0x7499  ldloc.s  4
0x749b  ldelem.ref
0x749c  callvirt instance class Microsoft.Crm.Sdk.IFieldParser Microsoft.Crm.Sdk.RequestFieldDescription::get_Parser()
0x74a1  stloc.s  6
0x74a3  ldloc.s  5
0x74a5  ldloc.s  6
0x74a7  ldarg.1
0x74a8  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName Microsoft.Crm.Sdk.ISchemaBuilder::BuildSchema(class Microsoft.Crm.Sdk.SchemaContext context)
0x74ad  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x74b2  ldloc.s  4
0x74b4  ldc.i4.1
0x74b5  add
0x74b6  stloc.s  4
0x74b8  ldloc.s  4
0x74ba  ldarg.3
0x74bb  callvirt instance class Microsoft.Crm.Sdk.RequestFieldDescription[] Microsoft.Crm.Sdk.RequestDescription::get_Fields()
0x74c0  ldlen
0x74c1  conv.i4
0x74c2  blt.s    loc_7451
0x74c4  ldarg.3
0x74c5  callvirt instance class Microsoft.Crm.Sdk.ResponseDescription Microsoft.Crm.Sdk.RequestDescription::get_ResponseDescription()
0x74ca  callvirt instance bool Microsoft.Crm.Sdk.ResponseDescription::get_SupportsDynamicEntities()
0x74cf  brfalse.s loc_7510
0x74d1  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaAttribute::.ctor()
0x74d6  stloc.s  7
0x74d8  ldloc.2
0x74d9  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::get_Attributes()
0x74de  ldloc.s  7
0x74e0  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x74e5  pop
0x74e6  ldloc.s  7
0x74e8  ldstr    aReturndynamice// "ReturnDynamicEntities"
0x74ed  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaAttribute::set_Name(string)
0x74f2  ldloc.s  7
0x74f4  ldstr    aBoolean// "boolean"
0x74f9  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x74fe  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x7503  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaAttribute::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x7508  ldloc.s  7
0x750a  ldc.i4.3
0x750b  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaAttribute::set_Use(valuetype [System.Xml]System.Xml.Schema.XmlSchemaUse)
0x7510  ldloc.0
0x7511  ret
```
