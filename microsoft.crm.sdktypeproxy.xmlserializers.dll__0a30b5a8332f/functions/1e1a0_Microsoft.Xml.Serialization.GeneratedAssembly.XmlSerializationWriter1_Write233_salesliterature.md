# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write233_salesliterature

- ea: `0x1e1a0`
- end: `0x1e3b9`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write233_salesliterature`
- size: `537`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36050`
- `0x55400`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x1e1a0`

## string_xrefs

- `0x1e1e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e1f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e20d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e225`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e23b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e253`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e26b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e283`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e29b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e2b3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e2c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e2e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e2f9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e311`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e327`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e33f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e357`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e36f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e387`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e39f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e1f0`: `createdby`
- `0x1e208`: `createdon`
- `0x1e33a`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x1e1a0  ldarg.3
0x1e1a1  brtrue.s loc_1E1B0
0x1e1a3  ldarg.s  4
0x1e1a5  brfalse.s loc_1E1AF
0x1e1a7  ldarg.0
0x1e1a8  ldarg.1
0x1e1a9  ldarg.2
0x1e1aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1e1af  ret
0x1e1b0  ldarg.s  5
0x1e1b2  brtrue.s loc_1E1D0
0x1e1b4  ldarg.3
0x1e1b5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1e1ba  stloc.0
0x1e1bb  ldloc.0
0x1e1bc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature
0x1e1c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e1c6  beq.s    loc_1E1D0
0x1e1c8  ldarg.0
0x1e1c9  ldarg.3
0x1e1ca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1e1cf  throw
0x1e1d0  ldarg.0
0x1e1d1  ldarg.1
0x1e1d2  ldarg.2
0x1e1d3  ldarg.3
0x1e1d4  ldc.i4.0
0x1e1d5  ldnull
0x1e1d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1e1db  ldarg.s  5
0x1e1dd  brfalse.s loc_1E1EF
0x1e1df  ldarg.0
0x1e1e0  ldstr    aSalesliteratur// "salesliterature"
0x1e1e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e1ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1e1ef  ldarg.0
0x1e1f0  ldstr    aCreatedby// "createdby"
0x1e1f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e1fa  ldarg.3
0x1e1fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_createdby()
0x1e200  ldc.i4.0
0x1e201  ldc.i4.0
0x1e202  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e207  ldarg.0
0x1e208  ldstr    aCreatedon// "createdon"
0x1e20d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e212  ldarg.3
0x1e213  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_createdon()
0x1e218  ldc.i4.0
0x1e219  ldc.i4.0
0x1e21a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e21f  ldarg.0
0x1e220  ldstr    aDescription_0// "description"
0x1e225  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e22a  ldarg.3
0x1e22b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_description()
0x1e230  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e235  ldarg.0
0x1e236  ldstr    aEmployeecontac// "employeecontactid"
0x1e23b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e240  ldarg.3
0x1e241  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_employeecontactid()
0x1e246  ldc.i4.0
0x1e247  ldc.i4.0
0x1e248  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e24d  ldarg.0
0x1e24e  ldstr    aExpirationdate// "expirationdate"
0x1e253  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e258  ldarg.3
0x1e259  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_expirationdate()
0x1e25e  ldc.i4.0
0x1e25f  ldc.i4.0
0x1e260  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e265  ldarg.0
0x1e266  ldstr    aHasattachments// "hasattachments"
0x1e26b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e270  ldarg.3
0x1e271  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_hasattachments()
0x1e276  ldc.i4.0
0x1e277  ldc.i4.0
0x1e278  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1e27d  ldarg.0
0x1e27e  ldstr    aImportsequence// "importsequencenumber"
0x1e283  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e288  ldarg.3
0x1e289  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_importsequencenumber()
0x1e28e  ldc.i4.0
0x1e28f  ldc.i4.0
0x1e290  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1e295  ldarg.0
0x1e296  ldstr    aIscustomerview// "iscustomerviewable"
0x1e29b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e2a0  ldarg.3
0x1e2a1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_iscustomerviewable()
0x1e2a6  ldc.i4.0
0x1e2a7  ldc.i4.0
0x1e2a8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1e2ad  ldarg.0
0x1e2ae  ldstr    aKeywords// "keywords"
0x1e2b3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e2b8  ldarg.3
0x1e2b9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_keywords()
0x1e2be  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e2c3  ldarg.0
0x1e2c4  ldstr    aLiteraturetype// "literaturetypecode"
0x1e2c9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e2ce  ldarg.3
0x1e2cf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_literaturetypecode()
0x1e2d4  ldc.i4.0
0x1e2d5  ldc.i4.0
0x1e2d6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1e2db  ldarg.0
0x1e2dc  ldstr    aModifiedby// "modifiedby"
0x1e2e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e2e6  ldarg.3
0x1e2e7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_modifiedby()
0x1e2ec  ldc.i4.0
0x1e2ed  ldc.i4.0
0x1e2ee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e2f3  ldarg.0
0x1e2f4  ldstr    aModifiedon// "modifiedon"
0x1e2f9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e2fe  ldarg.3
0x1e2ff  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_modifiedon()
0x1e304  ldc.i4.0
0x1e305  ldc.i4.0
0x1e306  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e30b  ldarg.0
0x1e30c  ldstr    aName// "name"
0x1e311  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e316  ldarg.3
0x1e317  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_name()
0x1e31c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e321  ldarg.0
0x1e322  ldstr    aOrganizationid// "organizationid"
0x1e327  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e32c  ldarg.3
0x1e32d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_organizationid()
0x1e332  ldc.i4.0
0x1e333  ldc.i4.0
0x1e334  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e339  ldarg.0
0x1e33a  ldstr    aOverriddencrea// "overriddencreatedon"
0x1e33f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e344  ldarg.3
0x1e345  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_overriddencreatedon()
0x1e34a  ldc.i4.0
0x1e34b  ldc.i4.0
0x1e34c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e351  ldarg.0
0x1e352  ldstr    aSalesliteratur_1// "salesliteratureid"
0x1e357  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e35c  ldarg.3
0x1e35d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_salesliteratureid()
0x1e362  ldc.i4.0
0x1e363  ldc.i4.0
0x1e364  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1e369  ldarg.0
0x1e36a  ldstr    aSubjectid// "subjectid"
0x1e36f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e374  ldarg.3
0x1e375  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_subjectid()
0x1e37a  ldc.i4.0
0x1e37b  ldc.i4.0
0x1e37c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e381  ldarg.0
0x1e382  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x1e387  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e38c  ldarg.3
0x1e38d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_timezoneruleversionnumber()
0x1e392  ldc.i4.0
0x1e393  ldc.i4.0
0x1e394  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1e399  ldarg.0
0x1e39a  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x1e39f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e3a4  ldarg.3
0x1e3a5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliterature::get_utcconversiontimezonecode()
0x1e3aa  ldc.i4.0
0x1e3ab  ldc.i4.0
0x1e3ac  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1e3b1  ldarg.0
0x1e3b2  ldarg.3
0x1e3b3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1e3b8  ret
```
