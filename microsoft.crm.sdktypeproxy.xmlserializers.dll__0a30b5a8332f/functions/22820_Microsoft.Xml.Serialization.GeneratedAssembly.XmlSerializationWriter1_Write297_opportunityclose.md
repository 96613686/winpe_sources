# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write297_opportunityclose

- ea: `0x22820`
- end: `0x22b6f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write297_opportunityclose`
- size: `847`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36ad0`
- `0x55ef0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x150d0`
- `0x15180`
- `0x153c0`
- `0x15430`
- `0x16a10`
- `0x16cb0`
- `0x22820`
- `0x22b70`

## string_xrefs

- `0x22865`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22875`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2288d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x228a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x228bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x228d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x228ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22905`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2291b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22933`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2294b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22963`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22979`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22991`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x229a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x229c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x229d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x229f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22a09`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22a21`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22a39`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22a51`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22a69`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22a81`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22a99`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22ab1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22ac9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22ae1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22af9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22b0f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22b25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22b3d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22b55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2292e`: `createdby`
- `0x22946`: `createdon`
- `0x22a1c`: `overriddencreatedon`
- `0x22a7c`: `scheduledend`
- `0x22a94`: `scheduledstart`
- `0x22aac`: `serviceid`
- `0x229bc`: `isworkflowcreated`
- `0x22a64`: `scheduleddurationminutes`
- `0x22916`: `competitorid`

## pseudocode

```c

```

## disassembly

```asm
0x22820  ldarg.3
0x22821  brtrue.s loc_22830
0x22823  ldarg.s  4
0x22825  brfalse.s loc_2282F
0x22827  ldarg.0
0x22828  ldarg.1
0x22829  ldarg.2
0x2282a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2282f  ret
0x22830  ldarg.s  5
0x22832  brtrue.s loc_22850
0x22834  ldarg.3
0x22835  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2283a  stloc.0
0x2283b  ldloc.0
0x2283c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose
0x22841  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22846  beq.s    loc_22850
0x22848  ldarg.0
0x22849  ldarg.3
0x2284a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2284f  throw
0x22850  ldarg.0
0x22851  ldarg.1
0x22852  ldarg.2
0x22853  ldarg.3
0x22854  ldc.i4.0
0x22855  ldnull
0x22856  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2285b  ldarg.s  5
0x2285d  brfalse.s loc_2286F
0x2285f  ldarg.0
0x22860  ldstr    aOpportunityclo_0// "opportunityclose"
0x22865  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2286a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2286f  ldarg.0
0x22870  ldstr    aActivityid_0// "activityid"
0x22875  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2287a  ldarg.3
0x2287b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_activityid()
0x22880  ldc.i4.0
0x22881  ldc.i4.0
0x22882  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x22887  ldarg.0
0x22888  ldstr    aActualduration// "actualdurationminutes"
0x2288d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22892  ldarg.3
0x22893  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_actualdurationminutes()
0x22898  ldc.i4.0
0x22899  ldc.i4.0
0x2289a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2289f  ldarg.0
0x228a0  ldstr    aActualend// "actualend"
0x228a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x228aa  ldarg.3
0x228ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_actualend()
0x228b0  ldc.i4.0
0x228b1  ldc.i4.0
0x228b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x228b7  ldarg.0
0x228b8  ldstr    aActualrevenue// "actualrevenue"
0x228bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x228c2  ldarg.3
0x228c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_actualrevenue()
0x228c8  ldc.i4.0
0x228c9  ldc.i4.0
0x228ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x228cf  ldarg.0
0x228d0  ldstr    aActualrevenueB// "actualrevenue_base"
0x228d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x228da  ldarg.3
0x228db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_actualrevenue_base()
0x228e0  ldc.i4.0
0x228e1  ldc.i4.0
0x228e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x228e7  ldarg.0
0x228e8  ldstr    aActualstart// "actualstart"
0x228ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x228f2  ldarg.3
0x228f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_actualstart()
0x228f8  ldc.i4.0
0x228f9  ldc.i4.0
0x228fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x228ff  ldarg.0
0x22900  ldstr    aCategory// "category"
0x22905  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2290a  ldarg.3
0x2290b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_category()
0x22910  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x22915  ldarg.0
0x22916  ldstr    aCompetitorid// "competitorid"
0x2291b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22920  ldarg.3
0x22921  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_competitorid()
0x22926  ldc.i4.0
0x22927  ldc.i4.0
0x22928  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2292d  ldarg.0
0x2292e  ldstr    aCreatedby// "createdby"
0x22933  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22938  ldarg.3
0x22939  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_createdby()
0x2293e  ldc.i4.0
0x2293f  ldc.i4.0
0x22940  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22945  ldarg.0
0x22946  ldstr    aCreatedon// "createdon"
0x2294b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22950  ldarg.3
0x22951  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_createdon()
0x22956  ldc.i4.0
0x22957  ldc.i4.0
0x22958  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2295d  ldarg.0
0x2295e  ldstr    aDescription_0// "description"
0x22963  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22968  ldarg.3
0x22969  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_description()
0x2296e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x22973  ldarg.0
0x22974  ldstr    aExchangerate// "exchangerate"
0x22979  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2297e  ldarg.3
0x2297f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_exchangerate()
0x22984  ldc.i4.0
0x22985  ldc.i4.0
0x22986  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x2298b  ldarg.0
0x2298c  ldstr    aImportsequence// "importsequencenumber"
0x22991  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22996  ldarg.3
0x22997  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_importsequencenumber()
0x2299c  ldc.i4.0
0x2299d  ldc.i4.0
0x2299e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x229a3  ldarg.0
0x229a4  ldstr    aIsbilled// "isbilled"
0x229a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x229ae  ldarg.3
0x229af  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_isbilled()
0x229b4  ldc.i4.0
0x229b5  ldc.i4.0
0x229b6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x229bb  ldarg.0
0x229bc  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x229c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x229c6  ldarg.3
0x229c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_isworkflowcreated()
0x229cc  ldc.i4.0
0x229cd  ldc.i4.0
0x229ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x229d3  ldarg.0
0x229d4  ldstr    aModifiedby// "modifiedby"
0x229d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x229de  ldarg.3
0x229df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_modifiedby()
0x229e4  ldc.i4.0
0x229e5  ldc.i4.0
0x229e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x229eb  ldarg.0
0x229ec  ldstr    aModifiedon// "modifiedon"
0x229f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x229f6  ldarg.3
0x229f7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_modifiedon()
0x229fc  ldc.i4.0
0x229fd  ldc.i4.0
0x229fe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22a03  ldarg.0
0x22a04  ldstr    aOpportunityid// "opportunityid"
0x22a09  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22a0e  ldarg.3
0x22a0f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_opportunityid()
0x22a14  ldc.i4.0
0x22a15  ldc.i4.0
0x22a16  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22a1b  ldarg.0
0x22a1c  ldstr    aOverriddencrea// "overriddencreatedon"
0x22a21  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22a26  ldarg.3
0x22a27  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_overriddencreatedon()
0x22a2c  ldc.i4.0
0x22a2d  ldc.i4.0
0x22a2e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22a33  ldarg.0
0x22a34  ldstr    aOwnerid// "ownerid"
0x22a39  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22a3e  ldarg.3
0x22a3f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_ownerid()
0x22a44  ldc.i4.0
0x22a45  ldc.i4.0
0x22a46  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x22a4b  ldarg.0
0x22a4c  ldstr    aOwningbusiness// "owningbusinessunit"
0x22a51  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22a56  ldarg.3
0x22a57  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_owningbusinessunit()
0x22a5c  ldc.i4.0
0x22a5d  ldc.i4.0
0x22a5e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22a63  ldarg.0
0x22a64  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x22a69  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22a6e  ldarg.3
0x22a6f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_scheduleddurationminutes()
0x22a74  ldc.i4.0
0x22a75  ldc.i4.0
0x22a76  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x22a7b  ldarg.0
0x22a7c  ldstr    aScheduledend// "scheduledend"
0x22a81  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22a86  ldarg.3
0x22a87  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_scheduledend()
0x22a8c  ldc.i4.0
0x22a8d  ldc.i4.0
0x22a8e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22a93  ldarg.0
0x22a94  ldstr    aScheduledstart// "scheduledstart"
0x22a99  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22a9e  ldarg.3
0x22a9f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_scheduledstart()
0x22aa4  ldc.i4.0
0x22aa5  ldc.i4.0
0x22aa6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22aab  ldarg.0
0x22aac  ldstr    aServiceid// "serviceid"
0x22ab1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22ab6  ldarg.3
0x22ab7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_serviceid()
0x22abc  ldc.i4.0
0x22abd  ldc.i4.0
0x22abe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22ac3  ldarg.0
0x22ac4  ldstr    aStatecode// "statecode"
0x22ac9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22ace  ldarg.3
0x22acf  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.OpportunityCloseStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_statecode()
0x22ad4  ldc.i4.0
0x22ad5  ldc.i4.0
0x22ad6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write296_OpportunityCloseStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.OpportunityCloseStateInfo o, bool isNullable, bool needType)
0x22adb  ldarg.0
0x22adc  ldstr    aStatuscode// "statuscode"
0x22ae1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22ae6  ldarg.3
0x22ae7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_statuscode()
0x22aec  ldc.i4.0
0x22aed  ldc.i4.0
0x22aee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x22af3  ldarg.0
0x22af4  ldstr    aSubcategory// "subcategory"
0x22af9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22afe  ldarg.3
0x22aff  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_subcategory()
0x22b04  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x22b09  ldarg.0
0x22b0a  ldstr    aSubject// "subject"
0x22b0f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22b14  ldarg.3
0x22b15  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_subject()
0x22b1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x22b1f  ldarg.0
0x22b20  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x22b25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22b2a  ldarg.3
0x22b2b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_timezoneruleversionnumber()
0x22b30  ldc.i4.0
0x22b31  ldc.i4.0
0x22b32  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x22b37  ldarg.0
0x22b38  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x22b3d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22b42  ldarg.3
0x22b43  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_transactioncurrencyid()
0x22b48  ldc.i4.0
0x22b49  ldc.i4.0
0x22b4a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22b4f  ldarg.0
0x22b50  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x22b55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22b5a  ldarg.3
0x22b5b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityclose::get_utcconversiontimezonecode()
0x22b60  ldc.i4.0
0x22b61  ldc.i4.0
0x22b62  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x22b67  ldarg.0
0x22b68  ldarg.3
0x22b69  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x22b6e  ret
```
