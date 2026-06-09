# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write404_contract

- ea: `0x29270`
- end: `0x296ad`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write404_contract`
- size: `1085`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37a20`
- `0x56e40`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x150d0`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x15430`
- `0x16a10`
- `0x16cb0`
- `0x170c0`
- `0x29270`
- `0x296b0`

## string_xrefs

- `0x292b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x292c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x292dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x292f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2930d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29325`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2933d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29355`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2936d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29385`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2939d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x293b3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x293c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x293e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x293f7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2940f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29427`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2943f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29457`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2946f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29485`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2949d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x294b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x294cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x294e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x294fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29515`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2952d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29545`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2955d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29575`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2958d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x295a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x295bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x295d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x295ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29603`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2961b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29633`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2964b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29663`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2967b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29693`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2940a`: `createdby`
- `0x29422`: `createdon`
- `0x29540`: `overriddencreatedon`
- `0x293c4`: `contractservicelevelcode`
- `0x293f2`: `contracttemplateid`
- `0x29588`: `serviceaddress`
- `0x293dc`: `contracttemplateabbreviation`

## pseudocode

```c

```

## disassembly

```asm
0x29270  ldarg.3
0x29271  brtrue.s loc_29280
0x29273  ldarg.s  4
0x29275  brfalse.s loc_2927F
0x29277  ldarg.0
0x29278  ldarg.1
0x29279  ldarg.2
0x2927a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2927f  ret
0x29280  ldarg.s  5
0x29282  brtrue.s loc_292A0
0x29284  ldarg.3
0x29285  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2928a  stloc.0
0x2928b  ldloc.0
0x2928c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract
0x29291  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29296  beq.s    loc_292A0
0x29298  ldarg.0
0x29299  ldarg.3
0x2929a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2929f  throw
0x292a0  ldarg.0
0x292a1  ldarg.1
0x292a2  ldarg.2
0x292a3  ldarg.3
0x292a4  ldc.i4.0
0x292a5  ldnull
0x292a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x292ab  ldarg.s  5
0x292ad  brfalse.s loc_292BF
0x292af  ldarg.0
0x292b0  ldstr    aContract// "contract"
0x292b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x292ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x292bf  ldarg.0
0x292c0  ldstr    aActiveon// "activeon"
0x292c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x292ca  ldarg.3
0x292cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_activeon()
0x292d0  ldc.i4.0
0x292d1  ldc.i4.0
0x292d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x292d7  ldarg.0
0x292d8  ldstr    aAllotmenttypec// "allotmenttypecode"
0x292dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x292e2  ldarg.3
0x292e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_allotmenttypecode()
0x292e8  ldc.i4.0
0x292e9  ldc.i4.0
0x292ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x292ef  ldarg.0
0x292f0  ldstr    aBillingcustome// "billingcustomerid"
0x292f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x292fa  ldarg.3
0x292fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_billingcustomerid()
0x29300  ldc.i4.0
0x29301  ldc.i4.0
0x29302  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write124_Customer(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer o, bool isNullable, bool needType)
0x29307  ldarg.0
0x29308  ldstr    aBillingendon// "billingendon"
0x2930d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29312  ldarg.3
0x29313  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_billingendon()
0x29318  ldc.i4.0
0x29319  ldc.i4.0
0x2931a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2931f  ldarg.0
0x29320  ldstr    aBillingfrequen// "billingfrequencycode"
0x29325  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2932a  ldarg.3
0x2932b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_billingfrequencycode()
0x29330  ldc.i4.0
0x29331  ldc.i4.0
0x29332  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x29337  ldarg.0
0x29338  ldstr    aBillingstarton// "billingstarton"
0x2933d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29342  ldarg.3
0x29343  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_billingstarton()
0x29348  ldc.i4.0
0x29349  ldc.i4.0
0x2934a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2934f  ldarg.0
0x29350  ldstr    aBilltoaddress// "billtoaddress"
0x29355  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2935a  ldarg.3
0x2935b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_billtoaddress()
0x29360  ldc.i4.0
0x29361  ldc.i4.0
0x29362  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x29367  ldarg.0
0x29368  ldstr    aCancelon// "cancelon"
0x2936d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29372  ldarg.3
0x29373  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_cancelon()
0x29378  ldc.i4.0
0x29379  ldc.i4.0
0x2937a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2937f  ldarg.0
0x29380  ldstr    aContractid// "contractid"
0x29385  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2938a  ldarg.3
0x2938b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_contractid()
0x29390  ldc.i4.0
0x29391  ldc.i4.0
0x29392  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x29397  ldarg.0
0x29398  ldstr    aContractlangua// "contractlanguage"
0x2939d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x293a2  ldarg.3
0x293a3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_contractlanguage()
0x293a8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x293ad  ldarg.0
0x293ae  ldstr    aContractnumber// "contractnumber"
0x293b3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x293b8  ldarg.3
0x293b9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_contractnumber()
0x293be  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x293c3  ldarg.0
0x293c4  ldstr    aContractservic// "contractservicelevelcode"
0x293c9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x293ce  ldarg.3
0x293cf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_contractservicelevelcode()
0x293d4  ldc.i4.0
0x293d5  ldc.i4.0
0x293d6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x293db  ldarg.0
0x293dc  ldstr    aContracttempla_1// "contracttemplateabbreviation"
0x293e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x293e6  ldarg.3
0x293e7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_contracttemplateabbreviation()
0x293ec  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x293f1  ldarg.0
0x293f2  ldstr    aContracttempla_0// "contracttemplateid"
0x293f7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x293fc  ldarg.3
0x293fd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_contracttemplateid()
0x29402  ldc.i4.0
0x29403  ldc.i4.0
0x29404  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x29409  ldarg.0
0x2940a  ldstr    aCreatedby// "createdby"
0x2940f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29414  ldarg.3
0x29415  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_createdby()
0x2941a  ldc.i4.0
0x2941b  ldc.i4.0
0x2941c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x29421  ldarg.0
0x29422  ldstr    aCreatedon// "createdon"
0x29427  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2942c  ldarg.3
0x2942d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_createdon()
0x29432  ldc.i4.0
0x29433  ldc.i4.0
0x29434  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x29439  ldarg.0
0x2943a  ldstr    aCustomerid// "customerid"
0x2943f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29444  ldarg.3
0x29445  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_customerid()
0x2944a  ldc.i4.0
0x2944b  ldc.i4.0
0x2944c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write124_Customer(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer o, bool isNullable, bool needType)
0x29451  ldarg.0
0x29452  ldstr    aDuration// "duration"
0x29457  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2945c  ldarg.3
0x2945d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_duration()
0x29462  ldc.i4.0
0x29463  ldc.i4.0
0x29464  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x29469  ldarg.0
0x2946a  ldstr    aEffectivitycal// "effectivitycalendar"
0x2946f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29474  ldarg.3
0x29475  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_effectivitycalendar()
0x2947a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2947f  ldarg.0
0x29480  ldstr    aExchangerate// "exchangerate"
0x29485  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2948a  ldarg.3
0x2948b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_exchangerate()
0x29490  ldc.i4.0
0x29491  ldc.i4.0
0x29492  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x29497  ldarg.0
0x29498  ldstr    aExpireson// "expireson"
0x2949d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x294a2  ldarg.3
0x294a3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_expireson()
0x294a8  ldc.i4.0
0x294a9  ldc.i4.0
0x294aa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x294af  ldarg.0
0x294b0  ldstr    aImportsequence// "importsequencenumber"
0x294b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x294ba  ldarg.3
0x294bb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_importsequencenumber()
0x294c0  ldc.i4.0
0x294c1  ldc.i4.0
0x294c2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x294c7  ldarg.0
0x294c8  ldstr    aModifiedby// "modifiedby"
0x294cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x294d2  ldarg.3
0x294d3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_modifiedby()
0x294d8  ldc.i4.0
0x294d9  ldc.i4.0
0x294da  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x294df  ldarg.0
0x294e0  ldstr    aModifiedon// "modifiedon"
0x294e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x294ea  ldarg.3
0x294eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_modifiedon()
0x294f0  ldc.i4.0
0x294f1  ldc.i4.0
0x294f2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x294f7  ldarg.0
0x294f8  ldstr    aNetprice// "netprice"
0x294fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29502  ldarg.3
0x29503  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_netprice()
0x29508  ldc.i4.0
0x29509  ldc.i4.0
0x2950a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2950f  ldarg.0
0x29510  ldstr    aNetpriceBase// "netprice_base"
0x29515  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2951a  ldarg.3
0x2951b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_netprice_base()
0x29520  ldc.i4.0
0x29521  ldc.i4.0
0x29522  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x29527  ldarg.0
0x29528  ldstr    aOriginatingcon// "originatingcontract"
0x2952d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29532  ldarg.3
0x29533  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_originatingcontract()
0x29538  ldc.i4.0
0x29539  ldc.i4.0
0x2953a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2953f  ldarg.0
0x29540  ldstr    aOverriddencrea// "overriddencreatedon"
0x29545  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2954a  ldarg.3
0x2954b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_overriddencreatedon()
0x29550  ldc.i4.0
0x29551  ldc.i4.0
0x29552  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x29557  ldarg.0
0x29558  ldstr    aOwnerid// "ownerid"
0x2955d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29562  ldarg.3
0x29563  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_ownerid()
0x29568  ldc.i4.0
0x29569  ldc.i4.0
0x2956a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2956f  ldarg.0
0x29570  ldstr    aOwningbusiness// "owningbusinessunit"
0x29575  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2957a  ldarg.3
0x2957b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_owningbusinessunit()
0x29580  ldc.i4.0
0x29581  ldc.i4.0
0x29582  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x29587  ldarg.0
0x29588  ldstr    aServiceaddress// "serviceaddress"
0x2958d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29592  ldarg.3
0x29593  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_serviceaddress()
0x29598  ldc.i4.0
0x29599  ldc.i4.0
0x2959a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2959f  ldarg.0
0x295a0  ldstr    aStatecode// "statecode"
0x295a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x295aa  ldarg.3
0x295ab  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ContractStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_statecode()
0x295b0  ldc.i4.0
0x295b1  ldc.i4.0
0x295b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write403_ContractStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ContractStateInfo o, bool isNullable, bool needType)
0x295b7  ldarg.0
0x295b8  ldstr    aStatuscode// "statuscode"
0x295bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x295c2  ldarg.3
0x295c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_statuscode()
0x295c8  ldc.i4.0
0x295c9  ldc.i4.0
0x295ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x295cf  ldarg.0
0x295d0  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x295d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x295da  ldarg.3
0x295db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contract::get_timezoneruleversionnumber()
0x295e0  ldc.i4.0
0x295e1  ldc.i4.0
0x295e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x295e7  ldarg.0
  ... truncated ...
```
