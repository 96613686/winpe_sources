# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write241_reportentity

- ea: `0x1e860`
- end: `0x1e9bf`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write241_reportentity`
- size: `351`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36210`
- `0x555c0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x167c0`
- `0x1e860`

## string_xrefs

- `0x1e8a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e8b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e8cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e8e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e8fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e915`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e92d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e945`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e95d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e975`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e98d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e9a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e8b0`: `createdby`
- `0x1e8c8`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x1e860  ldarg.3
0x1e861  brtrue.s loc_1E870
0x1e863  ldarg.s  4
0x1e865  brfalse.s loc_1E86F
0x1e867  ldarg.0
0x1e868  ldarg.1
0x1e869  ldarg.2
0x1e86a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1e86f  ret
0x1e870  ldarg.s  5
0x1e872  brtrue.s loc_1E890
0x1e874  ldarg.3
0x1e875  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1e87a  stloc.0
0x1e87b  ldloc.0
0x1e87c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity
0x1e881  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e886  beq.s    loc_1E890
0x1e888  ldarg.0
0x1e889  ldarg.3
0x1e88a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1e88f  throw
0x1e890  ldarg.0
0x1e891  ldarg.1
0x1e892  ldarg.2
0x1e893  ldarg.3
0x1e894  ldc.i4.0
0x1e895  ldnull
0x1e896  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1e89b  ldarg.s  5
0x1e89d  brfalse.s loc_1E8AF
0x1e89f  ldarg.0
0x1e8a0  ldstr    aReportentity// "reportentity"
0x1e8a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e8aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1e8af  ldarg.0
0x1e8b0  ldstr    aCreatedby// "createdby"
0x1e8b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e8ba  ldarg.3
0x1e8bb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity::get_createdby()
0x1e8c0  ldc.i4.0
0x1e8c1  ldc.i4.0
0x1e8c2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e8c7  ldarg.0
0x1e8c8  ldstr    aCreatedon// "createdon"
0x1e8cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e8d2  ldarg.3
0x1e8d3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity::get_createdon()
0x1e8d8  ldc.i4.0
0x1e8d9  ldc.i4.0
0x1e8da  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e8df  ldarg.0
0x1e8e0  ldstr    aImportsequence// "importsequencenumber"
0x1e8e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e8ea  ldarg.3
0x1e8eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity::get_importsequencenumber()
0x1e8f0  ldc.i4.0
0x1e8f1  ldc.i4.0
0x1e8f2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1e8f7  ldarg.0
0x1e8f8  ldstr    aIsfilterable// "isfilterable"
0x1e8fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e902  ldarg.3
0x1e903  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity::get_isfilterable()
0x1e908  ldc.i4.0
0x1e909  ldc.i4.0
0x1e90a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1e90f  ldarg.0
0x1e910  ldstr    aModifiedby// "modifiedby"
0x1e915  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e91a  ldarg.3
0x1e91b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity::get_modifiedby()
0x1e920  ldc.i4.0
0x1e921  ldc.i4.0
0x1e922  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e927  ldarg.0
0x1e928  ldstr    aModifiedon// "modifiedon"
0x1e92d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e932  ldarg.3
0x1e933  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity::get_modifiedon()
0x1e938  ldc.i4.0
0x1e939  ldc.i4.0
0x1e93a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e93f  ldarg.0
0x1e940  ldstr    aObjecttypecode_0// "objecttypecode"
0x1e945  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e94a  ldarg.3
0x1e94b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity::get_objecttypecode()
0x1e950  ldc.i4.0
0x1e951  ldc.i4.0
0x1e952  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write135_EntityNameReference(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference o, bool isNullable, bool needType)
0x1e957  ldarg.0
0x1e958  ldstr    aOwningbusiness// "owningbusinessunit"
0x1e95d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e962  ldarg.3
0x1e963  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity::get_owningbusinessunit()
0x1e968  ldc.i4.0
0x1e969  ldc.i4.0
0x1e96a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1e96f  ldarg.0
0x1e970  ldstr    aOwninguser// "owninguser"
0x1e975  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e97a  ldarg.3
0x1e97b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity::get_owninguser()
0x1e980  ldc.i4.0
0x1e981  ldc.i4.0
0x1e982  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1e987  ldarg.0
0x1e988  ldstr    aReportentityid// "reportentityid"
0x1e98d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e992  ldarg.3
0x1e993  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity::get_reportentityid()
0x1e998  ldc.i4.0
0x1e999  ldc.i4.0
0x1e99a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1e99f  ldarg.0
0x1e9a0  ldstr    aReportid// "reportid"
0x1e9a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e9aa  ldarg.3
0x1e9ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportentity::get_reportid()
0x1e9b0  ldc.i4.0
0x1e9b1  ldc.i4.0
0x1e9b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e9b7  ldarg.0
0x1e9b8  ldarg.3
0x1e9b9  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1e9be  ret
```
