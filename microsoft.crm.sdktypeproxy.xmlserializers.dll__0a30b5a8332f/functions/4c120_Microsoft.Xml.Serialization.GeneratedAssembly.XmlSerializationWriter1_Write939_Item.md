# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write939_Item

- ea: `0x4c120`
- end: `0x4c208`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write939_Item`
- size: `232`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x4c120`

## string_xrefs

- `0x4c165`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c17f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c195`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c1ba`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c1d0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c1eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c1b5`: `ParameterXml`
- `0x4c160`: `ImportCompressedXmlWithProgressRequest`
- `0x4c1cb`: `CompressedCustomizationXml`

## pseudocode

```c

```

## disassembly

```asm
0x4c120  ldarg.3
0x4c121  brtrue.s loc_4C130
0x4c123  ldarg.s  4
0x4c125  brfalse.s loc_4C12F
0x4c127  ldarg.0
0x4c128  ldarg.1
0x4c129  ldarg.2
0x4c12a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4c12f  ret
0x4c130  ldarg.s  5
0x4c132  brtrue.s loc_4C150
0x4c134  ldarg.3
0x4c135  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4c13a  stloc.0
0x4c13b  ldloc.0
0x4c13c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportCompressedXmlWithProgressRequest
0x4c141  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c146  beq.s    loc_4C150
0x4c148  ldarg.0
0x4c149  ldarg.3
0x4c14a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4c14f  throw
0x4c150  ldarg.0
0x4c151  ldarg.1
0x4c152  ldarg.2
0x4c153  ldarg.3
0x4c154  ldc.i4.0
0x4c155  ldnull
0x4c156  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4c15b  ldarg.s  5
0x4c15d  brfalse.s loc_4C16F
0x4c15f  ldarg.0
0x4c160  ldstr    aImportcompress// "ImportCompressedXmlWithProgressRequest"
0x4c165  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c16a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4c16f  ldarg.3
0x4c170  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4c175  stloc.1
0x4c176  ldloc.1
0x4c177  brfalse.s loc_4C1B4
0x4c179  ldarg.0
0x4c17a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4c17f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c184  ldnull
0x4c185  ldc.i4.0
0x4c186  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4c18b  ldc.i4.0
0x4c18c  stloc.2
0x4c18d  br.s     loc_4C1A8
0x4c18f  ldarg.0
0x4c190  ldstr    aOptionalparame// "OptionalParameter"
0x4c195  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c19a  ldloc.1
0x4c19b  ldloc.2
0x4c19c  ldelem.ref
0x4c19d  ldc.i4.1
0x4c19e  ldc.i4.0
0x4c19f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4c1a4  ldloc.2
0x4c1a5  ldc.i4.1
0x4c1a6  add
0x4c1a7  stloc.2
0x4c1a8  ldloc.2
0x4c1a9  ldloc.1
0x4c1aa  ldlen
0x4c1ab  conv.i4
0x4c1ac  blt.s    loc_4C18F
0x4c1ae  ldarg.0
0x4c1af  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4c1b4  ldarg.0
0x4c1b5  ldstr    aParameterxml_0// "ParameterXml"
0x4c1ba  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c1bf  ldarg.3
0x4c1c0  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportCompressedXmlWithProgressRequest::get_ParameterXml()
0x4c1c5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4c1ca  ldarg.0
0x4c1cb  ldstr    aCompressedcust// "CompressedCustomizationXml"
0x4c1d0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c1d5  ldarg.3
0x4c1d6  callvirt instance unsigned int8[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportCompressedXmlWithProgressRequest::get_CompressedCustomizationXml()
0x4c1db  call     unsigned int8[] [System.Xml]System.Xml.Serialization.XmlSerializationWriter::FromByteArrayBase64(unsigned int8[])
0x4c1e0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, unsigned int8[])
0x4c1e5  ldarg.0
0x4c1e6  ldstr    aImportjobid_0// "ImportJobId"
0x4c1eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c1f0  ldarg.3
0x4c1f1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportCompressedXmlWithProgressRequest::get_ImportJobId()
0x4c1f6  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4c1fb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4c200  ldarg.0
0x4c201  ldarg.3
0x4c202  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4c207  ret
```
