# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write426_businessunitnewsarticle

- ea: `0x2bc10`
- end: `0x2bdf9`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write426_businessunitnewsarticle`
- size: `489`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37d30`
- `0x57230`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x2bc10`

## string_xrefs

- `0x2bc55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bc65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bc7d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bc95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bcab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bcc3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bcd9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bcf1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bd09`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bd21`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bd39`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bd51`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bd69`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bd7f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bd97`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bdaf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bdc7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bddf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bcec`: `createdby`
- `0x2bd04`: `createdon`
- `0x2bd92`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x2bc10  ldarg.3
0x2bc11  brtrue.s loc_2BC20
0x2bc13  ldarg.s  4
0x2bc15  brfalse.s loc_2BC1F
0x2bc17  ldarg.0
0x2bc18  ldarg.1
0x2bc19  ldarg.2
0x2bc1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2bc1f  ret
0x2bc20  ldarg.s  5
0x2bc22  brtrue.s loc_2BC40
0x2bc24  ldarg.3
0x2bc25  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2bc2a  stloc.0
0x2bc2b  ldloc.0
0x2bc2c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle
0x2bc31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bc36  beq.s    loc_2BC40
0x2bc38  ldarg.0
0x2bc39  ldarg.3
0x2bc3a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2bc3f  throw
0x2bc40  ldarg.0
0x2bc41  ldarg.1
0x2bc42  ldarg.2
0x2bc43  ldarg.3
0x2bc44  ldc.i4.0
0x2bc45  ldnull
0x2bc46  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2bc4b  ldarg.s  5
0x2bc4d  brfalse.s loc_2BC5F
0x2bc4f  ldarg.0
0x2bc50  ldstr    aBusinessunitne// "businessunitnewsarticle"
0x2bc55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bc5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2bc5f  ldarg.0
0x2bc60  ldstr    aActiveon// "activeon"
0x2bc65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bc6a  ldarg.3
0x2bc6b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_activeon()
0x2bc70  ldc.i4.0
0x2bc71  ldc.i4.0
0x2bc72  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2bc77  ldarg.0
0x2bc78  ldstr    aActiveuntil// "activeuntil"
0x2bc7d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bc82  ldarg.3
0x2bc83  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_activeuntil()
0x2bc88  ldc.i4.0
0x2bc89  ldc.i4.0
0x2bc8a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2bc8f  ldarg.0
0x2bc90  ldstr    aArticletitle// "articletitle"
0x2bc95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bc9a  ldarg.3
0x2bc9b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_articletitle()
0x2bca0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2bca5  ldarg.0
0x2bca6  ldstr    aArticletypecod// "articletypecode"
0x2bcab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bcb0  ldarg.3
0x2bcb1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_articletypecode()
0x2bcb6  ldc.i4.0
0x2bcb7  ldc.i4.0
0x2bcb8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2bcbd  ldarg.0
0x2bcbe  ldstr    aArticleurl// "articleurl"
0x2bcc3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bcc8  ldarg.3
0x2bcc9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_articleurl()
0x2bcce  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2bcd3  ldarg.0
0x2bcd4  ldstr    aBusinessunitne_0// "businessunitnewsarticleid"
0x2bcd9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bcde  ldarg.3
0x2bcdf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_businessunitnewsarticleid()
0x2bce4  ldc.i4.0
0x2bce5  ldc.i4.0
0x2bce6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2bceb  ldarg.0
0x2bcec  ldstr    aCreatedby// "createdby"
0x2bcf1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bcf6  ldarg.3
0x2bcf7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_createdby()
0x2bcfc  ldc.i4.0
0x2bcfd  ldc.i4.0
0x2bcfe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2bd03  ldarg.0
0x2bd04  ldstr    aCreatedon// "createdon"
0x2bd09  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bd0e  ldarg.3
0x2bd0f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_createdon()
0x2bd14  ldc.i4.0
0x2bd15  ldc.i4.0
0x2bd16  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2bd1b  ldarg.0
0x2bd1c  ldstr    aImportsequence// "importsequencenumber"
0x2bd21  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bd26  ldarg.3
0x2bd27  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_importsequencenumber()
0x2bd2c  ldc.i4.0
0x2bd2d  ldc.i4.0
0x2bd2e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2bd33  ldarg.0
0x2bd34  ldstr    aModifiedby// "modifiedby"
0x2bd39  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bd3e  ldarg.3
0x2bd3f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_modifiedby()
0x2bd44  ldc.i4.0
0x2bd45  ldc.i4.0
0x2bd46  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2bd4b  ldarg.0
0x2bd4c  ldstr    aModifiedon// "modifiedon"
0x2bd51  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bd56  ldarg.3
0x2bd57  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_modifiedon()
0x2bd5c  ldc.i4.0
0x2bd5d  ldc.i4.0
0x2bd5e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2bd63  ldarg.0
0x2bd64  ldstr    aNewsarticle// "newsarticle"
0x2bd69  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bd6e  ldarg.3
0x2bd6f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_newsarticle()
0x2bd74  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2bd79  ldarg.0
0x2bd7a  ldstr    aOrganizationid// "organizationid"
0x2bd7f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bd84  ldarg.3
0x2bd85  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_organizationid()
0x2bd8a  ldc.i4.0
0x2bd8b  ldc.i4.0
0x2bd8c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2bd91  ldarg.0
0x2bd92  ldstr    aOverriddencrea// "overriddencreatedon"
0x2bd97  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bd9c  ldarg.3
0x2bd9d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_overriddencreatedon()
0x2bda2  ldc.i4.0
0x2bda3  ldc.i4.0
0x2bda4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2bda9  ldarg.0
0x2bdaa  ldstr    aShowonhomepage// "showonhomepage"
0x2bdaf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bdb4  ldarg.3
0x2bdb5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_showonhomepage()
0x2bdba  ldc.i4.0
0x2bdbb  ldc.i4.0
0x2bdbc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2bdc1  ldarg.0
0x2bdc2  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x2bdc7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bdcc  ldarg.3
0x2bdcd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_timezoneruleversionnumber()
0x2bdd2  ldc.i4.0
0x2bdd3  ldc.i4.0
0x2bdd4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2bdd9  ldarg.0
0x2bdda  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x2bddf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bde4  ldarg.3
0x2bde5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businessunitnewsarticle::get_utcconversiontimezonecode()
0x2bdea  ldc.i4.0
0x2bdeb  ldc.i4.0
0x2bdec  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2bdf1  ldarg.0
0x2bdf2  ldarg.3
0x2bdf3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2bdf8  ret
```
