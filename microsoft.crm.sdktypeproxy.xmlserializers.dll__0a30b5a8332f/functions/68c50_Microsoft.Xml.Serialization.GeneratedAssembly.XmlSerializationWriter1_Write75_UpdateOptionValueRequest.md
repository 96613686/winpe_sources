# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write75_UpdateOptionValueRequest

- ea: `0x68c50`
- end: `0x68d21`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write75_UpdateOptionValueRequest`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xc40`
- `0x1940`

## callees

- `0x30bf0`
- `0x68c50`

## string_xrefs

- `0x68c95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x68ca5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x68cbb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x68cd1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x68ce9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x68d04`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x68c90`: `UpdateOptionValueRequest`

## pseudocode

```c

```

## disassembly

```asm
0x68c50  ldarg.3
0x68c51  brtrue.s loc_68C60
0x68c53  ldarg.s  4
0x68c55  brfalse.s loc_68C5F
0x68c57  ldarg.0
0x68c58  ldarg.1
0x68c59  ldarg.2
0x68c5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x68c5f  ret
0x68c60  ldarg.s  5
0x68c62  brtrue.s loc_68C80
0x68c64  ldarg.3
0x68c65  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x68c6a  stloc.0
0x68c6b  ldloc.0
0x68c6c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Metadata.UpdateOptionValueRequest
0x68c71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68c76  beq.s    loc_68C80
0x68c78  ldarg.0
0x68c79  ldarg.3
0x68c7a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x68c7f  throw
0x68c80  ldarg.0
0x68c81  ldarg.1
0x68c82  ldarg.2
0x68c83  ldarg.3
0x68c84  ldc.i4.0
0x68c85  ldnull
0x68c86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x68c8b  ldarg.s  5
0x68c8d  brfalse.s loc_68C9F
0x68c8f  ldarg.0
0x68c90  ldstr    aUpdateoptionva// "UpdateOptionValueRequest"
0x68c95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x68c9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x68c9f  ldarg.0
0x68ca0  ldstr    aAttributelogic// "AttributeLogicalName"
0x68ca5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x68caa  ldarg.3
0x68cab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Metadata.UpdateOptionValueRequest::get_AttributeLogicalName()
0x68cb0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x68cb5  ldarg.0
0x68cb6  ldstr    aEntitylogicaln// "EntityLogicalName"
0x68cbb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x68cc0  ldarg.3
0x68cc1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Metadata.UpdateOptionValueRequest::get_EntityLogicalName()
0x68cc6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x68ccb  ldarg.0
0x68ccc  ldstr    aLabel// "Label"
0x68cd1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x68cd6  ldarg.3
0x68cd7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Metadata.UpdateOptionValueRequest::get_Label()
0x68cdc  ldc.i4.0
0x68cdd  ldc.i4.0
0x68cde  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x68ce3  ldarg.0
0x68ce4  ldstr    aValue// "Value"
0x68ce9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x68cee  ldarg.3
0x68cef  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Metadata.UpdateOptionValueRequest::get_Value()
0x68cf4  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x68cf9  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x68cfe  ldarg.0
0x68cff  ldstr    aMergelabels// "MergeLabels"
0x68d04  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x68d09  ldarg.3
0x68d0a  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Metadata.UpdateOptionValueRequest::get_MergeLabels()
0x68d0f  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x68d14  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x68d19  ldarg.0
0x68d1a  ldarg.3
0x68d1b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x68d20  ret
```
