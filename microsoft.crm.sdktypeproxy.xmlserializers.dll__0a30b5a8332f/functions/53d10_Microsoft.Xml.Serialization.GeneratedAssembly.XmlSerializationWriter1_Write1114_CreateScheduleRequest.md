# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1114_CreateScheduleRequest

- ea: `0x53d10`
- end: `0x53e09`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1114_CreateScheduleRequest`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x53d10`

## string_xrefs

- `0x53d55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53d6f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53d85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53daa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53dc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53ddb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53df1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53dc0`: `ScheduleXml`
- `0x53dd6`: `ParameterXml`
- `0x53dec`: `ScheduledReportName`
- `0x53d50`: `CreateScheduleRequest`

## pseudocode

```c

```

## disassembly

```asm
0x53d10  ldarg.3
0x53d11  brtrue.s loc_53D20
0x53d13  ldarg.s  4
0x53d15  brfalse.s loc_53D1F
0x53d17  ldarg.0
0x53d18  ldarg.1
0x53d19  ldarg.2
0x53d1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x53d1f  ret
0x53d20  ldarg.s  5
0x53d22  brtrue.s loc_53D40
0x53d24  ldarg.3
0x53d25  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x53d2a  stloc.0
0x53d2b  ldloc.0
0x53d2c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateScheduleRequest
0x53d31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53d36  beq.s    loc_53D40
0x53d38  ldarg.0
0x53d39  ldarg.3
0x53d3a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x53d3f  throw
0x53d40  ldarg.0
0x53d41  ldarg.1
0x53d42  ldarg.2
0x53d43  ldarg.3
0x53d44  ldc.i4.0
0x53d45  ldnull
0x53d46  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x53d4b  ldarg.s  5
0x53d4d  brfalse.s loc_53D5F
0x53d4f  ldarg.0
0x53d50  ldstr    aCreateschedule// "CreateScheduleRequest"
0x53d55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53d5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x53d5f  ldarg.3
0x53d60  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x53d65  stloc.1
0x53d66  ldloc.1
0x53d67  brfalse.s loc_53DA4
0x53d69  ldarg.0
0x53d6a  ldstr    aOptionalparame_0// "OptionalParameters"
0x53d6f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53d74  ldnull
0x53d75  ldc.i4.0
0x53d76  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x53d7b  ldc.i4.0
0x53d7c  stloc.2
0x53d7d  br.s     loc_53D98
0x53d7f  ldarg.0
0x53d80  ldstr    aOptionalparame// "OptionalParameter"
0x53d85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53d8a  ldloc.1
0x53d8b  ldloc.2
0x53d8c  ldelem.ref
0x53d8d  ldc.i4.1
0x53d8e  ldc.i4.0
0x53d8f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x53d94  ldloc.2
0x53d95  ldc.i4.1
0x53d96  add
0x53d97  stloc.2
0x53d98  ldloc.2
0x53d99  ldloc.1
0x53d9a  ldlen
0x53d9b  conv.i4
0x53d9c  blt.s    loc_53D7F
0x53d9e  ldarg.0
0x53d9f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x53da4  ldarg.0
0x53da5  ldstr    aReportid_0// "ReportId"
0x53daa  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53daf  ldarg.3
0x53db0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateScheduleRequest::get_ReportId()
0x53db5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x53dba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x53dbf  ldarg.0
0x53dc0  ldstr    aSchedulexml_0// "ScheduleXml"
0x53dc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53dca  ldarg.3
0x53dcb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateScheduleRequest::get_ScheduleXml()
0x53dd0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x53dd5  ldarg.0
0x53dd6  ldstr    aParameterxml_0// "ParameterXml"
0x53ddb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53de0  ldarg.3
0x53de1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateScheduleRequest::get_ParameterXml()
0x53de6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x53deb  ldarg.0
0x53dec  ldstr    aScheduledrepor// "ScheduledReportName"
0x53df1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53df6  ldarg.3
0x53df7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateScheduleRequest::get_ScheduledReportName()
0x53dfc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x53e01  ldarg.0
0x53e02  ldarg.3
0x53e03  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x53e08  ret
```
