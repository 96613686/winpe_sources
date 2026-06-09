# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write195_team

- ea: `0x1b200`
- end: `0x1b371`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write195_team`
- size: `369`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x359c0`
- `0x54d70`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x1b200`

## string_xrefs

- `0x1b245`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b255`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b26d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b285`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b29d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b2b3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b2c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b2e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b2f9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b311`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b327`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b33f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b357`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b268`: `createdby`
- `0x1b280`: `createdon`
- `0x1b33a`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x1b200  ldarg.3
0x1b201  brtrue.s loc_1B210
0x1b203  ldarg.s  4
0x1b205  brfalse.s loc_1B20F
0x1b207  ldarg.0
0x1b208  ldarg.1
0x1b209  ldarg.2
0x1b20a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1b20f  ret
0x1b210  ldarg.s  5
0x1b212  brtrue.s loc_1B230
0x1b214  ldarg.3
0x1b215  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1b21a  stloc.0
0x1b21b  ldloc.0
0x1b21c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team
0x1b221  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b226  beq.s    loc_1B230
0x1b228  ldarg.0
0x1b229  ldarg.3
0x1b22a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1b22f  throw
0x1b230  ldarg.0
0x1b231  ldarg.1
0x1b232  ldarg.2
0x1b233  ldarg.3
0x1b234  ldc.i4.0
0x1b235  ldnull
0x1b236  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1b23b  ldarg.s  5
0x1b23d  brfalse.s loc_1B24F
0x1b23f  ldarg.0
0x1b240  ldstr    aTeam_0// "team"
0x1b245  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b24a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1b24f  ldarg.0
0x1b250  ldstr    aBusinessunitid// "businessunitid"
0x1b255  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b25a  ldarg.3
0x1b25b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_businessunitid()
0x1b260  ldc.i4.0
0x1b261  ldc.i4.0
0x1b262  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1b267  ldarg.0
0x1b268  ldstr    aCreatedby// "createdby"
0x1b26d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b272  ldarg.3
0x1b273  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_createdby()
0x1b278  ldc.i4.0
0x1b279  ldc.i4.0
0x1b27a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1b27f  ldarg.0
0x1b280  ldstr    aCreatedon// "createdon"
0x1b285  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b28a  ldarg.3
0x1b28b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_createdon()
0x1b290  ldc.i4.0
0x1b291  ldc.i4.0
0x1b292  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b297  ldarg.0
0x1b298  ldstr    aDescription_0// "description"
0x1b29d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b2a2  ldarg.3
0x1b2a3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_description()
0x1b2a8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b2ad  ldarg.0
0x1b2ae  ldstr    aEmailaddress// "emailaddress"
0x1b2b3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b2b8  ldarg.3
0x1b2b9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_emailaddress()
0x1b2be  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b2c3  ldarg.0
0x1b2c4  ldstr    aImportsequence// "importsequencenumber"
0x1b2c9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b2ce  ldarg.3
0x1b2cf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_importsequencenumber()
0x1b2d4  ldc.i4.0
0x1b2d5  ldc.i4.0
0x1b2d6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1b2db  ldarg.0
0x1b2dc  ldstr    aModifiedby// "modifiedby"
0x1b2e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b2e6  ldarg.3
0x1b2e7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_modifiedby()
0x1b2ec  ldc.i4.0
0x1b2ed  ldc.i4.0
0x1b2ee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1b2f3  ldarg.0
0x1b2f4  ldstr    aModifiedon// "modifiedon"
0x1b2f9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b2fe  ldarg.3
0x1b2ff  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_modifiedon()
0x1b304  ldc.i4.0
0x1b305  ldc.i4.0
0x1b306  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b30b  ldarg.0
0x1b30c  ldstr    aName// "name"
0x1b311  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b316  ldarg.3
0x1b317  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_name()
0x1b31c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b321  ldarg.0
0x1b322  ldstr    aOrganizationid// "organizationid"
0x1b327  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b32c  ldarg.3
0x1b32d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_organizationid()
0x1b332  ldc.i4.0
0x1b333  ldc.i4.0
0x1b334  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1b339  ldarg.0
0x1b33a  ldstr    aOverriddencrea// "overriddencreatedon"
0x1b33f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b344  ldarg.3
0x1b345  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_overriddencreatedon()
0x1b34a  ldc.i4.0
0x1b34b  ldc.i4.0
0x1b34c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b351  ldarg.0
0x1b352  ldstr    aTeamid// "teamid"
0x1b357  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b35c  ldarg.3
0x1b35d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.team::get_teamid()
0x1b362  ldc.i4.0
0x1b363  ldc.i4.0
0x1b364  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1b369  ldarg.0
0x1b36a  ldarg.3
0x1b36b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1b370  ret
```
