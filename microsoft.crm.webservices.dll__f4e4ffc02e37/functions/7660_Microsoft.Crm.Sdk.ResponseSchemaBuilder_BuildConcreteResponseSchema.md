# Microsoft.Crm.Sdk.ResponseSchemaBuilder::BuildConcreteResponseSchema

- ea: `0x7660`
- end: `0x77af`
- name: `Microsoft.Crm.Sdk.ResponseSchemaBuilder::BuildConcreteResponseSchema`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x75b0`

## callees

- `0x6420`
- `0x6450`
- `0x6540`
- `0x6590`
- `0x6910`
- `0x6ba0`
- `0x6da0`
- `0x7660`

## string_xrefs

- `0x776e`: `http://schemas.microsoft.com/crm/2006/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x7660  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchema::.ctor()
0x7665  stloc.0
0x7666  ldarg.1
0x7667  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0x766c  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SdkSerializationCommon::GetBusinessEntityNamespace(string)
0x7671  stloc.1
0x7672  ldloc.0
0x7673  ldloc.1
0x7674  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchema::set_TargetNamespace(string)
0x7679  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexType::.ctor()
0x767e  stloc.2
0x767f  ldloc.2
0x7680  ldarg.3
0x7681  callvirt instance string Microsoft.Crm.Sdk.ResponseDescription::get_Name()
0x7686  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaType::set_Name(string)
0x768b  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContent::.ctor()
0x7690  stloc.3
0x7691  ldloc.2
0x7692  ldloc.3
0x7693  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexType::set_ContentModel(class [System.Xml]System.Xml.Schema.XmlSchemaContentModel)
0x7698  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::.ctor()
0x769d  stloc.s  4
0x769f  ldloc.3
0x76a0  ldloc.s  4
0x76a2  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaContentModel::set_Content(class [System.Xml]System.Xml.Schema.XmlSchemaContent)
0x76a7  ldloc.s  4
0x76a9  ldarg.2
0x76aa  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::set_BaseTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x76af  ldarg.3
0x76b0  callvirt instance class Microsoft.Crm.Sdk.ResponseFieldDescription[] Microsoft.Crm.Sdk.ResponseDescription::get_Fields()
0x76b5  ldlen
0x76b6  brfalse  loc_77A6
0x76bb  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSequence::.ctor()
0x76c0  stloc.s  5
0x76c2  ldloc.s  4
0x76c4  ldloc.s  5
0x76c6  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::set_Particle(class [System.Xml]System.Xml.Schema.XmlSchemaParticle)
0x76cb  ldc.i4.0
0x76cc  stloc.s  6
0x76ce  br       loc_7797
0x76d3  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x76d8  stloc.s  7
0x76da  ldloc.s  5
0x76dc  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x76e1  ldloc.s  7
0x76e3  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x76e8  pop
0x76e9  ldarg.3
0x76ea  callvirt instance class Microsoft.Crm.Sdk.ResponseFieldDescription[] Microsoft.Crm.Sdk.ResponseDescription::get_Fields()
0x76ef  ldloc.s  6
0x76f1  ldelem.ref
0x76f2  callvirt instance class Microsoft.Crm.Sdk.IFieldFormatter Microsoft.Crm.Sdk.ResponseFieldDescription::get_Formatter()
0x76f7  ldarg.1
0x76f8  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName Microsoft.Crm.Sdk.ISchemaBuilder::BuildSchema(class Microsoft.Crm.Sdk.SchemaContext context)
0x76fd  stloc.s  8
0x76ff  ldarg.3
0x7700  callvirt instance class Microsoft.Crm.Sdk.ResponseFieldDescription[] Microsoft.Crm.Sdk.ResponseDescription::get_Fields()
0x7705  ldloc.s  6
0x7707  ldelem.ref
0x7708  callvirt instance string Microsoft.Crm.Sdk.ResponseFieldDescription::get_PublicName()
0x770d  stloc.s  9
0x770f  ldloc.s  8
0x7711  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x7716  ldstr    aBusinessentity// "BusinessEntity"
0x771b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7720  brtrue.s loc_7735
0x7722  ldloc.s  8
0x7724  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x7729  ldstr    aBusinessentity_1// "BusinessEntityCollection"
0x772e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7733  brfalse.s loc_777F
0x7735  ldarg.1
0x7736  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0x773b  ldloc.1
0x773c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7741  brfalse.s loc_777F
0x7743  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x7748  stloc.s  0xA
0x774a  ldloc.s  0xA
0x774c  ldloc.s  9
0x774e  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x7753  ldloc.s  0xA
0x7755  ldloc.s  8
0x7757  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x775c  ldloc.0
0x775d  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Items()
0x7762  ldloc.s  0xA
0x7764  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x7769  pop
0x776a  ldloc.s  7
0x776c  ldloc.s  9
0x776e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0x7773  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x7778  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_RefName(class [System.Xml]System.Xml.XmlQualifiedName)
0x777d  br.s     loc_7791
0x777f  ldloc.s  7
0x7781  ldloc.s  9
0x7783  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x7788  ldloc.s  7
0x778a  ldloc.s  8
0x778c  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x7791  ldloc.s  6
0x7793  ldc.i4.1
0x7794  add
0x7795  stloc.s  6
0x7797  ldloc.s  6
0x7799  ldarg.3
0x779a  callvirt instance class Microsoft.Crm.Sdk.ResponseFieldDescription[] Microsoft.Crm.Sdk.ResponseDescription::get_Fields()
0x779f  ldlen
0x77a0  conv.i4
0x77a1  blt      loc_76D3
0x77a6  ldarg.1
0x77a7  ldloc.0
0x77a8  callvirt instance void Microsoft.Crm.Sdk.SchemaContext::AddSchema(class [System.Xml]System.Xml.Schema.XmlSchema newSchema)
0x77ad  ldloc.2
0x77ae  ret
```
