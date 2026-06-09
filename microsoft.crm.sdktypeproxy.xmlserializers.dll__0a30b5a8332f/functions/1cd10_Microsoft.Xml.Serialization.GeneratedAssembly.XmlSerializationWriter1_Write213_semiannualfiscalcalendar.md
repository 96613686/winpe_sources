# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write213_semiannualfiscalcalendar

- ea: `0x1cd10`
- end: `0x1cf17`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write213_semiannualfiscalcalendar`
- size: `519`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35cd0`
- `0x55080`

## callees

- `0x5cf0`
- `0x5e50`
- `0x150d0`
- `0x15180`
- `0x153c0`
- `0x15430`
- `0x1cd10`

## string_xrefs

- `0x1cd55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cd65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cd7d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cd95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cdad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cdc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cddd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cdf5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ce0d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ce25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ce3d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ce55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ce6d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ce85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ce9d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ceb5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cecd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cee5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cefd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cd78`: `createdby`
- `0x1cd90`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x1cd10  ldarg.3
0x1cd11  brtrue.s loc_1CD20
0x1cd13  ldarg.s  4
0x1cd15  brfalse.s loc_1CD1F
0x1cd17  ldarg.0
0x1cd18  ldarg.1
0x1cd19  ldarg.2
0x1cd1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1cd1f  ret
0x1cd20  ldarg.s  5
0x1cd22  brtrue.s loc_1CD40
0x1cd24  ldarg.3
0x1cd25  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1cd2a  stloc.0
0x1cd2b  ldloc.0
0x1cd2c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar
0x1cd31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1cd36  beq.s    loc_1CD40
0x1cd38  ldarg.0
0x1cd39  ldarg.3
0x1cd3a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1cd3f  throw
0x1cd40  ldarg.0
0x1cd41  ldarg.1
0x1cd42  ldarg.2
0x1cd43  ldarg.3
0x1cd44  ldc.i4.0
0x1cd45  ldnull
0x1cd46  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1cd4b  ldarg.s  5
0x1cd4d  brfalse.s loc_1CD5F
0x1cd4f  ldarg.0
0x1cd50  ldstr    aSemiannualfisc// "semiannualfiscalcalendar"
0x1cd55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cd5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1cd5f  ldarg.0
0x1cd60  ldstr    aBusinessunitid// "businessunitid"
0x1cd65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cd6a  ldarg.3
0x1cd6b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_businessunitid()
0x1cd70  ldc.i4.0
0x1cd71  ldc.i4.0
0x1cd72  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1cd77  ldarg.0
0x1cd78  ldstr    aCreatedby// "createdby"
0x1cd7d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cd82  ldarg.3
0x1cd83  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_createdby()
0x1cd88  ldc.i4.0
0x1cd89  ldc.i4.0
0x1cd8a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1cd8f  ldarg.0
0x1cd90  ldstr    aCreatedon// "createdon"
0x1cd95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cd9a  ldarg.3
0x1cd9b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_createdon()
0x1cda0  ldc.i4.0
0x1cda1  ldc.i4.0
0x1cda2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1cda7  ldarg.0
0x1cda8  ldstr    aEffectiveon// "effectiveon"
0x1cdad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cdb2  ldarg.3
0x1cdb3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_effectiveon()
0x1cdb8  ldc.i4.0
0x1cdb9  ldc.i4.0
0x1cdba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1cdbf  ldarg.0
0x1cdc0  ldstr    aExchangerate// "exchangerate"
0x1cdc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cdca  ldarg.3
0x1cdcb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_exchangerate()
0x1cdd0  ldc.i4.0
0x1cdd1  ldc.i4.0
0x1cdd2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x1cdd7  ldarg.0
0x1cdd8  ldstr    aFirsthalf// "firsthalf"
0x1cddd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cde2  ldarg.3
0x1cde3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_firsthalf()
0x1cde8  ldc.i4.0
0x1cde9  ldc.i4.0
0x1cdea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x1cdef  ldarg.0
0x1cdf0  ldstr    aFirsthalfBase// "firsthalf_base"
0x1cdf5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cdfa  ldarg.3
0x1cdfb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_firsthalf_base()
0x1ce00  ldc.i4.0
0x1ce01  ldc.i4.0
0x1ce02  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x1ce07  ldarg.0
0x1ce08  ldstr    aFiscalperiodty// "fiscalperiodtype"
0x1ce0d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ce12  ldarg.3
0x1ce13  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_fiscalperiodtype()
0x1ce18  ldc.i4.0
0x1ce19  ldc.i4.0
0x1ce1a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ce1f  ldarg.0
0x1ce20  ldstr    aImportsequence// "importsequencenumber"
0x1ce25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ce2a  ldarg.3
0x1ce2b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_importsequencenumber()
0x1ce30  ldc.i4.0
0x1ce31  ldc.i4.0
0x1ce32  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ce37  ldarg.0
0x1ce38  ldstr    aModifiedby// "modifiedby"
0x1ce3d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ce42  ldarg.3
0x1ce43  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_modifiedby()
0x1ce48  ldc.i4.0
0x1ce49  ldc.i4.0
0x1ce4a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ce4f  ldarg.0
0x1ce50  ldstr    aModifiedon// "modifiedon"
0x1ce55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ce5a  ldarg.3
0x1ce5b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_modifiedon()
0x1ce60  ldc.i4.0
0x1ce61  ldc.i4.0
0x1ce62  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ce67  ldarg.0
0x1ce68  ldstr    aSalespersonid// "salespersonid"
0x1ce6d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ce72  ldarg.3
0x1ce73  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_salespersonid()
0x1ce78  ldc.i4.0
0x1ce79  ldc.i4.0
0x1ce7a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ce7f  ldarg.0
0x1ce80  ldstr    aSecondhalf// "secondhalf"
0x1ce85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ce8a  ldarg.3
0x1ce8b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_secondhalf()
0x1ce90  ldc.i4.0
0x1ce91  ldc.i4.0
0x1ce92  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x1ce97  ldarg.0
0x1ce98  ldstr    aSecondhalfBase// "secondhalf_base"
0x1ce9d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cea2  ldarg.3
0x1cea3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_secondhalf_base()
0x1cea8  ldc.i4.0
0x1cea9  ldc.i4.0
0x1ceaa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x1ceaf  ldarg.0
0x1ceb0  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x1ceb5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ceba  ldarg.3
0x1cebb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_timezoneruleversionnumber()
0x1cec0  ldc.i4.0
0x1cec1  ldc.i4.0
0x1cec2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1cec7  ldarg.0
0x1cec8  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x1cecd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ced2  ldarg.3
0x1ced3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_transactioncurrencyid()
0x1ced8  ldc.i4.0
0x1ced9  ldc.i4.0
0x1ceda  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1cedf  ldarg.0
0x1cee0  ldstr    aUserfiscalcale// "userfiscalcalendarid"
0x1cee5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ceea  ldarg.3
0x1ceeb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_userfiscalcalendarid()
0x1cef0  ldc.i4.0
0x1cef1  ldc.i4.0
0x1cef2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1cef7  ldarg.0
0x1cef8  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x1cefd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cf02  ldarg.3
0x1cf03  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.semiannualfiscalcalendar::get_utcconversiontimezonecode()
0x1cf08  ldc.i4.0
0x1cf09  ldc.i4.0
0x1cf0a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1cf0f  ldarg.0
0x1cf10  ldarg.3
0x1cf11  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1cf16  ret
```
