# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write476_UpdateRecurrencePatternRequest

- ea: `0x38510`
- end: `0x385f5`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write476_UpdateRecurrencePatternRequest`
- size: `229`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x5cf0`
- `0x2fdf0`
- `0x38510`

## string_xrefs

- `0x38555`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3856f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38585`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x385aa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x385c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x385db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38550`: `UpdateRecurrencePatternRequest`

## pseudocode

```c

```

## disassembly

```asm
0x38510  ldarg.3
0x38511  brtrue.s loc_38520
0x38513  ldarg.s  4
0x38515  brfalse.s loc_3851F
0x38517  ldarg.0
0x38518  ldarg.1
0x38519  ldarg.2
0x3851a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3851f  ret
0x38520  ldarg.s  5
0x38522  brtrue.s loc_38540
0x38524  ldarg.3
0x38525  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3852a  stloc.0
0x3852b  ldloc.0
0x3852c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateRecurrencePatternRequest
0x38531  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x38536  beq.s    loc_38540
0x38538  ldarg.0
0x38539  ldarg.3
0x3853a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3853f  throw
0x38540  ldarg.0
0x38541  ldarg.1
0x38542  ldarg.2
0x38543  ldarg.3
0x38544  ldc.i4.0
0x38545  ldnull
0x38546  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3854b  ldarg.s  5
0x3854d  brfalse.s loc_3855F
0x3854f  ldarg.0
0x38550  ldstr    aUpdaterecurren// "UpdateRecurrencePatternRequest"
0x38555  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3855a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3855f  ldarg.3
0x38560  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x38565  stloc.1
0x38566  ldloc.1
0x38567  brfalse.s loc_385A4
0x38569  ldarg.0
0x3856a  ldstr    aOptionalparame_0// "OptionalParameters"
0x3856f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38574  ldnull
0x38575  ldc.i4.0
0x38576  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3857b  ldc.i4.0
0x3857c  stloc.2
0x3857d  br.s     loc_38598
0x3857f  ldarg.0
0x38580  ldstr    aOptionalparame// "OptionalParameter"
0x38585  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3858a  ldloc.1
0x3858b  ldloc.2
0x3858c  ldelem.ref
0x3858d  ldc.i4.1
0x3858e  ldc.i4.0
0x3858f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x38594  ldloc.2
0x38595  ldc.i4.1
0x38596  add
0x38597  stloc.2
0x38598  ldloc.2
0x38599  ldloc.1
0x3859a  ldlen
0x3859b  conv.i4
0x3859c  blt.s    loc_3857F
0x3859e  ldarg.0
0x3859f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x385a4  ldarg.0
0x385a5  ldstr    aAsyncoperation_4// "AsyncOperationId"
0x385aa  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x385af  ldarg.3
0x385b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateRecurrencePatternRequest::get_AsyncOperationId()
0x385b5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x385ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x385bf  ldarg.0
0x385c0  ldstr    aRecurrencepatt_0// "RecurrencePattern"
0x385c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x385ca  ldarg.3
0x385cb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateRecurrencePatternRequest::get_RecurrencePattern()
0x385d0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x385d5  ldarg.0
0x385d6  ldstr    aRecurrencestar_0// "RecurrenceStartTime"
0x385db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x385e0  ldarg.3
0x385e1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateRecurrencePatternRequest::get_RecurrenceStartTime()
0x385e6  ldc.i4.0
0x385e7  ldc.i4.0
0x385e8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x385ed  ldarg.0
0x385ee  ldarg.3
0x385ef  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x385f4  ret
```
