# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write183_UpdateScheduleRequest

- ea: `0x34990`
- end: `0x34a89`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write183_UpdateScheduleRequest`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x34990`

## string_xrefs

- `0x349d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x349ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x34a05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x34a2a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x34a45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x34a5b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x34a71`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x349d0`: `UpdateScheduleRequest`
- `0x34a40`: `ScheduleXml`
- `0x34a56`: `ParameterXml`
- `0x34a6c`: `ScheduledReportName`

## pseudocode

```c

```

## disassembly

```asm
0x34990  ldarg.3
0x34991  brtrue.s loc_349A0
0x34993  ldarg.s  4
0x34995  brfalse.s loc_3499F
0x34997  ldarg.0
0x34998  ldarg.1
0x34999  ldarg.2
0x3499a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3499f  ret
0x349a0  ldarg.s  5
0x349a2  brtrue.s loc_349C0
0x349a4  ldarg.3
0x349a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x349aa  stloc.0
0x349ab  ldloc.0
0x349ac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateScheduleRequest
0x349b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x349b6  beq.s    loc_349C0
0x349b8  ldarg.0
0x349b9  ldarg.3
0x349ba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x349bf  throw
0x349c0  ldarg.0
0x349c1  ldarg.1
0x349c2  ldarg.2
0x349c3  ldarg.3
0x349c4  ldc.i4.0
0x349c5  ldnull
0x349c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x349cb  ldarg.s  5
0x349cd  brfalse.s loc_349DF
0x349cf  ldarg.0
0x349d0  ldstr    aUpdateschedule// "UpdateScheduleRequest"
0x349d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x349da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x349df  ldarg.3
0x349e0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x349e5  stloc.1
0x349e6  ldloc.1
0x349e7  brfalse.s loc_34A24
0x349e9  ldarg.0
0x349ea  ldstr    aOptionalparame_0// "OptionalParameters"
0x349ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x349f4  ldnull
0x349f5  ldc.i4.0
0x349f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x349fb  ldc.i4.0
0x349fc  stloc.2
0x349fd  br.s     loc_34A18
0x349ff  ldarg.0
0x34a00  ldstr    aOptionalparame// "OptionalParameter"
0x34a05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x34a0a  ldloc.1
0x34a0b  ldloc.2
0x34a0c  ldelem.ref
0x34a0d  ldc.i4.1
0x34a0e  ldc.i4.0
0x34a0f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x34a14  ldloc.2
0x34a15  ldc.i4.1
0x34a16  add
0x34a17  stloc.2
0x34a18  ldloc.2
0x34a19  ldloc.1
0x34a1a  ldlen
0x34a1b  conv.i4
0x34a1c  blt.s    loc_349FF
0x34a1e  ldarg.0
0x34a1f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x34a24  ldarg.0
0x34a25  ldstr    aReportid_0// "ReportId"
0x34a2a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x34a2f  ldarg.3
0x34a30  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateScheduleRequest::get_ReportId()
0x34a35  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x34a3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x34a3f  ldarg.0
0x34a40  ldstr    aSchedulexml_0// "ScheduleXml"
0x34a45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x34a4a  ldarg.3
0x34a4b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateScheduleRequest::get_ScheduleXml()
0x34a50  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x34a55  ldarg.0
0x34a56  ldstr    aParameterxml_0// "ParameterXml"
0x34a5b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x34a60  ldarg.3
0x34a61  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateScheduleRequest::get_ParameterXml()
0x34a66  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x34a6b  ldarg.0
0x34a6c  ldstr    aScheduledrepor// "ScheduledReportName"
0x34a71  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x34a76  ldarg.3
0x34a77  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateScheduleRequest::get_ScheduledReportName()
0x34a7c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x34a81  ldarg.0
0x34a82  ldarg.3
0x34a83  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x34a88  ret
```
