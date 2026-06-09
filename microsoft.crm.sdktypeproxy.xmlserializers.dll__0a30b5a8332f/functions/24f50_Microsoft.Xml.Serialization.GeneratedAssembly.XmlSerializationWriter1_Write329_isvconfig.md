# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write329_isvconfig

- ea: `0x24f50`
- end: `0x2504d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write329_isvconfig`
- size: `253`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36f30`
- `0x563c0`

## callees

- `0x5cf0`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x24f50`

## string_xrefs

- `0x24f95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24fa5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24fbb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24fd3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24feb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25003`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2501b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25033`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24fb6`: `createdby`
- `0x24fce`: `createdon`
- `0x24f90`: `isvconfig`
- `0x24fa0`: `configxml`
- `0x24fe6`: `isvconfigid`

## pseudocode

```c

```

## disassembly

```asm
0x24f50  ldarg.3
0x24f51  brtrue.s loc_24F60
0x24f53  ldarg.s  4
0x24f55  brfalse.s loc_24F5F
0x24f57  ldarg.0
0x24f58  ldarg.1
0x24f59  ldarg.2
0x24f5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x24f5f  ret
0x24f60  ldarg.s  5
0x24f62  brtrue.s loc_24F80
0x24f64  ldarg.3
0x24f65  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x24f6a  stloc.0
0x24f6b  ldloc.0
0x24f6c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.isvconfig
0x24f71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24f76  beq.s    loc_24F80
0x24f78  ldarg.0
0x24f79  ldarg.3
0x24f7a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x24f7f  throw
0x24f80  ldarg.0
0x24f81  ldarg.1
0x24f82  ldarg.2
0x24f83  ldarg.3
0x24f84  ldc.i4.0
0x24f85  ldnull
0x24f86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x24f8b  ldarg.s  5
0x24f8d  brfalse.s loc_24F9F
0x24f8f  ldarg.0
0x24f90  ldstr    aIsvconfig// "isvconfig"
0x24f95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24f9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x24f9f  ldarg.0
0x24fa0  ldstr    aConfigxml// "configxml"
0x24fa5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24faa  ldarg.3
0x24fab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.isvconfig::get_configxml()
0x24fb0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24fb5  ldarg.0
0x24fb6  ldstr    aCreatedby// "createdby"
0x24fbb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24fc0  ldarg.3
0x24fc1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.isvconfig::get_createdby()
0x24fc6  ldc.i4.0
0x24fc7  ldc.i4.0
0x24fc8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24fcd  ldarg.0
0x24fce  ldstr    aCreatedon// "createdon"
0x24fd3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24fd8  ldarg.3
0x24fd9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.isvconfig::get_createdon()
0x24fde  ldc.i4.0
0x24fdf  ldc.i4.0
0x24fe0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x24fe5  ldarg.0
0x24fe6  ldstr    aIsvconfigid// "isvconfigid"
0x24feb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24ff0  ldarg.3
0x24ff1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.isvconfig::get_isvconfigid()
0x24ff6  ldc.i4.0
0x24ff7  ldc.i4.0
0x24ff8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x24ffd  ldarg.0
0x24ffe  ldstr    aModifiedby// "modifiedby"
0x25003  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25008  ldarg.3
0x25009  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.isvconfig::get_modifiedby()
0x2500e  ldc.i4.0
0x2500f  ldc.i4.0
0x25010  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25015  ldarg.0
0x25016  ldstr    aModifiedon// "modifiedon"
0x2501b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25020  ldarg.3
0x25021  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.isvconfig::get_modifiedon()
0x25026  ldc.i4.0
0x25027  ldc.i4.0
0x25028  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2502d  ldarg.0
0x2502e  ldstr    aOrganizationid// "organizationid"
0x25033  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25038  ldarg.3
0x25039  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.isvconfig::get_organizationid()
0x2503e  ldc.i4.0
0x2503f  ldc.i4.0
0x25040  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x25045  ldarg.0
0x25046  ldarg.3
0x25047  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2504c  ret
```
