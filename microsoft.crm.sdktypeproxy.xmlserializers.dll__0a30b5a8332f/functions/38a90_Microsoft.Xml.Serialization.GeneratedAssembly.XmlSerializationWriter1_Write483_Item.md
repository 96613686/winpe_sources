# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write483_Item

- ea: `0x38a90`
- end: `0x38b7d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write483_Item`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x38a90`

## string_xrefs

- `0x38ad5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38aef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38b05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38b2a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38b45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38b60`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38ad0`: `StatusUpdateBulkOperationRequest`

## pseudocode

```c

```

## disassembly

```asm
0x38a90  ldarg.3
0x38a91  brtrue.s loc_38AA0
0x38a93  ldarg.s  4
0x38a95  brfalse.s loc_38A9F
0x38a97  ldarg.0
0x38a98  ldarg.1
0x38a99  ldarg.2
0x38a9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x38a9f  ret
0x38aa0  ldarg.s  5
0x38aa2  brtrue.s loc_38AC0
0x38aa4  ldarg.3
0x38aa5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x38aaa  stloc.0
0x38aab  ldloc.0
0x38aac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.StatusUpdateBulkOperationRequest
0x38ab1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x38ab6  beq.s    loc_38AC0
0x38ab8  ldarg.0
0x38ab9  ldarg.3
0x38aba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x38abf  throw
0x38ac0  ldarg.0
0x38ac1  ldarg.1
0x38ac2  ldarg.2
0x38ac3  ldarg.3
0x38ac4  ldc.i4.0
0x38ac5  ldnull
0x38ac6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x38acb  ldarg.s  5
0x38acd  brfalse.s loc_38ADF
0x38acf  ldarg.0
0x38ad0  ldstr    aStatusupdatebu// "StatusUpdateBulkOperationRequest"
0x38ad5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38ada  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x38adf  ldarg.3
0x38ae0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x38ae5  stloc.1
0x38ae6  ldloc.1
0x38ae7  brfalse.s loc_38B24
0x38ae9  ldarg.0
0x38aea  ldstr    aOptionalparame_0// "OptionalParameters"
0x38aef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38af4  ldnull
0x38af5  ldc.i4.0
0x38af6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x38afb  ldc.i4.0
0x38afc  stloc.2
0x38afd  br.s     loc_38B18
0x38aff  ldarg.0
0x38b00  ldstr    aOptionalparame// "OptionalParameter"
0x38b05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38b0a  ldloc.1
0x38b0b  ldloc.2
0x38b0c  ldelem.ref
0x38b0d  ldc.i4.1
0x38b0e  ldc.i4.0
0x38b0f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x38b14  ldloc.2
0x38b15  ldc.i4.1
0x38b16  add
0x38b17  stloc.2
0x38b18  ldloc.2
0x38b19  ldloc.1
0x38b1a  ldlen
0x38b1b  conv.i4
0x38b1c  blt.s    loc_38AFF
0x38b1e  ldarg.0
0x38b1f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x38b24  ldarg.0
0x38b25  ldstr    aBulkoperationi// "BulkOperationId"
0x38b2a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38b2f  ldarg.3
0x38b30  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.StatusUpdateBulkOperationRequest::get_BulkOperationId()
0x38b35  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x38b3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x38b3f  ldarg.0
0x38b40  ldstr    aFailurecount_0// "FailureCount"
0x38b45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38b4a  ldarg.3
0x38b4b  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.StatusUpdateBulkOperationRequest::get_FailureCount()
0x38b50  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x38b55  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x38b5a  ldarg.0
0x38b5b  ldstr    aSuccesscount_0// "SuccessCount"
0x38b60  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38b65  ldarg.3
0x38b66  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.StatusUpdateBulkOperationRequest::get_SuccessCount()
0x38b6b  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x38b70  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x38b75  ldarg.0
0x38b76  ldarg.3
0x38b77  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x38b7c  ret
```
