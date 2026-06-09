# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write321_kbarticletemplate

- ea: `0x249e0`
- end: `0x24b7f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write321_kbarticletemplate`
- size: `415`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36de0`
- `0x56270`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x153c0`
- `0x249e0`

## string_xrefs

- `0x24a25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24a35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24a4d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24a65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24a7b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24a91`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24aa9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24ac1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24ad9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24af1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24b09`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24b21`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24b39`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24b51`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24b67`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24a30`: `createdby`
- `0x24a48`: `createdon`
- `0x24b34`: `overriddencreatedon`
- `0x24a20`: `kbarticletemplate`
- `0x24a76`: `formatxml`
- `0x24abc`: `kbarticletemplateid`
- `0x24b4c`: `structurexml`

## pseudocode

```c

```

## disassembly

```asm
0x249e0  ldarg.3
0x249e1  brtrue.s loc_249F0
0x249e3  ldarg.s  4
0x249e5  brfalse.s loc_249EF
0x249e7  ldarg.0
0x249e8  ldarg.1
0x249e9  ldarg.2
0x249ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x249ef  ret
0x249f0  ldarg.s  5
0x249f2  brtrue.s loc_24A10
0x249f4  ldarg.3
0x249f5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x249fa  stloc.0
0x249fb  ldloc.0
0x249fc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate
0x24a01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24a06  beq.s    loc_24A10
0x24a08  ldarg.0
0x24a09  ldarg.3
0x24a0a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x24a0f  throw
0x24a10  ldarg.0
0x24a11  ldarg.1
0x24a12  ldarg.2
0x24a13  ldarg.3
0x24a14  ldc.i4.0
0x24a15  ldnull
0x24a16  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x24a1b  ldarg.s  5
0x24a1d  brfalse.s loc_24A2F
0x24a1f  ldarg.0
0x24a20  ldstr    aKbarticletempl// "kbarticletemplate"
0x24a25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24a2a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x24a2f  ldarg.0
0x24a30  ldstr    aCreatedby// "createdby"
0x24a35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24a3a  ldarg.3
0x24a3b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_createdby()
0x24a40  ldc.i4.0
0x24a41  ldc.i4.0
0x24a42  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24a47  ldarg.0
0x24a48  ldstr    aCreatedon// "createdon"
0x24a4d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24a52  ldarg.3
0x24a53  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_createdon()
0x24a58  ldc.i4.0
0x24a59  ldc.i4.0
0x24a5a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x24a5f  ldarg.0
0x24a60  ldstr    aDescription_0// "description"
0x24a65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24a6a  ldarg.3
0x24a6b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_description()
0x24a70  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24a75  ldarg.0
0x24a76  ldstr    aFormatxml// "formatxml"
0x24a7b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24a80  ldarg.3
0x24a81  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_formatxml()
0x24a86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24a8b  ldarg.0
0x24a8c  ldstr    aImportsequence// "importsequencenumber"
0x24a91  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24a96  ldarg.3
0x24a97  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_importsequencenumber()
0x24a9c  ldc.i4.0
0x24a9d  ldc.i4.0
0x24a9e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x24aa3  ldarg.0
0x24aa4  ldstr    aIsactive// "isactive"
0x24aa9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24aae  ldarg.3
0x24aaf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_isactive()
0x24ab4  ldc.i4.0
0x24ab5  ldc.i4.0
0x24ab6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x24abb  ldarg.0
0x24abc  ldstr    aKbarticletempl_0// "kbarticletemplateid"
0x24ac1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24ac6  ldarg.3
0x24ac7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_kbarticletemplateid()
0x24acc  ldc.i4.0
0x24acd  ldc.i4.0
0x24ace  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x24ad3  ldarg.0
0x24ad4  ldstr    aLanguagecode_0// "languagecode"
0x24ad9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24ade  ldarg.3
0x24adf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_languagecode()
0x24ae4  ldc.i4.0
0x24ae5  ldc.i4.0
0x24ae6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x24aeb  ldarg.0
0x24aec  ldstr    aModifiedby// "modifiedby"
0x24af1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24af6  ldarg.3
0x24af7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_modifiedby()
0x24afc  ldc.i4.0
0x24afd  ldc.i4.0
0x24afe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24b03  ldarg.0
0x24b04  ldstr    aModifiedon// "modifiedon"
0x24b09  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24b0e  ldarg.3
0x24b0f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_modifiedon()
0x24b14  ldc.i4.0
0x24b15  ldc.i4.0
0x24b16  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x24b1b  ldarg.0
0x24b1c  ldstr    aOrganizationid// "organizationid"
0x24b21  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24b26  ldarg.3
0x24b27  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_organizationid()
0x24b2c  ldc.i4.0
0x24b2d  ldc.i4.0
0x24b2e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24b33  ldarg.0
0x24b34  ldstr    aOverriddencrea// "overriddencreatedon"
0x24b39  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24b3e  ldarg.3
0x24b3f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_overriddencreatedon()
0x24b44  ldc.i4.0
0x24b45  ldc.i4.0
0x24b46  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x24b4b  ldarg.0
0x24b4c  ldstr    aStructurexml// "structurexml"
0x24b51  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24b56  ldarg.3
0x24b57  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_structurexml()
0x24b5c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24b61  ldarg.0
0x24b62  ldstr    aTitle// "title"
0x24b67  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24b6c  ldarg.3
0x24b6d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticletemplate::get_title()
0x24b72  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24b77  ldarg.0
0x24b78  ldarg.3
0x24b79  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x24b7e  ret
```
