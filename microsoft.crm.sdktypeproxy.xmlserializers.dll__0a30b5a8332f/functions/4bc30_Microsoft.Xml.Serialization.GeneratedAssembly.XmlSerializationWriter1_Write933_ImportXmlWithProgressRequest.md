# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write933_ImportXmlWithProgressRequest

- ea: `0x4bc30`
- end: `0x4bd13`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write933_ImportXmlWithProgressRequest`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x4bc30`

## string_xrefs

- `0x4bc75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bc8f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bca5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bcca`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bce0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bcf6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bcc5`: `ParameterXml`
- `0x4bc70`: `ImportXmlWithProgressRequest`
- `0x4bcdb`: `CustomizationXml`

## pseudocode

```c

```

## disassembly

```asm
0x4bc30  ldarg.3
0x4bc31  brtrue.s loc_4BC40
0x4bc33  ldarg.s  4
0x4bc35  brfalse.s loc_4BC3F
0x4bc37  ldarg.0
0x4bc38  ldarg.1
0x4bc39  ldarg.2
0x4bc3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4bc3f  ret
0x4bc40  ldarg.s  5
0x4bc42  brtrue.s loc_4BC60
0x4bc44  ldarg.3
0x4bc45  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4bc4a  stloc.0
0x4bc4b  ldloc.0
0x4bc4c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportXmlWithProgressRequest
0x4bc51  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4bc56  beq.s    loc_4BC60
0x4bc58  ldarg.0
0x4bc59  ldarg.3
0x4bc5a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4bc5f  throw
0x4bc60  ldarg.0
0x4bc61  ldarg.1
0x4bc62  ldarg.2
0x4bc63  ldarg.3
0x4bc64  ldc.i4.0
0x4bc65  ldnull
0x4bc66  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4bc6b  ldarg.s  5
0x4bc6d  brfalse.s loc_4BC7F
0x4bc6f  ldarg.0
0x4bc70  ldstr    aImportxmlwithp// "ImportXmlWithProgressRequest"
0x4bc75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bc7a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4bc7f  ldarg.3
0x4bc80  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4bc85  stloc.1
0x4bc86  ldloc.1
0x4bc87  brfalse.s loc_4BCC4
0x4bc89  ldarg.0
0x4bc8a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4bc8f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bc94  ldnull
0x4bc95  ldc.i4.0
0x4bc96  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4bc9b  ldc.i4.0
0x4bc9c  stloc.2
0x4bc9d  br.s     loc_4BCB8
0x4bc9f  ldarg.0
0x4bca0  ldstr    aOptionalparame// "OptionalParameter"
0x4bca5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bcaa  ldloc.1
0x4bcab  ldloc.2
0x4bcac  ldelem.ref
0x4bcad  ldc.i4.1
0x4bcae  ldc.i4.0
0x4bcaf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4bcb4  ldloc.2
0x4bcb5  ldc.i4.1
0x4bcb6  add
0x4bcb7  stloc.2
0x4bcb8  ldloc.2
0x4bcb9  ldloc.1
0x4bcba  ldlen
0x4bcbb  conv.i4
0x4bcbc  blt.s    loc_4BC9F
0x4bcbe  ldarg.0
0x4bcbf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4bcc4  ldarg.0
0x4bcc5  ldstr    aParameterxml_0// "ParameterXml"
0x4bcca  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bccf  ldarg.3
0x4bcd0  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportXmlWithProgressRequest::get_ParameterXml()
0x4bcd5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4bcda  ldarg.0
0x4bcdb  ldstr    aCustomizationx// "CustomizationXml"
0x4bce0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bce5  ldarg.3
0x4bce6  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportXmlWithProgressRequest::get_CustomizationXml()
0x4bceb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4bcf0  ldarg.0
0x4bcf1  ldstr    aImportjobid_0// "ImportJobId"
0x4bcf6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bcfb  ldarg.3
0x4bcfc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportXmlWithProgressRequest::get_ImportJobId()
0x4bd01  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4bd06  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4bd0b  ldarg.0
0x4bd0c  ldarg.3
0x4bd0d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4bd12  ret
```
