# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write349_importjob

- ea: `0x261b0`
- end: `0x262db`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write349_importjob`
- size: `299`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x371d0`
- `0x56660`

## callees

- `0x5cf0`
- `0x5e50`
- `0x153c0`
- `0x261b0`

## string_xrefs

- `0x261f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26205`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2621d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26235`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2624b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26263`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2627b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26291`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x262a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x262c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26218`: `createdon`
- `0x26200`: `completedon`

## pseudocode

```c

```

## disassembly

```asm
0x261b0  ldarg.3
0x261b1  brtrue.s loc_261C0
0x261b3  ldarg.s  4
0x261b5  brfalse.s loc_261BF
0x261b7  ldarg.0
0x261b8  ldarg.1
0x261b9  ldarg.2
0x261ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x261bf  ret
0x261c0  ldarg.s  5
0x261c2  brtrue.s loc_261E0
0x261c4  ldarg.3
0x261c5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x261ca  stloc.0
0x261cb  ldloc.0
0x261cc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importjob
0x261d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x261d6  beq.s    loc_261E0
0x261d8  ldarg.0
0x261d9  ldarg.3
0x261da  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x261df  throw
0x261e0  ldarg.0
0x261e1  ldarg.1
0x261e2  ldarg.2
0x261e3  ldarg.3
0x261e4  ldc.i4.0
0x261e5  ldnull
0x261e6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x261eb  ldarg.s  5
0x261ed  brfalse.s loc_261FF
0x261ef  ldarg.0
0x261f0  ldstr    aImportjob// "importjob"
0x261f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x261fa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x261ff  ldarg.0
0x26200  ldstr    aCompletedon// "completedon"
0x26205  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2620a  ldarg.3
0x2620b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importjob::get_completedon()
0x26210  ldc.i4.0
0x26211  ldc.i4.0
0x26212  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x26217  ldarg.0
0x26218  ldstr    aCreatedon// "createdon"
0x2621d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26222  ldarg.3
0x26223  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importjob::get_createdon()
0x26228  ldc.i4.0
0x26229  ldc.i4.0
0x2622a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2622f  ldarg.0
0x26230  ldstr    aData_0// "data"
0x26235  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2623a  ldarg.3
0x2623b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importjob::get_data()
0x26240  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x26245  ldarg.0
0x26246  ldstr    aImportjobid// "importjobid"
0x2624b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26250  ldarg.3
0x26251  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importjob::get_importjobid()
0x26256  ldc.i4.0
0x26257  ldc.i4.0
0x26258  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2625d  ldarg.0
0x2625e  ldstr    aModifiedon// "modifiedon"
0x26263  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26268  ldarg.3
0x26269  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importjob::get_modifiedon()
0x2626e  ldc.i4.0
0x2626f  ldc.i4.0
0x26270  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x26275  ldarg.0
0x26276  ldstr    aName// "name"
0x2627b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26280  ldarg.3
0x26281  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importjob::get_name()
0x26286  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2628b  ldarg.0
0x2628c  ldstr    aStartedon// "startedon"
0x26291  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26296  ldarg.3
0x26297  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importjob::get_startedon()
0x2629c  ldc.i4.0
0x2629d  ldc.i4.0
0x2629e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x262a3  ldarg.0
0x262a4  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x262a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x262ae  ldarg.3
0x262af  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importjob::get_timezoneruleversionnumber()
0x262b4  ldc.i4.0
0x262b5  ldc.i4.0
0x262b6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x262bb  ldarg.0
0x262bc  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x262c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x262c6  ldarg.3
0x262c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importjob::get_utcconversiontimezonecode()
0x262cc  ldc.i4.0
0x262cd  ldc.i4.0
0x262ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x262d3  ldarg.0
0x262d4  ldarg.3
0x262d5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x262da  ret
```
