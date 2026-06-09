# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1274_Item

- ea: `0x59690`
- end: `0x597b3`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1274_Item`
- size: `291`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x59690`

## string_xrefs

- `0x596d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x596ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59705`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5972a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59745`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59760`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5977b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59796`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x59690  ldarg.3
0x59691  brtrue.s loc_596A0
0x59693  ldarg.s  4
0x59695  brfalse.s loc_5969F
0x59697  ldarg.0
0x59698  ldarg.1
0x59699  ldarg.2
0x5969a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x5969f  ret
0x596a0  ldarg.s  5
0x596a2  brtrue.s loc_596C0
0x596a4  ldarg.3
0x596a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x596aa  stloc.0
0x596ab  ldloc.0
0x596ac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkOperationStatusCloseRequest
0x596b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x596b6  beq.s    loc_596C0
0x596b8  ldarg.0
0x596b9  ldarg.3
0x596ba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x596bf  throw
0x596c0  ldarg.0
0x596c1  ldarg.1
0x596c2  ldarg.2
0x596c3  ldarg.3
0x596c4  ldc.i4.0
0x596c5  ldnull
0x596c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x596cb  ldarg.s  5
0x596cd  brfalse.s loc_596DF
0x596cf  ldarg.0
0x596d0  ldstr    aBulkoperations_0// "BulkOperationStatusCloseRequest"
0x596d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x596da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x596df  ldarg.3
0x596e0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x596e5  stloc.1
0x596e6  ldloc.1
0x596e7  brfalse.s loc_59724
0x596e9  ldarg.0
0x596ea  ldstr    aOptionalparame_0// "OptionalParameters"
0x596ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x596f4  ldnull
0x596f5  ldc.i4.0
0x596f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x596fb  ldc.i4.0
0x596fc  stloc.2
0x596fd  br.s     loc_59718
0x596ff  ldarg.0
0x59700  ldstr    aOptionalparame// "OptionalParameter"
0x59705  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5970a  ldloc.1
0x5970b  ldloc.2
0x5970c  ldelem.ref
0x5970d  ldc.i4.1
0x5970e  ldc.i4.0
0x5970f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x59714  ldloc.2
0x59715  ldc.i4.1
0x59716  add
0x59717  stloc.2
0x59718  ldloc.2
0x59719  ldloc.1
0x5971a  ldlen
0x5971b  conv.i4
0x5971c  blt.s    loc_596FF
0x5971e  ldarg.0
0x5971f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x59724  ldarg.0
0x59725  ldstr    aBulkoperationi// "BulkOperationId"
0x5972a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5972f  ldarg.3
0x59730  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkOperationStatusCloseRequest::get_BulkOperationId()
0x59735  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x5973a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5973f  ldarg.0
0x59740  ldstr    aFailurecount_0// "FailureCount"
0x59745  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5974a  ldarg.3
0x5974b  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkOperationStatusCloseRequest::get_FailureCount()
0x59750  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x59755  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5975a  ldarg.0
0x5975b  ldstr    aSuccesscount_0// "SuccessCount"
0x59760  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59765  ldarg.3
0x59766  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkOperationStatusCloseRequest::get_SuccessCount()
0x5976b  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x59770  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x59775  ldarg.0
0x59776  ldstr    aStatusreason// "StatusReason"
0x5977b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59780  ldarg.3
0x59781  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkOperationStatusCloseRequest::get_StatusReason()
0x59786  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x5978b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x59790  ldarg.0
0x59791  ldstr    aErrorcode// "ErrorCode"
0x59796  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5979b  ldarg.3
0x5979c  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkOperationStatusCloseRequest::get_ErrorCode()
0x597a1  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x597a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x597ab  ldarg.0
0x597ac  ldarg.3
0x597ad  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x597b2  ret
```
