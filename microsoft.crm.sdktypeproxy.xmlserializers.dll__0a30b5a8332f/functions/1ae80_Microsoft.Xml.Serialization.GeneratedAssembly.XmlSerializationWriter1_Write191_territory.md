# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write191_territory

- ea: `0x1ae80`
- end: `0x1afdb`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write191_territory`
- size: `347`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x358e0`
- `0x54c90`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x1ae80`

## string_xrefs

- `0x1aec5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1aed5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1aeed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1af05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1af1b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1af33`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1af4b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1af63`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1af7b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1af91`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1afa9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1afc1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1aed0`: `createdby`
- `0x1aee8`: `createdon`
- `0x1afa4`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x1ae80  ldarg.3
0x1ae81  brtrue.s loc_1AE90
0x1ae83  ldarg.s  4
0x1ae85  brfalse.s loc_1AE8F
0x1ae87  ldarg.0
0x1ae88  ldarg.1
0x1ae89  ldarg.2
0x1ae8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1ae8f  ret
0x1ae90  ldarg.s  5
0x1ae92  brtrue.s loc_1AEB0
0x1ae94  ldarg.3
0x1ae95  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1ae9a  stloc.0
0x1ae9b  ldloc.0
0x1ae9c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory
0x1aea1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1aea6  beq.s    loc_1AEB0
0x1aea8  ldarg.0
0x1aea9  ldarg.3
0x1aeaa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1aeaf  throw
0x1aeb0  ldarg.0
0x1aeb1  ldarg.1
0x1aeb2  ldarg.2
0x1aeb3  ldarg.3
0x1aeb4  ldc.i4.0
0x1aeb5  ldnull
0x1aeb6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1aebb  ldarg.s  5
0x1aebd  brfalse.s loc_1AECF
0x1aebf  ldarg.0
0x1aec0  ldstr    aTerritory// "territory"
0x1aec5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1aeca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1aecf  ldarg.0
0x1aed0  ldstr    aCreatedby// "createdby"
0x1aed5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1aeda  ldarg.3
0x1aedb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory::get_createdby()
0x1aee0  ldc.i4.0
0x1aee1  ldc.i4.0
0x1aee2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1aee7  ldarg.0
0x1aee8  ldstr    aCreatedon// "createdon"
0x1aeed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1aef2  ldarg.3
0x1aef3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory::get_createdon()
0x1aef8  ldc.i4.0
0x1aef9  ldc.i4.0
0x1aefa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1aeff  ldarg.0
0x1af00  ldstr    aDescription_0// "description"
0x1af05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1af0a  ldarg.3
0x1af0b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory::get_description()
0x1af10  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1af15  ldarg.0
0x1af16  ldstr    aImportsequence// "importsequencenumber"
0x1af1b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1af20  ldarg.3
0x1af21  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory::get_importsequencenumber()
0x1af26  ldc.i4.0
0x1af27  ldc.i4.0
0x1af28  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1af2d  ldarg.0
0x1af2e  ldstr    aManagerid// "managerid"
0x1af33  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1af38  ldarg.3
0x1af39  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory::get_managerid()
0x1af3e  ldc.i4.0
0x1af3f  ldc.i4.0
0x1af40  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1af45  ldarg.0
0x1af46  ldstr    aModifiedby// "modifiedby"
0x1af4b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1af50  ldarg.3
0x1af51  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory::get_modifiedby()
0x1af56  ldc.i4.0
0x1af57  ldc.i4.0
0x1af58  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1af5d  ldarg.0
0x1af5e  ldstr    aModifiedon// "modifiedon"
0x1af63  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1af68  ldarg.3
0x1af69  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory::get_modifiedon()
0x1af6e  ldc.i4.0
0x1af6f  ldc.i4.0
0x1af70  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1af75  ldarg.0
0x1af76  ldstr    aName// "name"
0x1af7b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1af80  ldarg.3
0x1af81  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory::get_name()
0x1af86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1af8b  ldarg.0
0x1af8c  ldstr    aOrganizationid// "organizationid"
0x1af91  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1af96  ldarg.3
0x1af97  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory::get_organizationid()
0x1af9c  ldc.i4.0
0x1af9d  ldc.i4.0
0x1af9e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1afa3  ldarg.0
0x1afa4  ldstr    aOverriddencrea// "overriddencreatedon"
0x1afa9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1afae  ldarg.3
0x1afaf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory::get_overriddencreatedon()
0x1afb4  ldc.i4.0
0x1afb5  ldc.i4.0
0x1afb6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1afbb  ldarg.0
0x1afbc  ldstr    aTerritoryid// "territoryid"
0x1afc1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1afc6  ldarg.3
0x1afc7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.territory::get_territoryid()
0x1afcc  ldc.i4.0
0x1afcd  ldc.i4.0
0x1afce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1afd3  ldarg.0
0x1afd4  ldarg.3
0x1afd5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1afda  ret
```
