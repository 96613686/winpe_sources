# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write307_mailmergetemplate

- ea: `0x23400`
- end: `0x23689`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write307_mailmergetemplate`
- size: `649`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36c20`
- `0x56040`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x167c0`
- `0x16a10`
- `0x16cb0`
- `0x23400`
- `0x23690`

## string_xrefs

- `0x23445`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23455`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2346b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23483`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2349b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x234b1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x234c7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x234df`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x234f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2350d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23525`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2353d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23555`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2356d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23583`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2359b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x235b3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x235c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x235e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x235f9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2360f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23627`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2363f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23657`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2366f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23466`: `createdby`
- `0x2347e`: `createdon`
- `0x23440`: `mailmergetemplate`
- `0x2363a`: `templatetypecode`
- `0x23538`: `mailmergetemplateid`
- `0x235f4`: `parameterxml`

## pseudocode

```c

```

## disassembly

```asm
0x23400  ldarg.3
0x23401  brtrue.s loc_23410
0x23403  ldarg.s  4
0x23405  brfalse.s loc_2340F
0x23407  ldarg.0
0x23408  ldarg.1
0x23409  ldarg.2
0x2340a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2340f  ret
0x23410  ldarg.s  5
0x23412  brtrue.s loc_23430
0x23414  ldarg.3
0x23415  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2341a  stloc.0
0x2341b  ldloc.0
0x2341c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate
0x23421  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23426  beq.s    loc_23430
0x23428  ldarg.0
0x23429  ldarg.3
0x2342a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2342f  throw
0x23430  ldarg.0
0x23431  ldarg.1
0x23432  ldarg.2
0x23433  ldarg.3
0x23434  ldc.i4.0
0x23435  ldnull
0x23436  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2343b  ldarg.s  5
0x2343d  brfalse.s loc_2344F
0x2343f  ldarg.0
0x23440  ldstr    aMailmergetempl_0// "mailmergetemplate"
0x23445  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2344a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2344f  ldarg.0
0x23450  ldstr    aBody// "body"
0x23455  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2345a  ldarg.3
0x2345b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_body()
0x23460  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x23465  ldarg.0
0x23466  ldstr    aCreatedby// "createdby"
0x2346b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23470  ldarg.3
0x23471  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_createdby()
0x23476  ldc.i4.0
0x23477  ldc.i4.0
0x23478  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2347d  ldarg.0
0x2347e  ldstr    aCreatedon// "createdon"
0x23483  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23488  ldarg.3
0x23489  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_createdon()
0x2348e  ldc.i4.0
0x2348f  ldc.i4.0
0x23490  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x23495  ldarg.0
0x23496  ldstr    aDefaultfilter// "defaultfilter"
0x2349b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x234a0  ldarg.3
0x234a1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_defaultfilter()
0x234a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x234ab  ldarg.0
0x234ac  ldstr    aDescription_0// "description"
0x234b1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x234b6  ldarg.3
0x234b7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_description()
0x234bc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x234c1  ldarg.0
0x234c2  ldstr    aDocumentformat// "documentformat"
0x234c7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x234cc  ldarg.3
0x234cd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_documentformat()
0x234d2  ldc.i4.0
0x234d3  ldc.i4.0
0x234d4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x234d9  ldarg.0
0x234da  ldstr    aFilename// "filename"
0x234df  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x234e4  ldarg.3
0x234e5  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_filename()
0x234ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x234ef  ldarg.0
0x234f0  ldstr    aFilesize// "filesize"
0x234f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x234fa  ldarg.3
0x234fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_filesize()
0x23500  ldc.i4.0
0x23501  ldc.i4.0
0x23502  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x23507  ldarg.0
0x23508  ldstr    aIspersonal// "ispersonal"
0x2350d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23512  ldarg.3
0x23513  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_ispersonal()
0x23518  ldc.i4.0
0x23519  ldc.i4.0
0x2351a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2351f  ldarg.0
0x23520  ldstr    aLanguagecode_0// "languagecode"
0x23525  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2352a  ldarg.3
0x2352b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_languagecode()
0x23530  ldc.i4.0
0x23531  ldc.i4.0
0x23532  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x23537  ldarg.0
0x23538  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x2353d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23542  ldarg.3
0x23543  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_mailmergetemplateid()
0x23548  ldc.i4.0
0x23549  ldc.i4.0
0x2354a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2354f  ldarg.0
0x23550  ldstr    aMailmergetype// "mailmergetype"
0x23555  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2355a  ldarg.3
0x2355b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_mailmergetype()
0x23560  ldc.i4.0
0x23561  ldc.i4.0
0x23562  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x23567  ldarg.0
0x23568  ldstr    aMimetype// "mimetype"
0x2356d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23572  ldarg.3
0x23573  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_mimetype()
0x23578  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2357d  ldarg.0
0x2357e  ldstr    aModifiedby// "modifiedby"
0x23583  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23588  ldarg.3
0x23589  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_modifiedby()
0x2358e  ldc.i4.0
0x2358f  ldc.i4.0
0x23590  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x23595  ldarg.0
0x23596  ldstr    aModifiedon// "modifiedon"
0x2359b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x235a0  ldarg.3
0x235a1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_modifiedon()
0x235a6  ldc.i4.0
0x235a7  ldc.i4.0
0x235a8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x235ad  ldarg.0
0x235ae  ldstr    aName// "name"
0x235b3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x235b8  ldarg.3
0x235b9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_name()
0x235be  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x235c3  ldarg.0
0x235c4  ldstr    aOwnerid// "ownerid"
0x235c9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x235ce  ldarg.3
0x235cf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_ownerid()
0x235d4  ldc.i4.0
0x235d5  ldc.i4.0
0x235d6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x235db  ldarg.0
0x235dc  ldstr    aOwningbusiness// "owningbusinessunit"
0x235e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x235e6  ldarg.3
0x235e7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_owningbusinessunit()
0x235ec  ldc.i4.0
0x235ed  ldc.i4.0
0x235ee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x235f3  ldarg.0
0x235f4  ldstr    aParameterxml// "parameterxml"
0x235f9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x235fe  ldarg.3
0x235ff  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_parameterxml()
0x23604  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x23609  ldarg.0
0x2360a  ldstr    aStatecode// "statecode"
0x2360f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23614  ldarg.3
0x23615  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MailMergeTemplateStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_statecode()
0x2361a  ldc.i4.0
0x2361b  ldc.i4.0
0x2361c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write306_MailMergeTemplateStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MailMergeTemplateStateInfo o, bool isNullable, bool needType)
0x23621  ldarg.0
0x23622  ldstr    aStatuscode// "statuscode"
0x23627  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2362c  ldarg.3
0x2362d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_statuscode()
0x23632  ldc.i4.0
0x23633  ldc.i4.0
0x23634  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x23639  ldarg.0
0x2363a  ldstr    aTemplatetypeco// "templatetypecode"
0x2363f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23644  ldarg.3
0x23645  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_templatetypecode()
0x2364a  ldc.i4.0
0x2364b  ldc.i4.0
0x2364c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write135_EntityNameReference(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference o, bool isNullable, bool needType)
0x23651  ldarg.0
0x23652  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x23657  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2365c  ldarg.3
0x2365d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_timezoneruleversionnumber()
0x23662  ldc.i4.0
0x23663  ldc.i4.0
0x23664  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x23669  ldarg.0
0x2366a  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x2366f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23674  ldarg.3
0x23675  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.mailmergetemplate::get_utcconversiontimezonecode()
0x2367a  ldc.i4.0
0x2367b  ldc.i4.0
0x2367c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x23681  ldarg.0
0x23682  ldarg.3
0x23683  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x23688  ret
```
