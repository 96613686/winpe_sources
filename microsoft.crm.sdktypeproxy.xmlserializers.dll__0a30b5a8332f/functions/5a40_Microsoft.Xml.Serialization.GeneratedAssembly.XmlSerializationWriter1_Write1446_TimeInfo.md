# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1446_TimeInfo

- ea: `0x5a40`
- end: `0x5bb9`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1446_TimeInfo`
- size: `377`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1940`
- `0x6ac0`
- `0x60dd0`
- `0x60e70`
- `0x63850`

## callees

- `0x5a40`
- `0x5bc0`
- `0x5c90`
- `0x5cf0`

## string_xrefs

- `0x5a85`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x5a95`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x5aad`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x5ac5`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x5ae1`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x5afd`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x5b18`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x5b33`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x5b4e`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x5b69`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x5b84`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x5ba1`: `http://schemas.microsoft.com/crm/2006/Scheduling`

## pseudocode

```c

```

## disassembly

```asm
0x5a40  ldarg.3
0x5a41  brtrue.s loc_5A50
0x5a43  ldarg.s  4
0x5a45  brfalse.s loc_5A4F
0x5a47  ldarg.0
0x5a48  ldarg.1
0x5a49  ldarg.2
0x5a4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x5a4f  ret
0x5a50  ldarg.s  5
0x5a52  brtrue.s loc_5A70
0x5a54  ldarg.3
0x5a55  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5a5a  stloc.0
0x5a5b  ldloc.0
0x5a5c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo
0x5a61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5a66  beq.s    loc_5A70
0x5a68  ldarg.0
0x5a69  ldarg.3
0x5a6a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x5a6f  throw
0x5a70  ldarg.0
0x5a71  ldarg.1
0x5a72  ldarg.2
0x5a73  ldarg.3
0x5a74  ldc.i4.0
0x5a75  ldnull
0x5a76  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x5a7b  ldarg.s  5
0x5a7d  brfalse.s loc_5A8F
0x5a7f  ldarg.0
0x5a80  ldstr    aTimeinfo// "TimeInfo"
0x5a85  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5a8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x5a8f  ldarg.0
0x5a90  ldstr    aStart// "Start"
0x5a95  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5a9a  ldarg.3
0x5a9b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x5aa0  ldc.i4.0
0x5aa1  ldc.i4.0
0x5aa2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x5aa7  ldarg.0
0x5aa8  ldstr    aEnd// "End"
0x5aad  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5ab2  ldarg.3
0x5ab3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x5ab8  ldc.i4.0
0x5ab9  ldc.i4.0
0x5aba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x5abf  ldarg.0
0x5ac0  ldstr    aTimecode// "TimeCode"
0x5ac5  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5aca  ldarg.0
0x5acb  ldarg.3
0x5acc  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeCode [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_TimeCode()
0x5ad1  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write879_TimeCode(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeCode v)
0x5ad6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x5adb  ldarg.0
0x5adc  ldstr    aSubcode// "SubCode"
0x5ae1  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5ae6  ldarg.0
0x5ae7  ldarg.3
0x5ae8  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SubCode [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_SubCode()
0x5aed  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1445_SubCode(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SubCode v)
0x5af2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x5af7  ldarg.0
0x5af8  ldstr    aSourceid// "SourceId"
0x5afd  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5b02  ldarg.3
0x5b03  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_SourceId()
0x5b08  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x5b0d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5b12  ldarg.0
0x5b13  ldstr    aCalendarid// "CalendarId"
0x5b18  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5b1d  ldarg.3
0x5b1e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_CalendarId()
0x5b23  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x5b28  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5b2d  ldarg.0
0x5b2e  ldstr    aSourcetypecode// "SourceTypeCode"
0x5b33  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5b38  ldarg.3
0x5b39  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_SourceTypeCode()
0x5b3e  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x5b43  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5b48  ldarg.0
0x5b49  ldstr    aIsactivity// "IsActivity"
0x5b4e  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5b53  ldarg.3
0x5b54  callvirt instance bool [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_IsActivity()
0x5b59  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x5b5e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5b63  ldarg.0
0x5b64  ldstr    aActivitystatus// "ActivityStatusCode"
0x5b69  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5b6e  ldarg.3
0x5b6f  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_ActivityStatusCode()
0x5b74  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x5b79  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5b7e  ldarg.0
0x5b7f  ldstr    aEffort// "Effort"
0x5b84  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5b89  ldarg.3
0x5b8a  callvirt instance float64 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Effort()
0x5b8f  conv.r8
0x5b90  conv.r8
0x5b91  call     string [System.Xml]System.Xml.XmlConvert::ToString(float64)
0x5b96  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5b9b  ldarg.0
0x5b9c  ldstr    aDisplaytext// "DisplayText"
0x5ba1  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x5ba6  ldarg.3
0x5ba7  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_DisplayText()
0x5bac  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x5bb1  ldarg.0
0x5bb2  ldarg.3
0x5bb3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x5bb8  ret
```
