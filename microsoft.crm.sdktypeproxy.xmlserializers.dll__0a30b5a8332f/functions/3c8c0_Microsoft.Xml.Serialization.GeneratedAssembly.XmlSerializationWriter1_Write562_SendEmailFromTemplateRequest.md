# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write562_SendEmailFromTemplateRequest

- ea: `0x3c8c0`
- end: `0x3c9c0`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write562_SendEmailFromTemplateRequest`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x3c8c0`
- `0x3c9c0`

## string_xrefs

- `0x3c905`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c91f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c935`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c95a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c975`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c98b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c9a6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c955`: `TemplateId`
- `0x3c900`: `SendEmailFromTemplateRequest`

## pseudocode

```c

```

## disassembly

```asm
0x3c8c0  ldarg.3
0x3c8c1  brtrue.s loc_3C8D0
0x3c8c3  ldarg.s  4
0x3c8c5  brfalse.s loc_3C8CF
0x3c8c7  ldarg.0
0x3c8c8  ldarg.1
0x3c8c9  ldarg.2
0x3c8ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3c8cf  ret
0x3c8d0  ldarg.s  5
0x3c8d2  brtrue.s loc_3C8F0
0x3c8d4  ldarg.3
0x3c8d5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c8da  stloc.0
0x3c8db  ldloc.0
0x3c8dc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendEmailFromTemplateRequest
0x3c8e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c8e6  beq.s    loc_3C8F0
0x3c8e8  ldarg.0
0x3c8e9  ldarg.3
0x3c8ea  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3c8ef  throw
0x3c8f0  ldarg.0
0x3c8f1  ldarg.1
0x3c8f2  ldarg.2
0x3c8f3  ldarg.3
0x3c8f4  ldc.i4.0
0x3c8f5  ldnull
0x3c8f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3c8fb  ldarg.s  5
0x3c8fd  brfalse.s loc_3C90F
0x3c8ff  ldarg.0
0x3c900  ldstr    aSendemailfromt// "SendEmailFromTemplateRequest"
0x3c905  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c90a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3c90f  ldarg.3
0x3c910  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x3c915  stloc.1
0x3c916  ldloc.1
0x3c917  brfalse.s loc_3C954
0x3c919  ldarg.0
0x3c91a  ldstr    aOptionalparame_0// "OptionalParameters"
0x3c91f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c924  ldnull
0x3c925  ldc.i4.0
0x3c926  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3c92b  ldc.i4.0
0x3c92c  stloc.2
0x3c92d  br.s     loc_3C948
0x3c92f  ldarg.0
0x3c930  ldstr    aOptionalparame// "OptionalParameter"
0x3c935  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c93a  ldloc.1
0x3c93b  ldloc.2
0x3c93c  ldelem.ref
0x3c93d  ldc.i4.1
0x3c93e  ldc.i4.0
0x3c93f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x3c944  ldloc.2
0x3c945  ldc.i4.1
0x3c946  add
0x3c947  stloc.2
0x3c948  ldloc.2
0x3c949  ldloc.1
0x3c94a  ldlen
0x3c94b  conv.i4
0x3c94c  blt.s    loc_3C92F
0x3c94e  ldarg.0
0x3c94f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3c954  ldarg.0
0x3c955  ldstr    aTemplateid_0// "TemplateId"
0x3c95a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c95f  ldarg.3
0x3c960  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendEmailFromTemplateRequest::get_TemplateId()
0x3c965  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3c96a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3c96f  ldarg.0
0x3c970  ldstr    aRegardingtype// "RegardingType"
0x3c975  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c97a  ldarg.3
0x3c97b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendEmailFromTemplateRequest::get_RegardingType()
0x3c980  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3c985  ldarg.0
0x3c986  ldstr    aRegardingid// "RegardingId"
0x3c98b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c990  ldarg.3
0x3c991  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendEmailFromTemplateRequest::get_RegardingId()
0x3c996  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3c99b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3c9a0  ldarg.0
0x3c9a1  ldstr    aTarget// "Target"
0x3c9a6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c9ab  ldarg.3
0x3c9ac  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TargetSendFromTemplate [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendEmailFromTemplateRequest::get_Target()
0x3c9b1  ldc.i4.0
0x3c9b2  ldc.i4.0
0x3c9b3  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write561_TargetSendFromTemplate(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TargetSendFromTemplate o, bool isNullable, bool needType)
0x3c9b8  ldarg.0
0x3c9b9  ldarg.3
0x3c9ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3c9bf  ret
```
