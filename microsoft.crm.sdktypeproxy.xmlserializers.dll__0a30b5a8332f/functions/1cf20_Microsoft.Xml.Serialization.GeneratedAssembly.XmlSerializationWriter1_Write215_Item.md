# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write215_Item

- ea: `0x1cf20`
- end: `0x1d04d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write215_Item`
- size: `301`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35d40`
- `0x550f0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x1cf20`

## string_xrefs

- `0x1cf65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cf75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cf8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cfa5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cfbd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cfd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cfed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d005`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d01d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d035`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cf70`: `createdby`
- `0x1cf88`: `createdon`
- `0x1cf60`: `sdkmessageprocessingstepsecureconfig`
- `0x1d000`: `sdkmessageprocessingstepsecureconfigid`
- `0x1d018`: `sdkmessageprocessingstepsecureconfigidunique`
- `0x1d030`: `secureconfig`

## pseudocode

```c

```

## disassembly

```asm
0x1cf20  ldarg.3
0x1cf21  brtrue.s loc_1CF30
0x1cf23  ldarg.s  4
0x1cf25  brfalse.s loc_1CF2F
0x1cf27  ldarg.0
0x1cf28  ldarg.1
0x1cf29  ldarg.2
0x1cf2a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1cf2f  ret
0x1cf30  ldarg.s  5
0x1cf32  brtrue.s loc_1CF50
0x1cf34  ldarg.3
0x1cf35  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1cf3a  stloc.0
0x1cf3b  ldloc.0
0x1cf3c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepsecureconfig
0x1cf41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1cf46  beq.s    loc_1CF50
0x1cf48  ldarg.0
0x1cf49  ldarg.3
0x1cf4a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1cf4f  throw
0x1cf50  ldarg.0
0x1cf51  ldarg.1
0x1cf52  ldarg.2
0x1cf53  ldarg.3
0x1cf54  ldc.i4.0
0x1cf55  ldnull
0x1cf56  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1cf5b  ldarg.s  5
0x1cf5d  brfalse.s loc_1CF6F
0x1cf5f  ldarg.0
0x1cf60  ldstr    aSdkmessageproc_4// "sdkmessageprocessingstepsecureconfig"
0x1cf65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cf6a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1cf6f  ldarg.0
0x1cf70  ldstr    aCreatedby// "createdby"
0x1cf75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cf7a  ldarg.3
0x1cf7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepsecureconfig::get_createdby()
0x1cf80  ldc.i4.0
0x1cf81  ldc.i4.0
0x1cf82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1cf87  ldarg.0
0x1cf88  ldstr    aCreatedon// "createdon"
0x1cf8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cf92  ldarg.3
0x1cf93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepsecureconfig::get_createdon()
0x1cf98  ldc.i4.0
0x1cf99  ldc.i4.0
0x1cf9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1cf9f  ldarg.0
0x1cfa0  ldstr    aCustomizationl// "customizationlevel"
0x1cfa5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cfaa  ldarg.3
0x1cfab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepsecureconfig::get_customizationlevel()
0x1cfb0  ldc.i4.0
0x1cfb1  ldc.i4.0
0x1cfb2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1cfb7  ldarg.0
0x1cfb8  ldstr    aModifiedby// "modifiedby"
0x1cfbd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cfc2  ldarg.3
0x1cfc3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepsecureconfig::get_modifiedby()
0x1cfc8  ldc.i4.0
0x1cfc9  ldc.i4.0
0x1cfca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1cfcf  ldarg.0
0x1cfd0  ldstr    aModifiedon// "modifiedon"
0x1cfd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cfda  ldarg.3
0x1cfdb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepsecureconfig::get_modifiedon()
0x1cfe0  ldc.i4.0
0x1cfe1  ldc.i4.0
0x1cfe2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1cfe7  ldarg.0
0x1cfe8  ldstr    aOrganizationid// "organizationid"
0x1cfed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cff2  ldarg.3
0x1cff3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepsecureconfig::get_organizationid()
0x1cff8  ldc.i4.0
0x1cff9  ldc.i4.0
0x1cffa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1cfff  ldarg.0
0x1d000  ldstr    aSdkmessageproc_5// "sdkmessageprocessingstepsecureconfigid"
0x1d005  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d00a  ldarg.3
0x1d00b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepsecureconfig::get_sdkmessageprocessingstepsecureconfigid()
0x1d010  ldc.i4.0
0x1d011  ldc.i4.0
0x1d012  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1d017  ldarg.0
0x1d018  ldstr    aSdkmessageproc_6// "sdkmessageprocessingstepsecureconfigidu"...
0x1d01d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d022  ldarg.3
0x1d023  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepsecureconfig::get_sdkmessageprocessingstepsecureconfigidunique()
0x1d028  ldc.i4.0
0x1d029  ldc.i4.0
0x1d02a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1d02f  ldarg.0
0x1d030  ldstr    aSecureconfig// "secureconfig"
0x1d035  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d03a  ldarg.3
0x1d03b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepsecureconfig::get_secureconfig()
0x1d040  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d045  ldarg.0
0x1d046  ldarg.3
0x1d047  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1d04c  ret
```
