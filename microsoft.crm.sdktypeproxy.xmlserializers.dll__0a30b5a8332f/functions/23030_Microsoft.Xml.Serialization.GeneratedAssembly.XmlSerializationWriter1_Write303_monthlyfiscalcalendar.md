# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write303_monthlyfiscalcalendar

- ea: `0x23030`
- end: `0x233ff`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write303_monthlyfiscalcalendar`
- size: `975`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36bb0`
- `0x55fd0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x150d0`
- `0x15180`
- `0x153c0`
- `0x15430`
- `0x23030`

## string_xrefs

- `0x23075`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23085`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2309d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x230b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x230cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x230e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x230fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23115`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2312d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23145`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2315d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23175`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2318d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x231a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x231bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x231d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x231ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23205`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2321d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23235`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2324d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23265`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2327d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23295`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x232ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x232c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x232dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x232f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2330d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23325`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2333d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23355`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2336d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23385`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2339d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x233b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x233cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x233e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23098`: `createdby`
- `0x230b0`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x23030  ldarg.3
0x23031  brtrue.s loc_23040
0x23033  ldarg.s  4
0x23035  brfalse.s loc_2303F
0x23037  ldarg.0
0x23038  ldarg.1
0x23039  ldarg.2
0x2303a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2303f  ret
0x23040  ldarg.s  5
0x23042  brtrue.s loc_23060
0x23044  ldarg.3
0x23045  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2304a  stloc.0
0x2304b  ldloc.0
0x2304c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar
0x23051  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23056  beq.s    loc_23060
0x23058  ldarg.0
0x23059  ldarg.3
0x2305a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2305f  throw
0x23060  ldarg.0
0x23061  ldarg.1
0x23062  ldarg.2
0x23063  ldarg.3
0x23064  ldc.i4.0
0x23065  ldnull
0x23066  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2306b  ldarg.s  5
0x2306d  brfalse.s loc_2307F
0x2306f  ldarg.0
0x23070  ldstr    aMonthlyfiscalc// "monthlyfiscalcalendar"
0x23075  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2307a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2307f  ldarg.0
0x23080  ldstr    aBusinessunitid// "businessunitid"
0x23085  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2308a  ldarg.3
0x2308b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_businessunitid()
0x23090  ldc.i4.0
0x23091  ldc.i4.0
0x23092  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x23097  ldarg.0
0x23098  ldstr    aCreatedby// "createdby"
0x2309d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x230a2  ldarg.3
0x230a3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_createdby()
0x230a8  ldc.i4.0
0x230a9  ldc.i4.0
0x230aa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x230af  ldarg.0
0x230b0  ldstr    aCreatedon// "createdon"
0x230b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x230ba  ldarg.3
0x230bb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_createdon()
0x230c0  ldc.i4.0
0x230c1  ldc.i4.0
0x230c2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x230c7  ldarg.0
0x230c8  ldstr    aEffectiveon// "effectiveon"
0x230cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x230d2  ldarg.3
0x230d3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_effectiveon()
0x230d8  ldc.i4.0
0x230d9  ldc.i4.0
0x230da  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x230df  ldarg.0
0x230e0  ldstr    aExchangerate// "exchangerate"
0x230e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x230ea  ldarg.3
0x230eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_exchangerate()
0x230f0  ldc.i4.0
0x230f1  ldc.i4.0
0x230f2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x230f7  ldarg.0
0x230f8  ldstr    aFiscalperiodty// "fiscalperiodtype"
0x230fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23102  ldarg.3
0x23103  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_fiscalperiodtype()
0x23108  ldc.i4.0
0x23109  ldc.i4.0
0x2310a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2310f  ldarg.0
0x23110  ldstr    aModifiedby// "modifiedby"
0x23115  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2311a  ldarg.3
0x2311b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_modifiedby()
0x23120  ldc.i4.0
0x23121  ldc.i4.0
0x23122  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x23127  ldarg.0
0x23128  ldstr    aModifiedon// "modifiedon"
0x2312d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23132  ldarg.3
0x23133  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_modifiedon()
0x23138  ldc.i4.0
0x23139  ldc.i4.0
0x2313a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2313f  ldarg.0
0x23140  ldstr    aMonth1// "month1"
0x23145  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2314a  ldarg.3
0x2314b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month1()
0x23150  ldc.i4.0
0x23151  ldc.i4.0
0x23152  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x23157  ldarg.0
0x23158  ldstr    aMonth1Base// "month1_base"
0x2315d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23162  ldarg.3
0x23163  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month1_base()
0x23168  ldc.i4.0
0x23169  ldc.i4.0
0x2316a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2316f  ldarg.0
0x23170  ldstr    aMonth10// "month10"
0x23175  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2317a  ldarg.3
0x2317b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month10()
0x23180  ldc.i4.0
0x23181  ldc.i4.0
0x23182  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x23187  ldarg.0
0x23188  ldstr    aMonth10Base// "month10_base"
0x2318d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23192  ldarg.3
0x23193  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month10_base()
0x23198  ldc.i4.0
0x23199  ldc.i4.0
0x2319a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2319f  ldarg.0
0x231a0  ldstr    aMonth11// "month11"
0x231a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x231aa  ldarg.3
0x231ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month11()
0x231b0  ldc.i4.0
0x231b1  ldc.i4.0
0x231b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x231b7  ldarg.0
0x231b8  ldstr    aMonth11Base// "month11_base"
0x231bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x231c2  ldarg.3
0x231c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month11_base()
0x231c8  ldc.i4.0
0x231c9  ldc.i4.0
0x231ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x231cf  ldarg.0
0x231d0  ldstr    aMonth12// "month12"
0x231d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x231da  ldarg.3
0x231db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month12()
0x231e0  ldc.i4.0
0x231e1  ldc.i4.0
0x231e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x231e7  ldarg.0
0x231e8  ldstr    aMonth12Base// "month12_base"
0x231ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x231f2  ldarg.3
0x231f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month12_base()
0x231f8  ldc.i4.0
0x231f9  ldc.i4.0
0x231fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x231ff  ldarg.0
0x23200  ldstr    aMonth2// "month2"
0x23205  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2320a  ldarg.3
0x2320b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month2()
0x23210  ldc.i4.0
0x23211  ldc.i4.0
0x23212  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x23217  ldarg.0
0x23218  ldstr    aMonth2Base// "month2_base"
0x2321d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23222  ldarg.3
0x23223  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month2_base()
0x23228  ldc.i4.0
0x23229  ldc.i4.0
0x2322a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2322f  ldarg.0
0x23230  ldstr    aMonth3// "month3"
0x23235  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2323a  ldarg.3
0x2323b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month3()
0x23240  ldc.i4.0
0x23241  ldc.i4.0
0x23242  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x23247  ldarg.0
0x23248  ldstr    aMonth3Base// "month3_base"
0x2324d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23252  ldarg.3
0x23253  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month3_base()
0x23258  ldc.i4.0
0x23259  ldc.i4.0
0x2325a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2325f  ldarg.0
0x23260  ldstr    aMonth4// "month4"
0x23265  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2326a  ldarg.3
0x2326b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month4()
0x23270  ldc.i4.0
0x23271  ldc.i4.0
0x23272  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x23277  ldarg.0
0x23278  ldstr    aMonth4Base// "month4_base"
0x2327d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23282  ldarg.3
0x23283  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month4_base()
0x23288  ldc.i4.0
0x23289  ldc.i4.0
0x2328a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2328f  ldarg.0
0x23290  ldstr    aMonth5// "month5"
0x23295  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2329a  ldarg.3
0x2329b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month5()
0x232a0  ldc.i4.0
0x232a1  ldc.i4.0
0x232a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x232a7  ldarg.0
0x232a8  ldstr    aMonth5Base// "month5_base"
0x232ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x232b2  ldarg.3
0x232b3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month5_base()
0x232b8  ldc.i4.0
0x232b9  ldc.i4.0
0x232ba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x232bf  ldarg.0
0x232c0  ldstr    aMonth6// "month6"
0x232c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x232ca  ldarg.3
0x232cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month6()
0x232d0  ldc.i4.0
0x232d1  ldc.i4.0
0x232d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x232d7  ldarg.0
0x232d8  ldstr    aMonth6Base// "month6_base"
0x232dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x232e2  ldarg.3
0x232e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month6_base()
0x232e8  ldc.i4.0
0x232e9  ldc.i4.0
0x232ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x232ef  ldarg.0
0x232f0  ldstr    aMonth7// "month7"
0x232f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x232fa  ldarg.3
0x232fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month7()
0x23300  ldc.i4.0
0x23301  ldc.i4.0
0x23302  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x23307  ldarg.0
0x23308  ldstr    aMonth7Base// "month7_base"
0x2330d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23312  ldarg.3
0x23313  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month7_base()
0x23318  ldc.i4.0
0x23319  ldc.i4.0
0x2331a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2331f  ldarg.0
0x23320  ldstr    aMonth8// "month8"
0x23325  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2332a  ldarg.3
0x2332b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month8()
0x23330  ldc.i4.0
0x23331  ldc.i4.0
0x23332  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x23337  ldarg.0
0x23338  ldstr    aMonth8Base// "month8_base"
0x2333d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23342  ldarg.3
0x23343  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month8_base()
0x23348  ldc.i4.0
0x23349  ldc.i4.0
0x2334a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2334f  ldarg.0
0x23350  ldstr    aMonth9// "month9"
0x23355  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2335a  ldarg.3
0x2335b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month9()
0x23360  ldc.i4.0
0x23361  ldc.i4.0
0x23362  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x23367  ldarg.0
0x23368  ldstr    aMonth9Base// "month9_base"
0x2336d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23372  ldarg.3
0x23373  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_month9_base()
0x23378  ldc.i4.0
0x23379  ldc.i4.0
0x2337a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2337f  ldarg.0
0x23380  ldstr    aSalespersonid// "salespersonid"
0x23385  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2338a  ldarg.3
0x2338b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.monthlyfiscalcalendar::get_salespersonid()
0x23390  ldc.i4.0
0x23391  ldc.i4.0
0x23392  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x23397  ldarg.0
  ... truncated ...
```
