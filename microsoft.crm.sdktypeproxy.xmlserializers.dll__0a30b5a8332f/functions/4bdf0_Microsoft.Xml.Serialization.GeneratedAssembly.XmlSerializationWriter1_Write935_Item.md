# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write935_Item

- ea: `0x4bdf0`
- end: `0x4bebd`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write935_Item`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x4bdf0`

## string_xrefs

- `0x4be35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4be4f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4be65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4be8a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bea0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4be30`: `ImportTranslationsXmlWithProgressRequest`
- `0x4be85`: `ImportXml`

## pseudocode

```c

```

## disassembly

```asm
0x4bdf0  ldarg.3
0x4bdf1  brtrue.s loc_4BE00
0x4bdf3  ldarg.s  4
0x4bdf5  brfalse.s loc_4BDFF
0x4bdf7  ldarg.0
0x4bdf8  ldarg.1
0x4bdf9  ldarg.2
0x4bdfa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4bdff  ret
0x4be00  ldarg.s  5
0x4be02  brtrue.s loc_4BE20
0x4be04  ldarg.3
0x4be05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4be0a  stloc.0
0x4be0b  ldloc.0
0x4be0c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportTranslationsXmlWithProgressRequest
0x4be11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4be16  beq.s    loc_4BE20
0x4be18  ldarg.0
0x4be19  ldarg.3
0x4be1a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4be1f  throw
0x4be20  ldarg.0
0x4be21  ldarg.1
0x4be22  ldarg.2
0x4be23  ldarg.3
0x4be24  ldc.i4.0
0x4be25  ldnull
0x4be26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4be2b  ldarg.s  5
0x4be2d  brfalse.s loc_4BE3F
0x4be2f  ldarg.0
0x4be30  ldstr    aImporttranslat// "ImportTranslationsXmlWithProgressReques"...
0x4be35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4be3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4be3f  ldarg.3
0x4be40  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4be45  stloc.1
0x4be46  ldloc.1
0x4be47  brfalse.s loc_4BE84
0x4be49  ldarg.0
0x4be4a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4be4f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4be54  ldnull
0x4be55  ldc.i4.0
0x4be56  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4be5b  ldc.i4.0
0x4be5c  stloc.2
0x4be5d  br.s     loc_4BE78
0x4be5f  ldarg.0
0x4be60  ldstr    aOptionalparame// "OptionalParameter"
0x4be65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4be6a  ldloc.1
0x4be6b  ldloc.2
0x4be6c  ldelem.ref
0x4be6d  ldc.i4.1
0x4be6e  ldc.i4.0
0x4be6f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4be74  ldloc.2
0x4be75  ldc.i4.1
0x4be76  add
0x4be77  stloc.2
0x4be78  ldloc.2
0x4be79  ldloc.1
0x4be7a  ldlen
0x4be7b  conv.i4
0x4be7c  blt.s    loc_4BE5F
0x4be7e  ldarg.0
0x4be7f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4be84  ldarg.0
0x4be85  ldstr    aImportxml// "ImportXml"
0x4be8a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4be8f  ldarg.3
0x4be90  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportTranslationsXmlWithProgressRequest::get_ImportXml()
0x4be95  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4be9a  ldarg.0
0x4be9b  ldstr    aImportjobid_0// "ImportJobId"
0x4bea0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bea5  ldarg.3
0x4bea6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportTranslationsXmlWithProgressRequest::get_ImportJobId()
0x4beab  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4beb0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4beb5  ldarg.0
0x4beb6  ldarg.3
0x4beb7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4bebc  ret
```
