# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write369_equipment

- ea: `0x27430`
- end: `0x2765f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write369_equipment`
- size: `559`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37470`
- `0x56900`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x153c0`
- `0x27430`

## string_xrefs

- `0x27475`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27485`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2749d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x274b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x274cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x274e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x274fb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27513`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27529`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27541`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27559`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27571`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27589`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x275a1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x275b7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x275cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x275e7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x275ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27615`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2762d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27645`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x274b0`: `createdby`
- `0x274c8`: `createdon`
- `0x275ca`: `overriddencreatedon`
- `0x274f6`: `displayinserviceviews`

## pseudocode

```c

```

## disassembly

```asm
0x27430  ldarg.3
0x27431  brtrue.s loc_27440
0x27433  ldarg.s  4
0x27435  brfalse.s loc_2743F
0x27437  ldarg.0
0x27438  ldarg.1
0x27439  ldarg.2
0x2743a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2743f  ret
0x27440  ldarg.s  5
0x27442  brtrue.s loc_27460
0x27444  ldarg.3
0x27445  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2744a  stloc.0
0x2744b  ldloc.0
0x2744c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment
0x27451  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27456  beq.s    loc_27460
0x27458  ldarg.0
0x27459  ldarg.3
0x2745a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2745f  throw
0x27460  ldarg.0
0x27461  ldarg.1
0x27462  ldarg.2
0x27463  ldarg.3
0x27464  ldc.i4.0
0x27465  ldnull
0x27466  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2746b  ldarg.s  5
0x2746d  brfalse.s loc_2747F
0x2746f  ldarg.0
0x27470  ldstr    aEquipment// "equipment"
0x27475  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2747a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2747f  ldarg.0
0x27480  ldstr    aBusinessunitid// "businessunitid"
0x27485  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2748a  ldarg.3
0x2748b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_businessunitid()
0x27490  ldc.i4.0
0x27491  ldc.i4.0
0x27492  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x27497  ldarg.0
0x27498  ldstr    aCalendarid_0// "calendarid"
0x2749d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x274a2  ldarg.3
0x274a3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_calendarid()
0x274a8  ldc.i4.0
0x274a9  ldc.i4.0
0x274aa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x274af  ldarg.0
0x274b0  ldstr    aCreatedby// "createdby"
0x274b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x274ba  ldarg.3
0x274bb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_createdby()
0x274c0  ldc.i4.0
0x274c1  ldc.i4.0
0x274c2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x274c7  ldarg.0
0x274c8  ldstr    aCreatedon// "createdon"
0x274cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x274d2  ldarg.3
0x274d3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_createdon()
0x274d8  ldc.i4.0
0x274d9  ldc.i4.0
0x274da  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x274df  ldarg.0
0x274e0  ldstr    aDescription_0// "description"
0x274e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x274ea  ldarg.3
0x274eb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_description()
0x274f0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x274f5  ldarg.0
0x274f6  ldstr    aDisplayinservi// "displayinserviceviews"
0x274fb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27500  ldarg.3
0x27501  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_displayinserviceviews()
0x27506  ldc.i4.0
0x27507  ldc.i4.0
0x27508  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2750d  ldarg.0
0x2750e  ldstr    aEmailaddress// "emailaddress"
0x27513  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27518  ldarg.3
0x27519  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_emailaddress()
0x2751e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27523  ldarg.0
0x27524  ldstr    aEquipmentid// "equipmentid"
0x27529  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2752e  ldarg.3
0x2752f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_equipmentid()
0x27534  ldc.i4.0
0x27535  ldc.i4.0
0x27536  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2753b  ldarg.0
0x2753c  ldstr    aImportsequence// "importsequencenumber"
0x27541  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27546  ldarg.3
0x27547  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_importsequencenumber()
0x2754c  ldc.i4.0
0x2754d  ldc.i4.0
0x2754e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x27553  ldarg.0
0x27554  ldstr    aIsdisabled// "isdisabled"
0x27559  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2755e  ldarg.3
0x2755f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_isdisabled()
0x27564  ldc.i4.0
0x27565  ldc.i4.0
0x27566  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2756b  ldarg.0
0x2756c  ldstr    aModifiedby// "modifiedby"
0x27571  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27576  ldarg.3
0x27577  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_modifiedby()
0x2757c  ldc.i4.0
0x2757d  ldc.i4.0
0x2757e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x27583  ldarg.0
0x27584  ldstr    aModifiedon// "modifiedon"
0x27589  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2758e  ldarg.3
0x2758f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_modifiedon()
0x27594  ldc.i4.0
0x27595  ldc.i4.0
0x27596  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2759b  ldarg.0
0x2759c  ldstr    aName// "name"
0x275a1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x275a6  ldarg.3
0x275a7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_name()
0x275ac  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x275b1  ldarg.0
0x275b2  ldstr    aOrganizationid// "organizationid"
0x275b7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x275bc  ldarg.3
0x275bd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_organizationid()
0x275c2  ldc.i4.0
0x275c3  ldc.i4.0
0x275c4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x275c9  ldarg.0
0x275ca  ldstr    aOverriddencrea// "overriddencreatedon"
0x275cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x275d4  ldarg.3
0x275d5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_overriddencreatedon()
0x275da  ldc.i4.0
0x275db  ldc.i4.0
0x275dc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x275e1  ldarg.0
0x275e2  ldstr    aSiteid_0// "siteid"
0x275e7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x275ec  ldarg.3
0x275ed  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_siteid()
0x275f2  ldc.i4.0
0x275f3  ldc.i4.0
0x275f4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x275f9  ldarg.0
0x275fa  ldstr    aSkills// "skills"
0x275ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27604  ldarg.3
0x27605  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_skills()
0x2760a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2760f  ldarg.0
0x27610  ldstr    aTimezonecode// "timezonecode"
0x27615  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2761a  ldarg.3
0x2761b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_timezonecode()
0x27620  ldc.i4.0
0x27621  ldc.i4.0
0x27622  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x27627  ldarg.0
0x27628  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x2762d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27632  ldarg.3
0x27633  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_timezoneruleversionnumber()
0x27638  ldc.i4.0
0x27639  ldc.i4.0
0x2763a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2763f  ldarg.0
0x27640  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x27645  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2764a  ldarg.3
0x2764b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.equipment::get_utcconversiontimezonecode()
0x27650  ldc.i4.0
0x27651  ldc.i4.0
0x27652  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x27657  ldarg.0
0x27658  ldarg.3
0x27659  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2765e  ret
```
