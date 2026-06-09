# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write193_template

- ea: `0x1afe0`
- end: `0x1b1f1`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write193_template`
- size: `529`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35950`
- `0x54d00`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x153c0`
- `0x167c0`
- `0x16a10`
- `0x1afe0`

## string_xrefs

- `0x1b025`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b035`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b04b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b063`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b07b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b091`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b0a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b0c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b0d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b0f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b107`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b11f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b137`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b14f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b167`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b17d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b193`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b1a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b1c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b1d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b046`: `createdby`
- `0x1b05e`: `createdon`
- `0x1b020`: `template`
- `0x1b162`: `presentationxml`
- `0x1b18e`: `subjectpresentationxml`
- `0x1b1a4`: `templateid`
- `0x1b1bc`: `templatetypecode`

## pseudocode

```c

```

## disassembly

```asm
0x1afe0  ldarg.3
0x1afe1  brtrue.s loc_1AFF0
0x1afe3  ldarg.s  4
0x1afe5  brfalse.s loc_1AFEF
0x1afe7  ldarg.0
0x1afe8  ldarg.1
0x1afe9  ldarg.2
0x1afea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1afef  ret
0x1aff0  ldarg.s  5
0x1aff2  brtrue.s loc_1B010
0x1aff4  ldarg.3
0x1aff5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1affa  stloc.0
0x1affb  ldloc.0
0x1affc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template
0x1b001  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b006  beq.s    loc_1B010
0x1b008  ldarg.0
0x1b009  ldarg.3
0x1b00a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1b00f  throw
0x1b010  ldarg.0
0x1b011  ldarg.1
0x1b012  ldarg.2
0x1b013  ldarg.3
0x1b014  ldc.i4.0
0x1b015  ldnull
0x1b016  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1b01b  ldarg.s  5
0x1b01d  brfalse.s loc_1B02F
0x1b01f  ldarg.0
0x1b020  ldstr    aTemplate// "template"
0x1b025  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b02a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1b02f  ldarg.0
0x1b030  ldstr    aBody// "body"
0x1b035  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b03a  ldarg.3
0x1b03b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_body()
0x1b040  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b045  ldarg.0
0x1b046  ldstr    aCreatedby// "createdby"
0x1b04b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b050  ldarg.3
0x1b051  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_createdby()
0x1b056  ldc.i4.0
0x1b057  ldc.i4.0
0x1b058  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1b05d  ldarg.0
0x1b05e  ldstr    aCreatedon// "createdon"
0x1b063  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b068  ldarg.3
0x1b069  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_createdon()
0x1b06e  ldc.i4.0
0x1b06f  ldc.i4.0
0x1b070  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b075  ldarg.0
0x1b076  ldstr    aDescription_0// "description"
0x1b07b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b080  ldarg.3
0x1b081  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_description()
0x1b086  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b08b  ldarg.0
0x1b08c  ldstr    aGenerationtype// "generationtypecode"
0x1b091  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b096  ldarg.3
0x1b097  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_generationtypecode()
0x1b09c  ldc.i4.0
0x1b09d  ldc.i4.0
0x1b09e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1b0a3  ldarg.0
0x1b0a4  ldstr    aImportsequence// "importsequencenumber"
0x1b0a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b0ae  ldarg.3
0x1b0af  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_importsequencenumber()
0x1b0b4  ldc.i4.0
0x1b0b5  ldc.i4.0
0x1b0b6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1b0bb  ldarg.0
0x1b0bc  ldstr    aIspersonal// "ispersonal"
0x1b0c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b0c6  ldarg.3
0x1b0c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_ispersonal()
0x1b0cc  ldc.i4.0
0x1b0cd  ldc.i4.0
0x1b0ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1b0d3  ldarg.0
0x1b0d4  ldstr    aLanguagecode_0// "languagecode"
0x1b0d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b0de  ldarg.3
0x1b0df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_languagecode()
0x1b0e4  ldc.i4.0
0x1b0e5  ldc.i4.0
0x1b0e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1b0eb  ldarg.0
0x1b0ec  ldstr    aMimetype// "mimetype"
0x1b0f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b0f6  ldarg.3
0x1b0f7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_mimetype()
0x1b0fc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b101  ldarg.0
0x1b102  ldstr    aModifiedby// "modifiedby"
0x1b107  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b10c  ldarg.3
0x1b10d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_modifiedby()
0x1b112  ldc.i4.0
0x1b113  ldc.i4.0
0x1b114  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1b119  ldarg.0
0x1b11a  ldstr    aModifiedon// "modifiedon"
0x1b11f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b124  ldarg.3
0x1b125  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_modifiedon()
0x1b12a  ldc.i4.0
0x1b12b  ldc.i4.0
0x1b12c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b131  ldarg.0
0x1b132  ldstr    aOwnerid// "ownerid"
0x1b137  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b13c  ldarg.3
0x1b13d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_ownerid()
0x1b142  ldc.i4.0
0x1b143  ldc.i4.0
0x1b144  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x1b149  ldarg.0
0x1b14a  ldstr    aOwningbusiness// "owningbusinessunit"
0x1b14f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b154  ldarg.3
0x1b155  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_owningbusinessunit()
0x1b15a  ldc.i4.0
0x1b15b  ldc.i4.0
0x1b15c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1b161  ldarg.0
0x1b162  ldstr    aPresentationxm// "presentationxml"
0x1b167  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b16c  ldarg.3
0x1b16d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_presentationxml()
0x1b172  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b177  ldarg.0
0x1b178  ldstr    aSubject// "subject"
0x1b17d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b182  ldarg.3
0x1b183  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_subject()
0x1b188  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b18d  ldarg.0
0x1b18e  ldstr    aSubjectpresent// "subjectpresentationxml"
0x1b193  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b198  ldarg.3
0x1b199  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_subjectpresentationxml()
0x1b19e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b1a3  ldarg.0
0x1b1a4  ldstr    aTemplateid// "templateid"
0x1b1a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b1ae  ldarg.3
0x1b1af  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_templateid()
0x1b1b4  ldc.i4.0
0x1b1b5  ldc.i4.0
0x1b1b6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1b1bb  ldarg.0
0x1b1bc  ldstr    aTemplatetypeco// "templatetypecode"
0x1b1c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b1c6  ldarg.3
0x1b1c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_templatetypecode()
0x1b1cc  ldc.i4.0
0x1b1cd  ldc.i4.0
0x1b1ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write135_EntityNameReference(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference o, bool isNullable, bool needType)
0x1b1d3  ldarg.0
0x1b1d4  ldstr    aTitle// "title"
0x1b1d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b1de  ldarg.3
0x1b1df  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.template::get_title()
0x1b1e4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b1e9  ldarg.0
0x1b1ea  ldarg.3
0x1b1eb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1b1f0  ret
```
