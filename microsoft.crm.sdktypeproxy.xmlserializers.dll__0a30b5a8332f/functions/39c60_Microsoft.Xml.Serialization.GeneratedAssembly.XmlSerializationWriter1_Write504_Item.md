# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write504_Item

- ea: `0x39c60`
- end: `0x39d4e`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write504_Item`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x19320`
- `0x2fdf0`
- `0x39c60`

## string_xrefs

- `0x39ca5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x39cbf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x39cd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x39cfa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x39d15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x39d31`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x39d10`: `MailMergeTemplateState`
- `0x39ca0`: `SetStateMailMergeTemplateRequest`
- `0x39d2c`: `MailMergeTemplateStatus`

## pseudocode

```c

```

## disassembly

```asm
0x39c60  ldarg.3
0x39c61  brtrue.s loc_39C70
0x39c63  ldarg.s  4
0x39c65  brfalse.s loc_39C6F
0x39c67  ldarg.0
0x39c68  ldarg.1
0x39c69  ldarg.2
0x39c6a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x39c6f  ret
0x39c70  ldarg.s  5
0x39c72  brtrue.s loc_39C90
0x39c74  ldarg.3
0x39c75  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x39c7a  stloc.0
0x39c7b  ldloc.0
0x39c7c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateMailMergeTemplateRequest
0x39c81  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x39c86  beq.s    loc_39C90
0x39c88  ldarg.0
0x39c89  ldarg.3
0x39c8a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x39c8f  throw
0x39c90  ldarg.0
0x39c91  ldarg.1
0x39c92  ldarg.2
0x39c93  ldarg.3
0x39c94  ldc.i4.0
0x39c95  ldnull
0x39c96  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x39c9b  ldarg.s  5
0x39c9d  brfalse.s loc_39CAF
0x39c9f  ldarg.0
0x39ca0  ldstr    aSetstatemailme// "SetStateMailMergeTemplateRequest"
0x39ca5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x39caa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x39caf  ldarg.3
0x39cb0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x39cb5  stloc.1
0x39cb6  ldloc.1
0x39cb7  brfalse.s loc_39CF4
0x39cb9  ldarg.0
0x39cba  ldstr    aOptionalparame_0// "OptionalParameters"
0x39cbf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x39cc4  ldnull
0x39cc5  ldc.i4.0
0x39cc6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x39ccb  ldc.i4.0
0x39ccc  stloc.2
0x39ccd  br.s     loc_39CE8
0x39ccf  ldarg.0
0x39cd0  ldstr    aOptionalparame// "OptionalParameter"
0x39cd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x39cda  ldloc.1
0x39cdb  ldloc.2
0x39cdc  ldelem.ref
0x39cdd  ldc.i4.1
0x39cde  ldc.i4.0
0x39cdf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x39ce4  ldloc.2
0x39ce5  ldc.i4.1
0x39ce6  add
0x39ce7  stloc.2
0x39ce8  ldloc.2
0x39ce9  ldloc.1
0x39cea  ldlen
0x39ceb  conv.i4
0x39cec  blt.s    loc_39CCF
0x39cee  ldarg.0
0x39cef  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x39cf4  ldarg.0
0x39cf5  ldstr    aEntityid// "EntityId"
0x39cfa  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x39cff  ldarg.3
0x39d00  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateMailMergeTemplateRequest::get_EntityId()
0x39d05  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x39d0a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x39d0f  ldarg.0
0x39d10  ldstr    aMailmergetempl// "MailMergeTemplateState"
0x39d15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x39d1a  ldarg.0
0x39d1b  ldarg.3
0x39d1c  callvirt instance valuetype [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MailMergeTemplateState [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateMailMergeTemplateRequest::get_MailMergeTemplateState()
0x39d21  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write305_MailMergeTemplateState(valuetype [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MailMergeTemplateState v)
0x39d26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x39d2b  ldarg.0
0x39d2c  ldstr    aMailmergetempl_4// "MailMergeTemplateStatus"
0x39d31  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x39d36  ldarg.3
0x39d37  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateMailMergeTemplateRequest::get_MailMergeTemplateStatus()
0x39d3c  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x39d41  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x39d46  ldarg.0
0x39d47  ldarg.3
0x39d48  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x39d4d  ret
```
