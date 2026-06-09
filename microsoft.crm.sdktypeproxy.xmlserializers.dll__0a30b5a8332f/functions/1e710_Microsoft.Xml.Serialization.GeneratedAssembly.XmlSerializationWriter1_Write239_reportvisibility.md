# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write239_reportvisibility

- ea: `0x1e710`
- end: `0x1e857`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write239_reportvisibility`
- size: `327`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x361a0`
- `0x55550`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x1e710`

## string_xrefs

- `0x1e755`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e765`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e77d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e795`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e7ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e7c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e7dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e7f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e80d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e825`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e83d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e760`: `createdby`
- `0x1e778`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x1e710  ldarg.3
0x1e711  brtrue.s loc_1E720
0x1e713  ldarg.s  4
0x1e715  brfalse.s loc_1E71F
0x1e717  ldarg.0
0x1e718  ldarg.1
0x1e719  ldarg.2
0x1e71a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1e71f  ret
0x1e720  ldarg.s  5
0x1e722  brtrue.s loc_1E740
0x1e724  ldarg.3
0x1e725  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1e72a  stloc.0
0x1e72b  ldloc.0
0x1e72c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportvisibility
0x1e731  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e736  beq.s    loc_1E740
0x1e738  ldarg.0
0x1e739  ldarg.3
0x1e73a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1e73f  throw
0x1e740  ldarg.0
0x1e741  ldarg.1
0x1e742  ldarg.2
0x1e743  ldarg.3
0x1e744  ldc.i4.0
0x1e745  ldnull
0x1e746  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1e74b  ldarg.s  5
0x1e74d  brfalse.s loc_1E75F
0x1e74f  ldarg.0
0x1e750  ldstr    aReportvisibili// "reportvisibility"
0x1e755  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e75a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1e75f  ldarg.0
0x1e760  ldstr    aCreatedby// "createdby"
0x1e765  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e76a  ldarg.3
0x1e76b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportvisibility::get_createdby()
0x1e770  ldc.i4.0
0x1e771  ldc.i4.0
0x1e772  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e777  ldarg.0
0x1e778  ldstr    aCreatedon// "createdon"
0x1e77d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e782  ldarg.3
0x1e783  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportvisibility::get_createdon()
0x1e788  ldc.i4.0
0x1e789  ldc.i4.0
0x1e78a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e78f  ldarg.0
0x1e790  ldstr    aImportsequence// "importsequencenumber"
0x1e795  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e79a  ldarg.3
0x1e79b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportvisibility::get_importsequencenumber()
0x1e7a0  ldc.i4.0
0x1e7a1  ldc.i4.0
0x1e7a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1e7a7  ldarg.0
0x1e7a8  ldstr    aModifiedby// "modifiedby"
0x1e7ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e7b2  ldarg.3
0x1e7b3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportvisibility::get_modifiedby()
0x1e7b8  ldc.i4.0
0x1e7b9  ldc.i4.0
0x1e7ba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e7bf  ldarg.0
0x1e7c0  ldstr    aModifiedon// "modifiedon"
0x1e7c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e7ca  ldarg.3
0x1e7cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportvisibility::get_modifiedon()
0x1e7d0  ldc.i4.0
0x1e7d1  ldc.i4.0
0x1e7d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e7d7  ldarg.0
0x1e7d8  ldstr    aOwningbusiness// "owningbusinessunit"
0x1e7dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e7e2  ldarg.3
0x1e7e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportvisibility::get_owningbusinessunit()
0x1e7e8  ldc.i4.0
0x1e7e9  ldc.i4.0
0x1e7ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1e7ef  ldarg.0
0x1e7f0  ldstr    aOwninguser// "owninguser"
0x1e7f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e7fa  ldarg.3
0x1e7fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportvisibility::get_owninguser()
0x1e800  ldc.i4.0
0x1e801  ldc.i4.0
0x1e802  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1e807  ldarg.0
0x1e808  ldstr    aReportid// "reportid"
0x1e80d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e812  ldarg.3
0x1e813  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportvisibility::get_reportid()
0x1e818  ldc.i4.0
0x1e819  ldc.i4.0
0x1e81a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e81f  ldarg.0
0x1e820  ldstr    aReportvisibili_0// "reportvisibilityid"
0x1e825  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e82a  ldarg.3
0x1e82b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportvisibility::get_reportvisibilityid()
0x1e830  ldc.i4.0
0x1e831  ldc.i4.0
0x1e832  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1e837  ldarg.0
0x1e838  ldstr    aVisibilitycode// "visibilitycode"
0x1e83d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e842  ldarg.3
0x1e843  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.reportvisibility::get_visibilitycode()
0x1e848  ldc.i4.0
0x1e849  ldc.i4.0
0x1e84a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1e84f  ldarg.0
0x1e850  ldarg.3
0x1e851  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1e856  ret
```
