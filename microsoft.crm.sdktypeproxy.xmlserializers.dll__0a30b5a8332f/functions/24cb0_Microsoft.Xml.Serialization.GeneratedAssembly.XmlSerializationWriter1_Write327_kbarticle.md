# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write327_kbarticle

- ea: `0x24cb0`
- end: `0x24ec1`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write327_kbarticle`
- size: `529`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36ec0`
- `0x56350`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x16cb0`
- `0x24cb0`
- `0x24ed0`

## string_xrefs

- `0x24cf5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24d05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24d1b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24d31`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24d47`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24d5f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24d77`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24d8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24da5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24dbd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24dd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24deb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24e03`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24e1b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24e31`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24e49`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24e61`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24e79`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24e91`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24ea9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24d42`: `createdby`
- `0x24d5a`: `createdon`
- `0x24e44`: `overriddencreatedon`
- `0x24db8`: `kbarticletemplateid`
- `0x24d00`: `articlexml`
- `0x24d16`: `comments`

## pseudocode

```c

```

## disassembly

```asm
0x24cb0  ldarg.3
0x24cb1  brtrue.s loc_24CC0
0x24cb3  ldarg.s  4
0x24cb5  brfalse.s loc_24CBF
0x24cb7  ldarg.0
0x24cb8  ldarg.1
0x24cb9  ldarg.2
0x24cba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x24cbf  ret
0x24cc0  ldarg.s  5
0x24cc2  brtrue.s loc_24CE0
0x24cc4  ldarg.3
0x24cc5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x24cca  stloc.0
0x24ccb  ldloc.0
0x24ccc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle
0x24cd1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24cd6  beq.s    loc_24CE0
0x24cd8  ldarg.0
0x24cd9  ldarg.3
0x24cda  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x24cdf  throw
0x24ce0  ldarg.0
0x24ce1  ldarg.1
0x24ce2  ldarg.2
0x24ce3  ldarg.3
0x24ce4  ldc.i4.0
0x24ce5  ldnull
0x24ce6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x24ceb  ldarg.s  5
0x24ced  brfalse.s loc_24CFF
0x24cef  ldarg.0
0x24cf0  ldstr    aKbarticle// "kbarticle"
0x24cf5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24cfa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x24cff  ldarg.0
0x24d00  ldstr    aArticlexml// "articlexml"
0x24d05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24d0a  ldarg.3
0x24d0b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_articlexml()
0x24d10  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24d15  ldarg.0
0x24d16  ldstr    aComments// "comments"
0x24d1b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24d20  ldarg.3
0x24d21  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_comments()
0x24d26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24d2b  ldarg.0
0x24d2c  ldstr    aContent// "content"
0x24d31  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24d36  ldarg.3
0x24d37  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_content()
0x24d3c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24d41  ldarg.0
0x24d42  ldstr    aCreatedby// "createdby"
0x24d47  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24d4c  ldarg.3
0x24d4d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_createdby()
0x24d52  ldc.i4.0
0x24d53  ldc.i4.0
0x24d54  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24d59  ldarg.0
0x24d5a  ldstr    aCreatedon// "createdon"
0x24d5f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24d64  ldarg.3
0x24d65  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_createdon()
0x24d6a  ldc.i4.0
0x24d6b  ldc.i4.0
0x24d6c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x24d71  ldarg.0
0x24d72  ldstr    aDescription_0// "description"
0x24d77  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24d7c  ldarg.3
0x24d7d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_description()
0x24d82  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24d87  ldarg.0
0x24d88  ldstr    aImportsequence// "importsequencenumber"
0x24d8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24d92  ldarg.3
0x24d93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_importsequencenumber()
0x24d98  ldc.i4.0
0x24d99  ldc.i4.0
0x24d9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x24d9f  ldarg.0
0x24da0  ldstr    aKbarticleid// "kbarticleid"
0x24da5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24daa  ldarg.3
0x24dab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_kbarticleid()
0x24db0  ldc.i4.0
0x24db1  ldc.i4.0
0x24db2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x24db7  ldarg.0
0x24db8  ldstr    aKbarticletempl_0// "kbarticletemplateid"
0x24dbd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24dc2  ldarg.3
0x24dc3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_kbarticletemplateid()
0x24dc8  ldc.i4.0
0x24dc9  ldc.i4.0
0x24dca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24dcf  ldarg.0
0x24dd0  ldstr    aKeywords// "keywords"
0x24dd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24dda  ldarg.3
0x24ddb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_keywords()
0x24de0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24de5  ldarg.0
0x24de6  ldstr    aModifiedby// "modifiedby"
0x24deb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24df0  ldarg.3
0x24df1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_modifiedby()
0x24df6  ldc.i4.0
0x24df7  ldc.i4.0
0x24df8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24dfd  ldarg.0
0x24dfe  ldstr    aModifiedon// "modifiedon"
0x24e03  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24e08  ldarg.3
0x24e09  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_modifiedon()
0x24e0e  ldc.i4.0
0x24e0f  ldc.i4.0
0x24e10  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x24e15  ldarg.0
0x24e16  ldstr    aNumber// "number"
0x24e1b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24e20  ldarg.3
0x24e21  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_number()
0x24e26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24e2b  ldarg.0
0x24e2c  ldstr    aOrganizationid// "organizationid"
0x24e31  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24e36  ldarg.3
0x24e37  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_organizationid()
0x24e3c  ldc.i4.0
0x24e3d  ldc.i4.0
0x24e3e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24e43  ldarg.0
0x24e44  ldstr    aOverriddencrea// "overriddencreatedon"
0x24e49  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24e4e  ldarg.3
0x24e4f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_overriddencreatedon()
0x24e54  ldc.i4.0
0x24e55  ldc.i4.0
0x24e56  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x24e5b  ldarg.0
0x24e5c  ldstr    aStatecode// "statecode"
0x24e61  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24e66  ldarg.3
0x24e67  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.KbArticleStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_statecode()
0x24e6c  ldc.i4.0
0x24e6d  ldc.i4.0
0x24e6e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write326_KbArticleStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.KbArticleStateInfo o, bool isNullable, bool needType)
0x24e73  ldarg.0
0x24e74  ldstr    aStatuscode// "statuscode"
0x24e79  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24e7e  ldarg.3
0x24e7f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_statuscode()
0x24e84  ldc.i4.0
0x24e85  ldc.i4.0
0x24e86  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x24e8b  ldarg.0
0x24e8c  ldstr    aSubjectid// "subjectid"
0x24e91  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24e96  ldarg.3
0x24e97  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_subjectid()
0x24e9c  ldc.i4.0
0x24e9d  ldc.i4.0
0x24e9e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24ea3  ldarg.0
0x24ea4  ldstr    aTitle// "title"
0x24ea9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24eae  ldarg.3
0x24eaf  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticle::get_title()
0x24eb4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24eb9  ldarg.0
0x24eba  ldarg.3
0x24ebb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x24ec0  ret
```
