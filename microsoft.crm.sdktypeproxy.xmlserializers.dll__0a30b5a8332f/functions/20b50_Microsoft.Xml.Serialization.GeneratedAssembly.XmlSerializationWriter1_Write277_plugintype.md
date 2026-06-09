# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write277_plugintype

- ea: `0x20b50`
- end: `0x20d1b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write277_plugintype`
- size: `459`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x367c0`
- `0x55b70`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x20b50`

## string_xrefs

- `0x20b95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20ba5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20bbb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20bd3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20beb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20c01`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20c19`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20c2f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20c47`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20c5f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20c77`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20c8f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20ca7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20cbf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20cd7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20ced`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20d03`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20bb6`: `createdby`
- `0x20bce`: `createdon`
- `0x20b90`: `plugintype`
- `0x20ca2`: `plugintypeid`
- `0x20c8a`: `pluginassemblyid`
- `0x20cba`: `plugintypeidunique`
- `0x20cd2`: `publickeytoken`

## pseudocode

```c

```

## disassembly

```asm
0x20b50  ldarg.3
0x20b51  brtrue.s loc_20B60
0x20b53  ldarg.s  4
0x20b55  brfalse.s loc_20B5F
0x20b57  ldarg.0
0x20b58  ldarg.1
0x20b59  ldarg.2
0x20b5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x20b5f  ret
0x20b60  ldarg.s  5
0x20b62  brtrue.s loc_20B80
0x20b64  ldarg.3
0x20b65  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20b6a  stloc.0
0x20b6b  ldloc.0
0x20b6c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype
0x20b71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20b76  beq.s    loc_20B80
0x20b78  ldarg.0
0x20b79  ldarg.3
0x20b7a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x20b7f  throw
0x20b80  ldarg.0
0x20b81  ldarg.1
0x20b82  ldarg.2
0x20b83  ldarg.3
0x20b84  ldc.i4.0
0x20b85  ldnull
0x20b86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x20b8b  ldarg.s  5
0x20b8d  brfalse.s loc_20B9F
0x20b8f  ldarg.0
0x20b90  ldstr    aPlugintype// "plugintype"
0x20b95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20b9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x20b9f  ldarg.0
0x20ba0  ldstr    aAssemblyname// "assemblyname"
0x20ba5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20baa  ldarg.3
0x20bab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_assemblyname()
0x20bb0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20bb5  ldarg.0
0x20bb6  ldstr    aCreatedby// "createdby"
0x20bbb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20bc0  ldarg.3
0x20bc1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_createdby()
0x20bc6  ldc.i4.0
0x20bc7  ldc.i4.0
0x20bc8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20bcd  ldarg.0
0x20bce  ldstr    aCreatedon// "createdon"
0x20bd3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20bd8  ldarg.3
0x20bd9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_createdon()
0x20bde  ldc.i4.0
0x20bdf  ldc.i4.0
0x20be0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x20be5  ldarg.0
0x20be6  ldstr    aCulture// "culture"
0x20beb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20bf0  ldarg.3
0x20bf1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_culture()
0x20bf6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20bfb  ldarg.0
0x20bfc  ldstr    aCustomizationl// "customizationlevel"
0x20c01  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20c06  ldarg.3
0x20c07  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_customizationlevel()
0x20c0c  ldc.i4.0
0x20c0d  ldc.i4.0
0x20c0e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x20c13  ldarg.0
0x20c14  ldstr    aFriendlyname// "friendlyname"
0x20c19  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20c1e  ldarg.3
0x20c1f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_friendlyname()
0x20c24  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20c29  ldarg.0
0x20c2a  ldstr    aIsworkflowacti// "isworkflowactivity"
0x20c2f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20c34  ldarg.3
0x20c35  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_isworkflowactivity()
0x20c3a  ldc.i4.0
0x20c3b  ldc.i4.0
0x20c3c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x20c41  ldarg.0
0x20c42  ldstr    aModifiedby// "modifiedby"
0x20c47  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20c4c  ldarg.3
0x20c4d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_modifiedby()
0x20c52  ldc.i4.0
0x20c53  ldc.i4.0
0x20c54  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20c59  ldarg.0
0x20c5a  ldstr    aModifiedon// "modifiedon"
0x20c5f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20c64  ldarg.3
0x20c65  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_modifiedon()
0x20c6a  ldc.i4.0
0x20c6b  ldc.i4.0
0x20c6c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x20c71  ldarg.0
0x20c72  ldstr    aOrganizationid// "organizationid"
0x20c77  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20c7c  ldarg.3
0x20c7d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_organizationid()
0x20c82  ldc.i4.0
0x20c83  ldc.i4.0
0x20c84  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20c89  ldarg.0
0x20c8a  ldstr    aPluginassembly_0// "pluginassemblyid"
0x20c8f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20c94  ldarg.3
0x20c95  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_pluginassemblyid()
0x20c9a  ldc.i4.0
0x20c9b  ldc.i4.0
0x20c9c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20ca1  ldarg.0
0x20ca2  ldstr    aPlugintypeid// "plugintypeid"
0x20ca7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20cac  ldarg.3
0x20cad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_plugintypeid()
0x20cb2  ldc.i4.0
0x20cb3  ldc.i4.0
0x20cb4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x20cb9  ldarg.0
0x20cba  ldstr    aPlugintypeidun// "plugintypeidunique"
0x20cbf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20cc4  ldarg.3
0x20cc5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_plugintypeidunique()
0x20cca  ldc.i4.0
0x20ccb  ldc.i4.0
0x20ccc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x20cd1  ldarg.0
0x20cd2  ldstr    aPublickeytoken// "publickeytoken"
0x20cd7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20cdc  ldarg.3
0x20cdd  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_publickeytoken()
0x20ce2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20ce7  ldarg.0
0x20ce8  ldstr    aTypename// "typename"
0x20ced  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20cf2  ldarg.3
0x20cf3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_typename()
0x20cf8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20cfd  ldarg.0
0x20cfe  ldstr    aVersion// "version"
0x20d03  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20d08  ldarg.3
0x20d09  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.plugintype::get_version()
0x20d0e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20d13  ldarg.0
0x20d14  ldarg.3
0x20d15  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x20d1a  ret
```
