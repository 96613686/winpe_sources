# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write243_reportcategory

- ea: `0x1e9c0`
- end: `0x1eb37`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write243_reportcategory`
- size: `375`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36280`
- `0x54c20`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x1e9c0`

## string_xrefs

- `0x1ea05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ea15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ea2d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ea45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ea5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ea75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ea8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eaa5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eabd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ead5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eaed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eb05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eb1d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ea28`: `createdby`
- `0x1ea40`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x1e9c0  ldarg.3
0x1e9c1  brtrue.s loc_1E9D0
0x1e9c3  ldarg.s  4
0x1e9c5  brfalse.s loc_1E9CF
0x1e9c7  ldarg.0
0x1e9c8  ldarg.1
0x1e9c9  ldarg.2
0x1e9ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1e9cf  ret
0x1e9d0  ldarg.s  5
0x1e9d2  brtrue.s loc_1E9F0
0x1e9d4  ldarg.3
0x1e9d5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1e9da  stloc.0
0x1e9db  ldloc.0
0x1e9dc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory
0x1e9e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e9e6  beq.s    loc_1E9F0
0x1e9e8  ldarg.0
0x1e9e9  ldarg.3
0x1e9ea  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1e9ef  throw
0x1e9f0  ldarg.0
0x1e9f1  ldarg.1
0x1e9f2  ldarg.2
0x1e9f3  ldarg.3
0x1e9f4  ldc.i4.0
0x1e9f5  ldnull
0x1e9f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1e9fb  ldarg.s  5
0x1e9fd  brfalse.s loc_1EA0F
0x1e9ff  ldarg.0
0x1ea00  ldstr    aReportcategory// "reportcategory"
0x1ea05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ea0a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1ea0f  ldarg.0
0x1ea10  ldstr    aCategorycode// "categorycode"
0x1ea15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ea1a  ldarg.3
0x1ea1b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_categorycode()
0x1ea20  ldc.i4.0
0x1ea21  ldc.i4.0
0x1ea22  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1ea27  ldarg.0
0x1ea28  ldstr    aCreatedby// "createdby"
0x1ea2d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ea32  ldarg.3
0x1ea33  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_createdby()
0x1ea38  ldc.i4.0
0x1ea39  ldc.i4.0
0x1ea3a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ea3f  ldarg.0
0x1ea40  ldstr    aCreatedon// "createdon"
0x1ea45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ea4a  ldarg.3
0x1ea4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_createdon()
0x1ea50  ldc.i4.0
0x1ea51  ldc.i4.0
0x1ea52  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ea57  ldarg.0
0x1ea58  ldstr    aImportsequence// "importsequencenumber"
0x1ea5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ea62  ldarg.3
0x1ea63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_importsequencenumber()
0x1ea68  ldc.i4.0
0x1ea69  ldc.i4.0
0x1ea6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ea6f  ldarg.0
0x1ea70  ldstr    aModifiedby// "modifiedby"
0x1ea75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ea7a  ldarg.3
0x1ea7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_modifiedby()
0x1ea80  ldc.i4.0
0x1ea81  ldc.i4.0
0x1ea82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ea87  ldarg.0
0x1ea88  ldstr    aModifiedon// "modifiedon"
0x1ea8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ea92  ldarg.3
0x1ea93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_modifiedon()
0x1ea98  ldc.i4.0
0x1ea99  ldc.i4.0
0x1ea9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ea9f  ldarg.0
0x1eaa0  ldstr    aOwningbusiness// "owningbusinessunit"
0x1eaa5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1eaaa  ldarg.3
0x1eaab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_owningbusinessunit()
0x1eab0  ldc.i4.0
0x1eab1  ldc.i4.0
0x1eab2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1eab7  ldarg.0
0x1eab8  ldstr    aOwninguser// "owninguser"
0x1eabd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1eac2  ldarg.3
0x1eac3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_owninguser()
0x1eac8  ldc.i4.0
0x1eac9  ldc.i4.0
0x1eaca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1eacf  ldarg.0
0x1ead0  ldstr    aReportcategory_0// "reportcategoryid"
0x1ead5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1eada  ldarg.3
0x1eadb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_reportcategoryid()
0x1eae0  ldc.i4.0
0x1eae1  ldc.i4.0
0x1eae2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1eae7  ldarg.0
0x1eae8  ldstr    aReportid// "reportid"
0x1eaed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1eaf2  ldarg.3
0x1eaf3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_reportid()
0x1eaf8  ldc.i4.0
0x1eaf9  ldc.i4.0
0x1eafa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1eaff  ldarg.0
0x1eb00  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x1eb05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1eb0a  ldarg.3
0x1eb0b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_timezoneruleversionnumber()
0x1eb10  ldc.i4.0
0x1eb11  ldc.i4.0
0x1eb12  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1eb17  ldarg.0
0x1eb18  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x1eb1d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1eb22  ldarg.3
0x1eb23  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportcategory::get_utcconversiontimezonecode()
0x1eb28  ldc.i4.0
0x1eb29  ldc.i4.0
0x1eb2a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1eb2f  ldarg.0
0x1eb30  ldarg.3
0x1eb31  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1eb36  ret
```
