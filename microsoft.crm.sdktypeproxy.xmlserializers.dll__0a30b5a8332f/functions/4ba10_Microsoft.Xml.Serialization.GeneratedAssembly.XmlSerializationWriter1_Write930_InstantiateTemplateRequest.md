# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write930_InstantiateTemplateRequest

- ea: `0x4ba10`
- end: `0x4bb13`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write930_InstantiateTemplateRequest`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x4ba10`

## string_xrefs

- `0x4ba55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4ba8a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4baa0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bac5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bae0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4baf6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bac0`: `TemplateId`
- `0x4ba50`: `InstantiateTemplateRequest`

## pseudocode

```c

```

## disassembly

```asm
0x4ba10  ldarg.3
0x4ba11  brtrue.s loc_4BA20
0x4ba13  ldarg.s  4
0x4ba15  brfalse.s loc_4BA1F
0x4ba17  ldarg.0
0x4ba18  ldarg.1
0x4ba19  ldarg.2
0x4ba1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4ba1f  ret
0x4ba20  ldarg.s  5
0x4ba22  brtrue.s loc_4BA40
0x4ba24  ldarg.3
0x4ba25  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4ba2a  stloc.0
0x4ba2b  ldloc.0
0x4ba2c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.InstantiateTemplateRequest
0x4ba31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ba36  beq.s    loc_4BA40
0x4ba38  ldarg.0
0x4ba39  ldarg.3
0x4ba3a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4ba3f  throw
0x4ba40  ldarg.0
0x4ba41  ldarg.1
0x4ba42  ldarg.2
0x4ba43  ldarg.3
0x4ba44  ldc.i4.0
0x4ba45  ldnull
0x4ba46  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4ba4b  ldarg.s  5
0x4ba4d  brfalse.s loc_4BA5F
0x4ba4f  ldarg.0
0x4ba50  ldstr    aInstantiatetem// "InstantiateTemplateRequest"
0x4ba55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ba5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4ba5f  ldarg.0
0x4ba60  ldstr    aReturndynamice// "ReturnDynamicEntities"
0x4ba65  ldstr    asc_1A34A2// ""
0x4ba6a  ldarg.3
0x4ba6b  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.InstantiateTemplateRequest::get_ReturnDynamicEntities()
0x4ba70  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4ba75  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x4ba7a  ldarg.3
0x4ba7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4ba80  stloc.1
0x4ba81  ldloc.1
0x4ba82  brfalse.s loc_4BABF
0x4ba84  ldarg.0
0x4ba85  ldstr    aOptionalparame_0// "OptionalParameters"
0x4ba8a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ba8f  ldnull
0x4ba90  ldc.i4.0
0x4ba91  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4ba96  ldc.i4.0
0x4ba97  stloc.2
0x4ba98  br.s     loc_4BAB3
0x4ba9a  ldarg.0
0x4ba9b  ldstr    aOptionalparame// "OptionalParameter"
0x4baa0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4baa5  ldloc.1
0x4baa6  ldloc.2
0x4baa7  ldelem.ref
0x4baa8  ldc.i4.1
0x4baa9  ldc.i4.0
0x4baaa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4baaf  ldloc.2
0x4bab0  ldc.i4.1
0x4bab1  add
0x4bab2  stloc.2
0x4bab3  ldloc.2
0x4bab4  ldloc.1
0x4bab5  ldlen
0x4bab6  conv.i4
0x4bab7  blt.s    loc_4BA9A
0x4bab9  ldarg.0
0x4baba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4babf  ldarg.0
0x4bac0  ldstr    aTemplateid_0// "TemplateId"
0x4bac5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4baca  ldarg.3
0x4bacb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.InstantiateTemplateRequest::get_TemplateId()
0x4bad0  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4bad5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4bada  ldarg.0
0x4badb  ldstr    aObjecttype// "ObjectType"
0x4bae0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bae5  ldarg.3
0x4bae6  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.InstantiateTemplateRequest::get_ObjectType()
0x4baeb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4baf0  ldarg.0
0x4baf1  ldstr    aObjectid// "ObjectId"
0x4baf6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bafb  ldarg.3
0x4bafc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.InstantiateTemplateRequest::get_ObjectId()
0x4bb01  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4bb06  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4bb0b  ldarg.0
0x4bb0c  ldarg.3
0x4bb0d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4bb12  ret
```
