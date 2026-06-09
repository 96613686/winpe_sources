# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write918_LogFailureBulkOperationRequest

- ea: `0x4b090`
- end: `0x4b1c4`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write918_LogFailureBulkOperationRequest`
- size: `308`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x4b090`

## string_xrefs

- `0x4b0d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b0ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b105`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b12a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b145`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b160`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b17b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b196`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b1ac`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x4b090  ldarg.3
0x4b091  brtrue.s loc_4B0A0
0x4b093  ldarg.s  4
0x4b095  brfalse.s loc_4B09F
0x4b097  ldarg.0
0x4b098  ldarg.1
0x4b099  ldarg.2
0x4b09a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4b09f  ret
0x4b0a0  ldarg.s  5
0x4b0a2  brtrue.s loc_4B0C0
0x4b0a4  ldarg.3
0x4b0a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4b0aa  stloc.0
0x4b0ab  ldloc.0
0x4b0ac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogFailureBulkOperationRequest
0x4b0b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4b0b6  beq.s    loc_4B0C0
0x4b0b8  ldarg.0
0x4b0b9  ldarg.3
0x4b0ba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4b0bf  throw
0x4b0c0  ldarg.0
0x4b0c1  ldarg.1
0x4b0c2  ldarg.2
0x4b0c3  ldarg.3
0x4b0c4  ldc.i4.0
0x4b0c5  ldnull
0x4b0c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4b0cb  ldarg.s  5
0x4b0cd  brfalse.s loc_4B0DF
0x4b0cf  ldarg.0
0x4b0d0  ldstr    aLogfailurebulk// "LogFailureBulkOperationRequest"
0x4b0d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b0da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4b0df  ldarg.3
0x4b0e0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4b0e5  stloc.1
0x4b0e6  ldloc.1
0x4b0e7  brfalse.s loc_4B124
0x4b0e9  ldarg.0
0x4b0ea  ldstr    aOptionalparame_0// "OptionalParameters"
0x4b0ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b0f4  ldnull
0x4b0f5  ldc.i4.0
0x4b0f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4b0fb  ldc.i4.0
0x4b0fc  stloc.2
0x4b0fd  br.s     loc_4B118
0x4b0ff  ldarg.0
0x4b100  ldstr    aOptionalparame// "OptionalParameter"
0x4b105  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b10a  ldloc.1
0x4b10b  ldloc.2
0x4b10c  ldelem.ref
0x4b10d  ldc.i4.1
0x4b10e  ldc.i4.0
0x4b10f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4b114  ldloc.2
0x4b115  ldc.i4.1
0x4b116  add
0x4b117  stloc.2
0x4b118  ldloc.2
0x4b119  ldloc.1
0x4b11a  ldlen
0x4b11b  conv.i4
0x4b11c  blt.s    loc_4B0FF
0x4b11e  ldarg.0
0x4b11f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4b124  ldarg.0
0x4b125  ldstr    aBulkoperationi// "BulkOperationId"
0x4b12a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b12f  ldarg.3
0x4b130  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogFailureBulkOperationRequest::get_BulkOperationId()
0x4b135  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4b13a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4b13f  ldarg.0
0x4b140  ldstr    aRegardingobjec_1// "RegardingObjectId"
0x4b145  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b14a  ldarg.3
0x4b14b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogFailureBulkOperationRequest::get_RegardingObjectId()
0x4b150  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4b155  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4b15a  ldarg.0
0x4b15b  ldstr    aRegardingobjec_2// "RegardingObjectTypeCode"
0x4b160  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b165  ldarg.3
0x4b166  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogFailureBulkOperationRequest::get_RegardingObjectTypeCode()
0x4b16b  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4b170  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4b175  ldarg.0
0x4b176  ldstr    aErrorcode// "ErrorCode"
0x4b17b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b180  ldarg.3
0x4b181  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogFailureBulkOperationRequest::get_ErrorCode()
0x4b186  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4b18b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4b190  ldarg.0
0x4b191  ldstr    aMessage_0// "Message"
0x4b196  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b19b  ldarg.3
0x4b19c  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogFailureBulkOperationRequest::get_Message()
0x4b1a1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4b1a6  ldarg.0
0x4b1a7  ldstr    aAdditionalinfo// "AdditionalInfo"
0x4b1ac  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b1b1  ldarg.3
0x4b1b2  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogFailureBulkOperationRequest::get_AdditionalInfo()
0x4b1b7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4b1bc  ldarg.0
0x4b1bd  ldarg.3
0x4b1be  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4b1c3  ret
```
