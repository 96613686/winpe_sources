# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write279_pluginassembly

- ea: `0x20d20`
- end: `0x20ee9`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write279_pluginassembly`
- size: `457`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36830`
- `0x55be0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x20d20`

## string_xrefs

- `0x20d65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20d75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20d8b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20da3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20dbb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20dd1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20de9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20e01`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20e19`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20e2f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20e47`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20e5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20e75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20e8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20ea3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20eb9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20ed1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20d86`: `createdby`
- `0x20d9e`: `createdon`
- `0x20d60`: `pluginassembly`
- `0x20e58`: `pluginassemblyid`
- `0x20e88`: `publickeytoken`
- `0x20e70`: `pluginassemblyidunique`

## pseudocode

```c

```

## disassembly

```asm
0x20d20  ldarg.3
0x20d21  brtrue.s loc_20D30
0x20d23  ldarg.s  4
0x20d25  brfalse.s loc_20D2F
0x20d27  ldarg.0
0x20d28  ldarg.1
0x20d29  ldarg.2
0x20d2a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x20d2f  ret
0x20d30  ldarg.s  5
0x20d32  brtrue.s loc_20D50
0x20d34  ldarg.3
0x20d35  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20d3a  stloc.0
0x20d3b  ldloc.0
0x20d3c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly
0x20d41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20d46  beq.s    loc_20D50
0x20d48  ldarg.0
0x20d49  ldarg.3
0x20d4a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x20d4f  throw
0x20d50  ldarg.0
0x20d51  ldarg.1
0x20d52  ldarg.2
0x20d53  ldarg.3
0x20d54  ldc.i4.0
0x20d55  ldnull
0x20d56  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x20d5b  ldarg.s  5
0x20d5d  brfalse.s loc_20D6F
0x20d5f  ldarg.0
0x20d60  ldstr    aPluginassembly// "pluginassembly"
0x20d65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20d6a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x20d6f  ldarg.0
0x20d70  ldstr    aContent// "content"
0x20d75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20d7a  ldarg.3
0x20d7b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_content()
0x20d80  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20d85  ldarg.0
0x20d86  ldstr    aCreatedby// "createdby"
0x20d8b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20d90  ldarg.3
0x20d91  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_createdby()
0x20d96  ldc.i4.0
0x20d97  ldc.i4.0
0x20d98  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20d9d  ldarg.0
0x20d9e  ldstr    aCreatedon// "createdon"
0x20da3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20da8  ldarg.3
0x20da9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_createdon()
0x20dae  ldc.i4.0
0x20daf  ldc.i4.0
0x20db0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x20db5  ldarg.0
0x20db6  ldstr    aCulture// "culture"
0x20dbb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20dc0  ldarg.3
0x20dc1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_culture()
0x20dc6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20dcb  ldarg.0
0x20dcc  ldstr    aCustomizationl// "customizationlevel"
0x20dd1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20dd6  ldarg.3
0x20dd7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_customizationlevel()
0x20ddc  ldc.i4.0
0x20ddd  ldc.i4.0
0x20dde  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x20de3  ldarg.0
0x20de4  ldstr    aModifiedby// "modifiedby"
0x20de9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20dee  ldarg.3
0x20def  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_modifiedby()
0x20df4  ldc.i4.0
0x20df5  ldc.i4.0
0x20df6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20dfb  ldarg.0
0x20dfc  ldstr    aModifiedon// "modifiedon"
0x20e01  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20e06  ldarg.3
0x20e07  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_modifiedon()
0x20e0c  ldc.i4.0
0x20e0d  ldc.i4.0
0x20e0e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x20e13  ldarg.0
0x20e14  ldstr    aName// "name"
0x20e19  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20e1e  ldarg.3
0x20e1f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_name()
0x20e24  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20e29  ldarg.0
0x20e2a  ldstr    aOrganizationid// "organizationid"
0x20e2f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20e34  ldarg.3
0x20e35  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_organizationid()
0x20e3a  ldc.i4.0
0x20e3b  ldc.i4.0
0x20e3c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20e41  ldarg.0
0x20e42  ldstr    aPath// "path"
0x20e47  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20e4c  ldarg.3
0x20e4d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_path()
0x20e52  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20e57  ldarg.0
0x20e58  ldstr    aPluginassembly_0// "pluginassemblyid"
0x20e5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20e62  ldarg.3
0x20e63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_pluginassemblyid()
0x20e68  ldc.i4.0
0x20e69  ldc.i4.0
0x20e6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x20e6f  ldarg.0
0x20e70  ldstr    aPluginassembly_1// "pluginassemblyidunique"
0x20e75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20e7a  ldarg.3
0x20e7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_pluginassemblyidunique()
0x20e80  ldc.i4.0
0x20e81  ldc.i4.0
0x20e82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x20e87  ldarg.0
0x20e88  ldstr    aPublickeytoken// "publickeytoken"
0x20e8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20e92  ldarg.3
0x20e93  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_publickeytoken()
0x20e98  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20e9d  ldarg.0
0x20e9e  ldstr    aSourcehash// "sourcehash"
0x20ea3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20ea8  ldarg.3
0x20ea9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_sourcehash()
0x20eae  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20eb3  ldarg.0
0x20eb4  ldstr    aSourcetype// "sourcetype"
0x20eb9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20ebe  ldarg.3
0x20ebf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_sourcetype()
0x20ec4  ldc.i4.0
0x20ec5  ldc.i4.0
0x20ec6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x20ecb  ldarg.0
0x20ecc  ldstr    aVersion// "version"
0x20ed1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20ed6  ldarg.3
0x20ed7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pluginassembly::get_version()
0x20edc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20ee1  ldarg.0
0x20ee2  ldarg.3
0x20ee3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x20ee8  ret
```
