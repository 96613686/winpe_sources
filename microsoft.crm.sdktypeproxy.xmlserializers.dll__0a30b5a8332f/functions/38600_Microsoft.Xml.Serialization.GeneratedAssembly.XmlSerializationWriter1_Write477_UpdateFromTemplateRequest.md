# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write477_UpdateFromTemplateRequest

- ea: `0x38600`
- end: `0x386cd`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write477_UpdateFromTemplateRequest`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x38600`

## string_xrefs

- `0x38645`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3865f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38675`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3869a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x386b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38640`: `UpdateFromTemplateRequest`
- `0x386b0`: `WizardXml`

## pseudocode

```c

```

## disassembly

```asm
0x38600  ldarg.3
0x38601  brtrue.s loc_38610
0x38603  ldarg.s  4
0x38605  brfalse.s loc_3860F
0x38607  ldarg.0
0x38608  ldarg.1
0x38609  ldarg.2
0x3860a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3860f  ret
0x38610  ldarg.s  5
0x38612  brtrue.s loc_38630
0x38614  ldarg.3
0x38615  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3861a  stloc.0
0x3861b  ldloc.0
0x3861c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateFromTemplateRequest
0x38621  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x38626  beq.s    loc_38630
0x38628  ldarg.0
0x38629  ldarg.3
0x3862a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3862f  throw
0x38630  ldarg.0
0x38631  ldarg.1
0x38632  ldarg.2
0x38633  ldarg.3
0x38634  ldc.i4.0
0x38635  ldnull
0x38636  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3863b  ldarg.s  5
0x3863d  brfalse.s loc_3864F
0x3863f  ldarg.0
0x38640  ldstr    aUpdatefromtemp// "UpdateFromTemplateRequest"
0x38645  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3864a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3864f  ldarg.3
0x38650  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x38655  stloc.1
0x38656  ldloc.1
0x38657  brfalse.s loc_38694
0x38659  ldarg.0
0x3865a  ldstr    aOptionalparame_0// "OptionalParameters"
0x3865f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38664  ldnull
0x38665  ldc.i4.0
0x38666  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3866b  ldc.i4.0
0x3866c  stloc.2
0x3866d  br.s     loc_38688
0x3866f  ldarg.0
0x38670  ldstr    aOptionalparame// "OptionalParameter"
0x38675  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3867a  ldloc.1
0x3867b  ldloc.2
0x3867c  ldelem.ref
0x3867d  ldc.i4.1
0x3867e  ldc.i4.0
0x3867f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x38684  ldloc.2
0x38685  ldc.i4.1
0x38686  add
0x38687  stloc.2
0x38688  ldloc.2
0x38689  ldloc.1
0x3868a  ldlen
0x3868b  conv.i4
0x3868c  blt.s    loc_3866F
0x3868e  ldarg.0
0x3868f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x38694  ldarg.0
0x38695  ldstr    aReportid_0// "ReportId"
0x3869a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3869f  ldarg.3
0x386a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateFromTemplateRequest::get_ReportId()
0x386a5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x386aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x386af  ldarg.0
0x386b0  ldstr    aWizardxml// "WizardXml"
0x386b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x386ba  ldarg.3
0x386bb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UpdateFromTemplateRequest::get_WizardXml()
0x386c0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x386c5  ldarg.0
0x386c6  ldarg.3
0x386c7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x386cc  ret
```
