# Microsoft.Crm.Sdk.ConcreteBusinessEntitySchemaBuilder::BuildConcreteEntitySchema

- ea: `0x78f0`
- end: `0x7b13`
- name: `Microsoft.Crm.Sdk.ConcreteBusinessEntitySchemaBuilder::BuildConcreteEntitySchema`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x77d0`

## callees

- `0x420`
- `0x67b0`
- `0x6b90`
- `0x6ba0`
- `0x6da0`
- `0x6f50`
- `0x78f0`
- `0x7c90`
- `0x7f10`
- `0x8060`
- `0x10120`

## string_xrefs

- `0x7986`: `http://schemas.microsoft.com/crm/2006/WebServices`
- `0x7994`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x78f0  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexType::.ctor()
0x78f5  stloc.0
0x78f6  ldloc.0
0x78f7  ldarg.2
0x78f8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x78fd  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaType::set_Name(string)
0x7902  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x7907  ldc.i4.s 0x1A
0x7909  ldstr    aEntityBuilderE// "Entity Builder:  Entity Name:{0}"
0x790e  ldc.i4.1
0x790f  newarr   [mscorlib]System.Object
0x7914  dup
0x7915  ldc.i4.0
0x7916  ldarg.2
0x7917  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x791c  stelem.ref
0x791d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7922  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContent::.ctor()
0x7927  stloc.1
0x7928  ldloc.0
0x7929  ldloc.1
0x792a  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexType::set_ContentModel(class [System.Xml]System.Xml.Schema.XmlSchemaContentModel)
0x792f  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::.ctor()
0x7934  stloc.2
0x7935  ldloc.1
0x7936  ldloc.2
0x7937  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaContentModel::set_Content(class [System.Xml]System.Xml.Schema.XmlSchemaContent)
0x793c  ldloc.2
0x793d  ldarg.1
0x793e  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0x7943  call     class [mscorlib]System.Type Microsoft.Crm.Sdk.BusinessEntityFactory::GetBusinessEntityType(string typeNamespace)
0x7948  call     class Microsoft.Crm.Sdk.ISchemaBuilder Microsoft.Crm.Sdk.SchemaBuilderFactory::Create(class [mscorlib]System.Type type)
0x794d  ldarg.1
0x794e  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName Microsoft.Crm.Sdk.ISchemaBuilder::BuildSchema(class Microsoft.Crm.Sdk.SchemaContext context)
0x7953  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::set_BaseTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x7958  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSequence::.ctor()
0x795d  stloc.3
0x795e  ldloc.2
0x795f  ldloc.3
0x7960  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::set_Particle(class [System.Xml]System.Xml.Schema.XmlSchemaParticle)
0x7965  ldarg.2
0x7966  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x796b  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x7970  newobj   instance void Microsoft.Crm.Sdk.AttributeMetadataComparer::.ctor()
0x7975  call     class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Sdk.SchemaHelper::CreateSortedList(class [mscorlib]System.Collections.ICollection source, class [mscorlib]System.Collections.IComparer comparer)
0x797a  stloc.s  4
0x797c  ldarg.1
0x797d  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0x7982  stloc.s  6
0x7984  ldloc.s  6
0x7986  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0x798b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7990  brtrue.s loc_79A2
0x7992  ldloc.s  6
0x7994  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x7999  call     bool [mscorlib]System.String::op_Equality(string, string)
0x799e  brtrue.s loc_79AB
0x79a0  br.s     loc_79AB
0x79a2  ldsfld   class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EndpointVersionProvider::CrmSdk2006Version
0x79a7  stloc.s  5
0x79a9  br.s     loc_79B2
0x79ab  ldsfld   class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EndpointVersionProvider::CrmSdk2007Version
0x79b0  stloc.s  5
0x79b2  ldloc.s  4
0x79b4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x79b9  stloc.s  7
0x79bb  br       loc_7AA2
0x79c0  ldloc.s  7
0x79c2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x79c7  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x79cc  stloc.s  8
0x79ce  ldloc.s  8
0x79d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0x79d5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x79da  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x79df  brfalse  loc_7AA2
0x79e4  ldloc.s  8
0x79e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AggregateOf()
0x79eb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x79f0  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x79f5  brfalse  loc_7AA2
0x79fa  ldloc.s  8
0x79fc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_VisibleToPlatform()
0x7a01  brfalse  loc_7AA2
0x7a06  ldloc.s  8
0x7a08  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x7a0d  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x7a12  ldc.i4.s 0x14
0x7a14  beq      loc_7AA2
0x7a19  ldloc.s  8
0x7a1b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x7a20  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x7a25  ldstr    aManagedpropert// "managedproperty"
0x7a2a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7a2f  brfalse.s loc_7AA2
0x7a31  ldloc.s  8
0x7a33  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForRead()
0x7a38  brtrue.s loc_7A4C
0x7a3a  ldloc.s  8
0x7a3c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0x7a41  brtrue.s loc_7A4C
0x7a43  ldloc.s  8
0x7a45  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0x7a4a  brfalse.s loc_7AA2
0x7a4c  ldloc.s  8
0x7a4e  ldloc.s  5
0x7a50  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::IsDeprecated(class [mscorlib]System.Version)
0x7a55  brtrue.s loc_7AA2
0x7a57  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x7a5c  stloc.s  9
0x7a5e  ldloc.3
0x7a5f  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x7a64  ldloc.s  9
0x7a66  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x7a6b  pop
0x7a6c  ldloc.s  9
0x7a6e  ldloc.s  8
0x7a70  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x7a75  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x7a7a  ldloc.s  9
0x7a7c  ldarg.0
0x7a7d  ldarg.1
0x7a7e  ldloc.s  8
0x7a80  call     instance class [System.Xml]System.Xml.XmlQualifiedName Microsoft.Crm.Sdk.ConcreteBusinessEntitySchemaBuilder::GetAttributeType(class Microsoft.Crm.Sdk.SchemaContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata amd)
0x7a85  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x7a8a  ldloc.s  9
0x7a8c  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Zero
0x7a91  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaParticle::set_MinOccurs(valuetype [mscorlib]System.Decimal)
0x7a96  ldloc.s  9
0x7a98  ldstr    a1// "1"
0x7a9d  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaParticle::set_MaxOccursString(string)
0x7aa2  ldloc.s  7
0x7aa4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7aa9  brtrue   loc_79C0
0x7aae  leave.s  loc_7AC5
0x7ab0  ldloc.s  7
0x7ab2  isinst   [mscorlib]System.IDisposable
0x7ab7  stloc.s  0xA
0x7ab9  ldloc.s  0xA
0x7abb  brfalse.s loc_7AC4
0x7abd  ldloc.s  0xA
0x7abf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7ac4  endfinally
0x7ac5  ldarg.2
0x7ac6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x7acb  ldstr    aCalendar// "Calendar"
0x7ad0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7ad5  brfalse.s loc_7B11
0x7ad7  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0x7adc  stloc.s  0xB
0x7ade  ldloc.3
0x7adf  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x7ae4  ldloc.s  0xB
0x7ae6  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x7aeb  pop
0x7aec  ldloc.s  0xB
0x7aee  ldstr    aCalendarrules// "calendarrules"
0x7af3  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0x7af8  ldloc.s  0xB
0x7afa  ldarg.1
0x7afb  callvirt instance class Microsoft.Crm.Sdk.AttributeTypeSchemaCache Microsoft.Crm.Sdk.SchemaContext::get_AttributeTypeSchemaCache()
0x7b00  ldc.i4.s 0x13
0x7b02  callvirt instance class AttributeTypeSchemaCacheEntry Microsoft.Crm.Sdk.AttributeTypeSchemaCache::get_Item(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType attributeType)
0x7b07  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName AttributeTypeSchemaCacheEntry::get_StrongType()
0x7b0c  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x7b11  ldloc.0
0x7b12  ret
```
