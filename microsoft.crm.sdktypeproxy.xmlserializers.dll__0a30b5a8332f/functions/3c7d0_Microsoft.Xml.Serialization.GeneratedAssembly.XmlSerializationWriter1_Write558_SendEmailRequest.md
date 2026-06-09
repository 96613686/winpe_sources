# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write558_SendEmailRequest

- ea: `0x3c7d0`
- end: `0x3c8b8`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write558_SendEmailRequest`
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
- `0x3c7d0`

## string_xrefs

- `0x3c815`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c82f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c845`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c86a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c885`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c8a0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c89b`: `TrackingToken`

## pseudocode

```c

```

## disassembly

```asm
0x3c7d0  ldarg.3
0x3c7d1  brtrue.s loc_3C7E0
0x3c7d3  ldarg.s  4
0x3c7d5  brfalse.s loc_3C7DF
0x3c7d7  ldarg.0
0x3c7d8  ldarg.1
0x3c7d9  ldarg.2
0x3c7da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3c7df  ret
0x3c7e0  ldarg.s  5
0x3c7e2  brtrue.s loc_3C800
0x3c7e4  ldarg.3
0x3c7e5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c7ea  stloc.0
0x3c7eb  ldloc.0
0x3c7ec  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendEmailRequest
0x3c7f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c7f6  beq.s    loc_3C800
0x3c7f8  ldarg.0
0x3c7f9  ldarg.3
0x3c7fa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3c7ff  throw
0x3c800  ldarg.0
0x3c801  ldarg.1
0x3c802  ldarg.2
0x3c803  ldarg.3
0x3c804  ldc.i4.0
0x3c805  ldnull
0x3c806  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3c80b  ldarg.s  5
0x3c80d  brfalse.s loc_3C81F
0x3c80f  ldarg.0
0x3c810  ldstr    aSendemailreque// "SendEmailRequest"
0x3c815  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c81a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3c81f  ldarg.3
0x3c820  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x3c825  stloc.1
0x3c826  ldloc.1
0x3c827  brfalse.s loc_3C864
0x3c829  ldarg.0
0x3c82a  ldstr    aOptionalparame_0// "OptionalParameters"
0x3c82f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c834  ldnull
0x3c835  ldc.i4.0
0x3c836  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3c83b  ldc.i4.0
0x3c83c  stloc.2
0x3c83d  br.s     loc_3C858
0x3c83f  ldarg.0
0x3c840  ldstr    aOptionalparame// "OptionalParameter"
0x3c845  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c84a  ldloc.1
0x3c84b  ldloc.2
0x3c84c  ldelem.ref
0x3c84d  ldc.i4.1
0x3c84e  ldc.i4.0
0x3c84f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x3c854  ldloc.2
0x3c855  ldc.i4.1
0x3c856  add
0x3c857  stloc.2
0x3c858  ldloc.2
0x3c859  ldloc.1
0x3c85a  ldlen
0x3c85b  conv.i4
0x3c85c  blt.s    loc_3C83F
0x3c85e  ldarg.0
0x3c85f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3c864  ldarg.0
0x3c865  ldstr    aEmailid// "EmailId"
0x3c86a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c86f  ldarg.3
0x3c870  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendEmailRequest::get_EmailId()
0x3c875  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3c87a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3c87f  ldarg.0
0x3c880  ldstr    aIssuesend// "IssueSend"
0x3c885  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c88a  ldarg.3
0x3c88b  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendEmailRequest::get_IssueSend()
0x3c890  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x3c895  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3c89a  ldarg.0
0x3c89b  ldstr    aTrackingtoken_0// "TrackingToken"
0x3c8a0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c8a5  ldarg.3
0x3c8a6  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendEmailRequest::get_TrackingToken()
0x3c8ab  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3c8b0  ldarg.0
0x3c8b1  ldarg.3
0x3c8b2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3c8b7  ret
```
