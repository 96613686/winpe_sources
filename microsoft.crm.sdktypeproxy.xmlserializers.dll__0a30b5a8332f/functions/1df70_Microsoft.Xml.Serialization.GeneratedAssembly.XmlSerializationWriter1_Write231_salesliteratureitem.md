# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write231_salesliteratureitem

- ea: `0x1df70`
- end: `0x1e197`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write231_salesliteratureitem`
- size: `551`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35fe0`
- `0x55390`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x1df70`

## string_xrefs

- `0x1dfb5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1dfc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1dfdb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1dff1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e007`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e01f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e037`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e04d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e063`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e07b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e093`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e0ab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e0c3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e0d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e0ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e107`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e11f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e137`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e14f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e167`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e17f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e002`: `createdby`
- `0x1e01a`: `createdon`
- `0x1e132`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x1df70  ldarg.3
0x1df71  brtrue.s loc_1DF80
0x1df73  ldarg.s  4
0x1df75  brfalse.s loc_1DF7F
0x1df77  ldarg.0
0x1df78  ldarg.1
0x1df79  ldarg.2
0x1df7a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1df7f  ret
0x1df80  ldarg.s  5
0x1df82  brtrue.s loc_1DFA0
0x1df84  ldarg.3
0x1df85  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1df8a  stloc.0
0x1df8b  ldloc.0
0x1df8c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem
0x1df91  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1df96  beq.s    loc_1DFA0
0x1df98  ldarg.0
0x1df99  ldarg.3
0x1df9a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1df9f  throw
0x1dfa0  ldarg.0
0x1dfa1  ldarg.1
0x1dfa2  ldarg.2
0x1dfa3  ldarg.3
0x1dfa4  ldc.i4.0
0x1dfa5  ldnull
0x1dfa6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1dfab  ldarg.s  5
0x1dfad  brfalse.s loc_1DFBF
0x1dfaf  ldarg.0
0x1dfb0  ldstr    aSalesliteratur_0// "salesliteratureitem"
0x1dfb5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1dfba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1dfbf  ldarg.0
0x1dfc0  ldstr    aAbstract// "abstract"
0x1dfc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1dfca  ldarg.3
0x1dfcb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_abstract()
0x1dfd0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1dfd5  ldarg.0
0x1dfd6  ldstr    aAttacheddocume// "attacheddocumenturl"
0x1dfdb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1dfe0  ldarg.3
0x1dfe1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_attacheddocumenturl()
0x1dfe6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1dfeb  ldarg.0
0x1dfec  ldstr    aAuthorname// "authorname"
0x1dff1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1dff6  ldarg.3
0x1dff7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_authorname()
0x1dffc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e001  ldarg.0
0x1e002  ldstr    aCreatedby// "createdby"
0x1e007  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e00c  ldarg.3
0x1e00d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_createdby()
0x1e012  ldc.i4.0
0x1e013  ldc.i4.0
0x1e014  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e019  ldarg.0
0x1e01a  ldstr    aCreatedon// "createdon"
0x1e01f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e024  ldarg.3
0x1e025  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_createdon()
0x1e02a  ldc.i4.0
0x1e02b  ldc.i4.0
0x1e02c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e031  ldarg.0
0x1e032  ldstr    aDocumentbody// "documentbody"
0x1e037  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e03c  ldarg.3
0x1e03d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_documentbody()
0x1e042  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e047  ldarg.0
0x1e048  ldstr    aFilename// "filename"
0x1e04d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e052  ldarg.3
0x1e053  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_filename()
0x1e058  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e05d  ldarg.0
0x1e05e  ldstr    aFilesize// "filesize"
0x1e063  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e068  ldarg.3
0x1e069  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_filesize()
0x1e06e  ldc.i4.0
0x1e06f  ldc.i4.0
0x1e070  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1e075  ldarg.0
0x1e076  ldstr    aFiletypecode// "filetypecode"
0x1e07b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e080  ldarg.3
0x1e081  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_filetypecode()
0x1e086  ldc.i4.0
0x1e087  ldc.i4.0
0x1e088  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1e08d  ldarg.0
0x1e08e  ldstr    aImportsequence// "importsequencenumber"
0x1e093  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e098  ldarg.3
0x1e099  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_importsequencenumber()
0x1e09e  ldc.i4.0
0x1e09f  ldc.i4.0
0x1e0a0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1e0a5  ldarg.0
0x1e0a6  ldstr    aIscustomerview// "iscustomerviewable"
0x1e0ab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e0b0  ldarg.3
0x1e0b1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_iscustomerviewable()
0x1e0b6  ldc.i4.0
0x1e0b7  ldc.i4.0
0x1e0b8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1e0bd  ldarg.0
0x1e0be  ldstr    aKeywords// "keywords"
0x1e0c3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e0c8  ldarg.3
0x1e0c9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_keywords()
0x1e0ce  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e0d3  ldarg.0
0x1e0d4  ldstr    aMimetype// "mimetype"
0x1e0d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e0de  ldarg.3
0x1e0df  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_mimetype()
0x1e0e4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e0e9  ldarg.0
0x1e0ea  ldstr    aModifiedby// "modifiedby"
0x1e0ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e0f4  ldarg.3
0x1e0f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_modifiedby()
0x1e0fa  ldc.i4.0
0x1e0fb  ldc.i4.0
0x1e0fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e101  ldarg.0
0x1e102  ldstr    aModifiedon// "modifiedon"
0x1e107  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e10c  ldarg.3
0x1e10d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_modifiedon()
0x1e112  ldc.i4.0
0x1e113  ldc.i4.0
0x1e114  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e119  ldarg.0
0x1e11a  ldstr    aOrganizationid// "organizationid"
0x1e11f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e124  ldarg.3
0x1e125  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_organizationid()
0x1e12a  ldc.i4.0
0x1e12b  ldc.i4.0
0x1e12c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1e131  ldarg.0
0x1e132  ldstr    aOverriddencrea// "overriddencreatedon"
0x1e137  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e13c  ldarg.3
0x1e13d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_overriddencreatedon()
0x1e142  ldc.i4.0
0x1e143  ldc.i4.0
0x1e144  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e149  ldarg.0
0x1e14a  ldstr    aSalesliteratur_1// "salesliteratureid"
0x1e14f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e154  ldarg.3
0x1e155  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_salesliteratureid()
0x1e15a  ldc.i4.0
0x1e15b  ldc.i4.0
0x1e15c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e161  ldarg.0
0x1e162  ldstr    aSalesliteratur_2// "salesliteratureitemid"
0x1e167  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e16c  ldarg.3
0x1e16d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_salesliteratureitemid()
0x1e172  ldc.i4.0
0x1e173  ldc.i4.0
0x1e174  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1e179  ldarg.0
0x1e17a  ldstr    aTitle// "title"
0x1e17f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e184  ldarg.3
0x1e185  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.salesliteratureitem::get_title()
0x1e18a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e18f  ldarg.0
0x1e190  ldarg.3
0x1e191  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1e196  ret
```
