# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write265_quarterlyfiscalcalendar

- ea: `0x1ff30`
- end: `0x2017f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write265_quarterlyfiscalcalendar`
- size: `591`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36600`
- `0x559b0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x150d0`
- `0x15180`
- `0x153c0`
- `0x15430`
- `0x1ff30`

## string_xrefs

- `0x1ff75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ff85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ff9d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ffb5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ffcd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ffe5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fffd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20015`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2002d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20045`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2005d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20075`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2008d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x200a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x200bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x200d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x200ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20105`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2011d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20135`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2014d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20165`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ff98`: `createdby`
- `0x1ffb0`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x1ff30  ldarg.3
0x1ff31  brtrue.s loc_1FF40
0x1ff33  ldarg.s  4
0x1ff35  brfalse.s loc_1FF3F
0x1ff37  ldarg.0
0x1ff38  ldarg.1
0x1ff39  ldarg.2
0x1ff3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1ff3f  ret
0x1ff40  ldarg.s  5
0x1ff42  brtrue.s loc_1FF60
0x1ff44  ldarg.3
0x1ff45  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1ff4a  stloc.0
0x1ff4b  ldloc.0
0x1ff4c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar
0x1ff51  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ff56  beq.s    loc_1FF60
0x1ff58  ldarg.0
0x1ff59  ldarg.3
0x1ff5a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1ff5f  throw
0x1ff60  ldarg.0
0x1ff61  ldarg.1
0x1ff62  ldarg.2
0x1ff63  ldarg.3
0x1ff64  ldc.i4.0
0x1ff65  ldnull
0x1ff66  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1ff6b  ldarg.s  5
0x1ff6d  brfalse.s loc_1FF7F
0x1ff6f  ldarg.0
0x1ff70  ldstr    aQuarterlyfisca// "quarterlyfiscalcalendar"
0x1ff75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ff7a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1ff7f  ldarg.0
0x1ff80  ldstr    aBusinessunitid// "businessunitid"
0x1ff85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ff8a  ldarg.3
0x1ff8b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_businessunitid()
0x1ff90  ldc.i4.0
0x1ff91  ldc.i4.0
0x1ff92  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ff97  ldarg.0
0x1ff98  ldstr    aCreatedby// "createdby"
0x1ff9d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ffa2  ldarg.3
0x1ffa3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_createdby()
0x1ffa8  ldc.i4.0
0x1ffa9  ldc.i4.0
0x1ffaa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ffaf  ldarg.0
0x1ffb0  ldstr    aCreatedon// "createdon"
0x1ffb5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ffba  ldarg.3
0x1ffbb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_createdon()
0x1ffc0  ldc.i4.0
0x1ffc1  ldc.i4.0
0x1ffc2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ffc7  ldarg.0
0x1ffc8  ldstr    aEffectiveon// "effectiveon"
0x1ffcd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ffd2  ldarg.3
0x1ffd3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_effectiveon()
0x1ffd8  ldc.i4.0
0x1ffd9  ldc.i4.0
0x1ffda  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ffdf  ldarg.0
0x1ffe0  ldstr    aExchangerate// "exchangerate"
0x1ffe5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ffea  ldarg.3
0x1ffeb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_exchangerate()
0x1fff0  ldc.i4.0
0x1fff1  ldc.i4.0
0x1fff2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x1fff7  ldarg.0
0x1fff8  ldstr    aFiscalperiodty// "fiscalperiodtype"
0x1fffd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20002  ldarg.3
0x20003  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_fiscalperiodtype()
0x20008  ldc.i4.0
0x20009  ldc.i4.0
0x2000a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2000f  ldarg.0
0x20010  ldstr    aModifiedby// "modifiedby"
0x20015  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2001a  ldarg.3
0x2001b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_modifiedby()
0x20020  ldc.i4.0
0x20021  ldc.i4.0
0x20022  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20027  ldarg.0
0x20028  ldstr    aModifiedon// "modifiedon"
0x2002d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20032  ldarg.3
0x20033  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_modifiedon()
0x20038  ldc.i4.0
0x20039  ldc.i4.0
0x2003a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2003f  ldarg.0
0x20040  ldstr    aQuarter1// "quarter1"
0x20045  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2004a  ldarg.3
0x2004b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_quarter1()
0x20050  ldc.i4.0
0x20051  ldc.i4.0
0x20052  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x20057  ldarg.0
0x20058  ldstr    aQuarter1Base// "quarter1_base"
0x2005d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20062  ldarg.3
0x20063  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_quarter1_base()
0x20068  ldc.i4.0
0x20069  ldc.i4.0
0x2006a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2006f  ldarg.0
0x20070  ldstr    aQuarter2// "quarter2"
0x20075  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2007a  ldarg.3
0x2007b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_quarter2()
0x20080  ldc.i4.0
0x20081  ldc.i4.0
0x20082  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x20087  ldarg.0
0x20088  ldstr    aQuarter2Base// "quarter2_base"
0x2008d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20092  ldarg.3
0x20093  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_quarter2_base()
0x20098  ldc.i4.0
0x20099  ldc.i4.0
0x2009a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2009f  ldarg.0
0x200a0  ldstr    aQuarter3// "quarter3"
0x200a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x200aa  ldarg.3
0x200ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_quarter3()
0x200b0  ldc.i4.0
0x200b1  ldc.i4.0
0x200b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x200b7  ldarg.0
0x200b8  ldstr    aQuarter3Base// "quarter3_base"
0x200bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x200c2  ldarg.3
0x200c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_quarter3_base()
0x200c8  ldc.i4.0
0x200c9  ldc.i4.0
0x200ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x200cf  ldarg.0
0x200d0  ldstr    aQuarter4// "quarter4"
0x200d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x200da  ldarg.3
0x200db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_quarter4()
0x200e0  ldc.i4.0
0x200e1  ldc.i4.0
0x200e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x200e7  ldarg.0
0x200e8  ldstr    aQuarter4Base// "quarter4_base"
0x200ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x200f2  ldarg.3
0x200f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_quarter4_base()
0x200f8  ldc.i4.0
0x200f9  ldc.i4.0
0x200fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x200ff  ldarg.0
0x20100  ldstr    aSalespersonid// "salespersonid"
0x20105  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2010a  ldarg.3
0x2010b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_salespersonid()
0x20110  ldc.i4.0
0x20111  ldc.i4.0
0x20112  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20117  ldarg.0
0x20118  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x2011d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20122  ldarg.3
0x20123  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_timezoneruleversionnumber()
0x20128  ldc.i4.0
0x20129  ldc.i4.0
0x2012a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2012f  ldarg.0
0x20130  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x20135  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2013a  ldarg.3
0x2013b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_transactioncurrencyid()
0x20140  ldc.i4.0
0x20141  ldc.i4.0
0x20142  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20147  ldarg.0
0x20148  ldstr    aUserfiscalcale// "userfiscalcalendarid"
0x2014d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20152  ldarg.3
0x20153  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_userfiscalcalendarid()
0x20158  ldc.i4.0
0x20159  ldc.i4.0
0x2015a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2015f  ldarg.0
0x20160  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x20165  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2016a  ldarg.3
0x2016b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quarterlyfiscalcalendar::get_utcconversiontimezonecode()
0x20170  ldc.i4.0
0x20171  ldc.i4.0
0x20172  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x20177  ldarg.0
0x20178  ldarg.3
0x20179  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2017e  ret
```
