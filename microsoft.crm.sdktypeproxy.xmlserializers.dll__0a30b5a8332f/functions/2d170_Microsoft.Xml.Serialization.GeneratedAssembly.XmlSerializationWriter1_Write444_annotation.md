# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write444_annotation

- ea: `0x2d170`
- end: `0x2d399`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write444_annotation`
- size: `553`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37fd0`
- `0x57540`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x153c0`
- `0x167c0`
- `0x16a10`
- `0x2d170`

## string_xrefs

- `0x2d1b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d1c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d1dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d1f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d20d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d223`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d239`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d251`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d269`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d281`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d297`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d2ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d2c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d2dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d2f3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d30b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d323`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d33b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d353`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d36b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d381`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d1d8`: `createdby`
- `0x2d1f0`: `createdon`
- `0x2d31e`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x2d170  ldarg.3
0x2d171  brtrue.s loc_2D180
0x2d173  ldarg.s  4
0x2d175  brfalse.s loc_2D17F
0x2d177  ldarg.0
0x2d178  ldarg.1
0x2d179  ldarg.2
0x2d17a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2d17f  ret
0x2d180  ldarg.s  5
0x2d182  brtrue.s loc_2D1A0
0x2d184  ldarg.3
0x2d185  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2d18a  stloc.0
0x2d18b  ldloc.0
0x2d18c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation
0x2d191  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d196  beq.s    loc_2D1A0
0x2d198  ldarg.0
0x2d199  ldarg.3
0x2d19a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2d19f  throw
0x2d1a0  ldarg.0
0x2d1a1  ldarg.1
0x2d1a2  ldarg.2
0x2d1a3  ldarg.3
0x2d1a4  ldc.i4.0
0x2d1a5  ldnull
0x2d1a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2d1ab  ldarg.s  5
0x2d1ad  brfalse.s loc_2D1BF
0x2d1af  ldarg.0
0x2d1b0  ldstr    aAnnotation// "annotation"
0x2d1b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d1ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2d1bf  ldarg.0
0x2d1c0  ldstr    aAnnotationid// "annotationid"
0x2d1c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d1ca  ldarg.3
0x2d1cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_annotationid()
0x2d1d0  ldc.i4.0
0x2d1d1  ldc.i4.0
0x2d1d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2d1d7  ldarg.0
0x2d1d8  ldstr    aCreatedby// "createdby"
0x2d1dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d1e2  ldarg.3
0x2d1e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_createdby()
0x2d1e8  ldc.i4.0
0x2d1e9  ldc.i4.0
0x2d1ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2d1ef  ldarg.0
0x2d1f0  ldstr    aCreatedon// "createdon"
0x2d1f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d1fa  ldarg.3
0x2d1fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_createdon()
0x2d200  ldc.i4.0
0x2d201  ldc.i4.0
0x2d202  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2d207  ldarg.0
0x2d208  ldstr    aDocumentbody// "documentbody"
0x2d20d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d212  ldarg.3
0x2d213  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_documentbody()
0x2d218  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2d21d  ldarg.0
0x2d21e  ldstr    aFilename// "filename"
0x2d223  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d228  ldarg.3
0x2d229  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_filename()
0x2d22e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2d233  ldarg.0
0x2d234  ldstr    aFilesize// "filesize"
0x2d239  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d23e  ldarg.3
0x2d23f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_filesize()
0x2d244  ldc.i4.0
0x2d245  ldc.i4.0
0x2d246  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2d24b  ldarg.0
0x2d24c  ldstr    aImportsequence// "importsequencenumber"
0x2d251  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d256  ldarg.3
0x2d257  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_importsequencenumber()
0x2d25c  ldc.i4.0
0x2d25d  ldc.i4.0
0x2d25e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2d263  ldarg.0
0x2d264  ldstr    aIsdocument// "isdocument"
0x2d269  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d26e  ldarg.3
0x2d26f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_isdocument()
0x2d274  ldc.i4.0
0x2d275  ldc.i4.0
0x2d276  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2d27b  ldarg.0
0x2d27c  ldstr    aLangid// "langid"
0x2d281  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d286  ldarg.3
0x2d287  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_langid()
0x2d28c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2d291  ldarg.0
0x2d292  ldstr    aMimetype// "mimetype"
0x2d297  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d29c  ldarg.3
0x2d29d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_mimetype()
0x2d2a2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2d2a7  ldarg.0
0x2d2a8  ldstr    aModifiedby// "modifiedby"
0x2d2ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d2b2  ldarg.3
0x2d2b3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_modifiedby()
0x2d2b8  ldc.i4.0
0x2d2b9  ldc.i4.0
0x2d2ba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2d2bf  ldarg.0
0x2d2c0  ldstr    aModifiedon// "modifiedon"
0x2d2c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d2ca  ldarg.3
0x2d2cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_modifiedon()
0x2d2d0  ldc.i4.0
0x2d2d1  ldc.i4.0
0x2d2d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2d2d7  ldarg.0
0x2d2d8  ldstr    aNotetext// "notetext"
0x2d2dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d2e2  ldarg.3
0x2d2e3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_notetext()
0x2d2e8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2d2ed  ldarg.0
0x2d2ee  ldstr    aObjectid_0// "objectid"
0x2d2f3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d2f8  ldarg.3
0x2d2f9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_objectid()
0x2d2fe  ldc.i4.0
0x2d2ff  ldc.i4.0
0x2d300  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2d305  ldarg.0
0x2d306  ldstr    aObjecttypecode_0// "objecttypecode"
0x2d30b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d310  ldarg.3
0x2d311  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_objecttypecode()
0x2d316  ldc.i4.0
0x2d317  ldc.i4.0
0x2d318  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write135_EntityNameReference(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference o, bool isNullable, bool needType)
0x2d31d  ldarg.0
0x2d31e  ldstr    aOverriddencrea// "overriddencreatedon"
0x2d323  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d328  ldarg.3
0x2d329  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_overriddencreatedon()
0x2d32e  ldc.i4.0
0x2d32f  ldc.i4.0
0x2d330  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2d335  ldarg.0
0x2d336  ldstr    aOwnerid// "ownerid"
0x2d33b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d340  ldarg.3
0x2d341  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_ownerid()
0x2d346  ldc.i4.0
0x2d347  ldc.i4.0
0x2d348  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2d34d  ldarg.0
0x2d34e  ldstr    aOwningbusiness// "owningbusinessunit"
0x2d353  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d358  ldarg.3
0x2d359  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_owningbusinessunit()
0x2d35e  ldc.i4.0
0x2d35f  ldc.i4.0
0x2d360  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2d365  ldarg.0
0x2d366  ldstr    aStepid// "stepid"
0x2d36b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d370  ldarg.3
0x2d371  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_stepid()
0x2d376  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2d37b  ldarg.0
0x2d37c  ldstr    aSubject// "subject"
0x2d381  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d386  ldarg.3
0x2d387  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annotation::get_subject()
0x2d38c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2d391  ldarg.0
0x2d392  ldarg.3
0x2d393  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2d398  ret
```
