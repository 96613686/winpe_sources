# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write363_fixedmonthlyfiscalcalendar

- ea: `0x26b90`
- end: `0x26f8f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write363_fixedmonthlyfiscalcalendar`
- size: `1023`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37390`
- `0x56820`

## callees

- `0x5cf0`
- `0x5e50`
- `0x150d0`
- `0x15180`
- `0x153c0`
- `0x15430`
- `0x26b90`

## string_xrefs

- `0x26bd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26be5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26bfd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26c15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26c2d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26c45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26c5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26c75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26c8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26ca5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26cbd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26cd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26ced`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26d05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26d1d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26d35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26d4d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26d65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26d7d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26d95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26dad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26dc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26ddd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26df5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26e0d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26e25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26e3d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26e55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26e6d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26e85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26e9d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26eb5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26ecd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26ee5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26efd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26f15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26f2d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26f45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26f5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26f75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26bf8`: `createdby`
- `0x26c10`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x26b90  ldarg.3
0x26b91  brtrue.s loc_26BA0
0x26b93  ldarg.s  4
0x26b95  brfalse.s loc_26B9F
0x26b97  ldarg.0
0x26b98  ldarg.1
0x26b99  ldarg.2
0x26b9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x26b9f  ret
0x26ba0  ldarg.s  5
0x26ba2  brtrue.s loc_26BC0
0x26ba4  ldarg.3
0x26ba5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x26baa  stloc.0
0x26bab  ldloc.0
0x26bac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar
0x26bb1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x26bb6  beq.s    loc_26BC0
0x26bb8  ldarg.0
0x26bb9  ldarg.3
0x26bba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x26bbf  throw
0x26bc0  ldarg.0
0x26bc1  ldarg.1
0x26bc2  ldarg.2
0x26bc3  ldarg.3
0x26bc4  ldc.i4.0
0x26bc5  ldnull
0x26bc6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x26bcb  ldarg.s  5
0x26bcd  brfalse.s loc_26BDF
0x26bcf  ldarg.0
0x26bd0  ldstr    aFixedmonthlyfi// "fixedmonthlyfiscalcalendar"
0x26bd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26bda  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x26bdf  ldarg.0
0x26be0  ldstr    aBusinessunitid// "businessunitid"
0x26be5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26bea  ldarg.3
0x26beb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_businessunitid()
0x26bf0  ldc.i4.0
0x26bf1  ldc.i4.0
0x26bf2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x26bf7  ldarg.0
0x26bf8  ldstr    aCreatedby// "createdby"
0x26bfd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26c02  ldarg.3
0x26c03  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_createdby()
0x26c08  ldc.i4.0
0x26c09  ldc.i4.0
0x26c0a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x26c0f  ldarg.0
0x26c10  ldstr    aCreatedon// "createdon"
0x26c15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26c1a  ldarg.3
0x26c1b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_createdon()
0x26c20  ldc.i4.0
0x26c21  ldc.i4.0
0x26c22  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x26c27  ldarg.0
0x26c28  ldstr    aEffectiveon// "effectiveon"
0x26c2d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26c32  ldarg.3
0x26c33  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_effectiveon()
0x26c38  ldc.i4.0
0x26c39  ldc.i4.0
0x26c3a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x26c3f  ldarg.0
0x26c40  ldstr    aExchangerate// "exchangerate"
0x26c45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26c4a  ldarg.3
0x26c4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_exchangerate()
0x26c50  ldc.i4.0
0x26c51  ldc.i4.0
0x26c52  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x26c57  ldarg.0
0x26c58  ldstr    aFiscalperiodty// "fiscalperiodtype"
0x26c5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26c62  ldarg.3
0x26c63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_fiscalperiodtype()
0x26c68  ldc.i4.0
0x26c69  ldc.i4.0
0x26c6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x26c6f  ldarg.0
0x26c70  ldstr    aModifiedby// "modifiedby"
0x26c75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26c7a  ldarg.3
0x26c7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_modifiedby()
0x26c80  ldc.i4.0
0x26c81  ldc.i4.0
0x26c82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x26c87  ldarg.0
0x26c88  ldstr    aModifiedon// "modifiedon"
0x26c8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26c92  ldarg.3
0x26c93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_modifiedon()
0x26c98  ldc.i4.0
0x26c99  ldc.i4.0
0x26c9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x26c9f  ldarg.0
0x26ca0  ldstr    aPeriod1// "period1"
0x26ca5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26caa  ldarg.3
0x26cab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period1()
0x26cb0  ldc.i4.0
0x26cb1  ldc.i4.0
0x26cb2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26cb7  ldarg.0
0x26cb8  ldstr    aPeriod1Base// "period1_base"
0x26cbd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26cc2  ldarg.3
0x26cc3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period1_base()
0x26cc8  ldc.i4.0
0x26cc9  ldc.i4.0
0x26cca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26ccf  ldarg.0
0x26cd0  ldstr    aPeriod10// "period10"
0x26cd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26cda  ldarg.3
0x26cdb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period10()
0x26ce0  ldc.i4.0
0x26ce1  ldc.i4.0
0x26ce2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26ce7  ldarg.0
0x26ce8  ldstr    aPeriod10Base// "period10_base"
0x26ced  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26cf2  ldarg.3
0x26cf3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period10_base()
0x26cf8  ldc.i4.0
0x26cf9  ldc.i4.0
0x26cfa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26cff  ldarg.0
0x26d00  ldstr    aPeriod11// "period11"
0x26d05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26d0a  ldarg.3
0x26d0b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period11()
0x26d10  ldc.i4.0
0x26d11  ldc.i4.0
0x26d12  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26d17  ldarg.0
0x26d18  ldstr    aPeriod11Base// "period11_base"
0x26d1d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26d22  ldarg.3
0x26d23  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period11_base()
0x26d28  ldc.i4.0
0x26d29  ldc.i4.0
0x26d2a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26d2f  ldarg.0
0x26d30  ldstr    aPeriod12// "period12"
0x26d35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26d3a  ldarg.3
0x26d3b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period12()
0x26d40  ldc.i4.0
0x26d41  ldc.i4.0
0x26d42  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26d47  ldarg.0
0x26d48  ldstr    aPeriod12Base// "period12_base"
0x26d4d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26d52  ldarg.3
0x26d53  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period12_base()
0x26d58  ldc.i4.0
0x26d59  ldc.i4.0
0x26d5a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26d5f  ldarg.0
0x26d60  ldstr    aPeriod13// "period13"
0x26d65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26d6a  ldarg.3
0x26d6b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period13()
0x26d70  ldc.i4.0
0x26d71  ldc.i4.0
0x26d72  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26d77  ldarg.0
0x26d78  ldstr    aPeriod13Base// "period13_base"
0x26d7d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26d82  ldarg.3
0x26d83  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period13_base()
0x26d88  ldc.i4.0
0x26d89  ldc.i4.0
0x26d8a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26d8f  ldarg.0
0x26d90  ldstr    aPeriod2// "period2"
0x26d95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26d9a  ldarg.3
0x26d9b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period2()
0x26da0  ldc.i4.0
0x26da1  ldc.i4.0
0x26da2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26da7  ldarg.0
0x26da8  ldstr    aPeriod2Base// "period2_base"
0x26dad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26db2  ldarg.3
0x26db3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period2_base()
0x26db8  ldc.i4.0
0x26db9  ldc.i4.0
0x26dba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26dbf  ldarg.0
0x26dc0  ldstr    aPeriod3// "period3"
0x26dc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26dca  ldarg.3
0x26dcb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period3()
0x26dd0  ldc.i4.0
0x26dd1  ldc.i4.0
0x26dd2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26dd7  ldarg.0
0x26dd8  ldstr    aPeriod3Base// "period3_base"
0x26ddd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26de2  ldarg.3
0x26de3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period3_base()
0x26de8  ldc.i4.0
0x26de9  ldc.i4.0
0x26dea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26def  ldarg.0
0x26df0  ldstr    aPeriod4// "period4"
0x26df5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26dfa  ldarg.3
0x26dfb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period4()
0x26e00  ldc.i4.0
0x26e01  ldc.i4.0
0x26e02  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26e07  ldarg.0
0x26e08  ldstr    aPeriod4Base// "period4_base"
0x26e0d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26e12  ldarg.3
0x26e13  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period4_base()
0x26e18  ldc.i4.0
0x26e19  ldc.i4.0
0x26e1a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26e1f  ldarg.0
0x26e20  ldstr    aPeriod5// "period5"
0x26e25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26e2a  ldarg.3
0x26e2b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period5()
0x26e30  ldc.i4.0
0x26e31  ldc.i4.0
0x26e32  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26e37  ldarg.0
0x26e38  ldstr    aPeriod5Base// "period5_base"
0x26e3d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26e42  ldarg.3
0x26e43  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period5_base()
0x26e48  ldc.i4.0
0x26e49  ldc.i4.0
0x26e4a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26e4f  ldarg.0
0x26e50  ldstr    aPeriod6// "period6"
0x26e55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26e5a  ldarg.3
0x26e5b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period6()
0x26e60  ldc.i4.0
0x26e61  ldc.i4.0
0x26e62  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26e67  ldarg.0
0x26e68  ldstr    aPeriod6Base// "period6_base"
0x26e6d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26e72  ldarg.3
0x26e73  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period6_base()
0x26e78  ldc.i4.0
0x26e79  ldc.i4.0
0x26e7a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26e7f  ldarg.0
0x26e80  ldstr    aPeriod7// "period7"
0x26e85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26e8a  ldarg.3
0x26e8b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period7()
0x26e90  ldc.i4.0
0x26e91  ldc.i4.0
0x26e92  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26e97  ldarg.0
0x26e98  ldstr    aPeriod7Base// "period7_base"
0x26e9d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26ea2  ldarg.3
0x26ea3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period7_base()
0x26ea8  ldc.i4.0
0x26ea9  ldc.i4.0
0x26eaa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26eaf  ldarg.0
0x26eb0  ldstr    aPeriod8// "period8"
0x26eb5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26eba  ldarg.3
0x26ebb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period8()
0x26ec0  ldc.i4.0
0x26ec1  ldc.i4.0
0x26ec2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26ec7  ldarg.0
0x26ec8  ldstr    aPeriod8Base// "period8_base"
0x26ecd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26ed2  ldarg.3
0x26ed3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period8_base()
0x26ed8  ldc.i4.0
0x26ed9  ldc.i4.0
0x26eda  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26edf  ldarg.0
0x26ee0  ldstr    aPeriod9// "period9"
0x26ee5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26eea  ldarg.3
0x26eeb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fixedmonthlyfiscalcalendar::get_period9()
0x26ef0  ldc.i4.0
0x26ef1  ldc.i4.0
0x26ef2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x26ef7  ldarg.0
  ... truncated ...
```
