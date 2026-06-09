# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write293_opportunityproduct

- ea: `0x22480`
- end: `0x2281b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write293_opportunityproduct`
- size: `923`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36a60`
- `0x55e80`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x150d0`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x15430`
- `0x22480`

## string_xrefs

- `0x224c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x224d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x224ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22505`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2251d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22535`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2254b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22563`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2257b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22593`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x225ab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x225c3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x225db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x225f3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2260b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22623`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2263b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22653`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2266b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22683`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2269b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x226b3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x226cb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x226e3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x226fb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22713`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22729`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22741`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22759`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22771`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22789`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x227a1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x227b9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x227d1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x227e9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22801`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x224d0`: `baseamount`
- `0x224e8`: `baseamount_base`
- `0x22500`: `createdby`
- `0x22518`: `createdon`
- `0x2255e`: `extendedamount`
- `0x22576`: `extendedamount_base`
- `0x225d6`: `manualdiscountamount`
- `0x225ee`: `manualdiscountamount_base`
- `0x2267e`: `overriddencreatedon`
- `0x227e4`: `volumediscountamount`
- `0x227fc`: `volumediscountamount_base`

## pseudocode

```c

```

## disassembly

```asm
0x22480  ldarg.3
0x22481  brtrue.s loc_22490
0x22483  ldarg.s  4
0x22485  brfalse.s loc_2248F
0x22487  ldarg.0
0x22488  ldarg.1
0x22489  ldarg.2
0x2248a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2248f  ret
0x22490  ldarg.s  5
0x22492  brtrue.s loc_224B0
0x22494  ldarg.3
0x22495  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2249a  stloc.0
0x2249b  ldloc.0
0x2249c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct
0x224a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x224a6  beq.s    loc_224B0
0x224a8  ldarg.0
0x224a9  ldarg.3
0x224aa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x224af  throw
0x224b0  ldarg.0
0x224b1  ldarg.1
0x224b2  ldarg.2
0x224b3  ldarg.3
0x224b4  ldc.i4.0
0x224b5  ldnull
0x224b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x224bb  ldarg.s  5
0x224bd  brfalse.s loc_224CF
0x224bf  ldarg.0
0x224c0  ldstr    aOpportunitypro// "opportunityproduct"
0x224c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x224ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x224cf  ldarg.0
0x224d0  ldstr    aBaseamount// "baseamount"
0x224d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x224da  ldarg.3
0x224db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_baseamount()
0x224e0  ldc.i4.0
0x224e1  ldc.i4.0
0x224e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x224e7  ldarg.0
0x224e8  ldstr    aBaseamountBase// "baseamount_base"
0x224ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x224f2  ldarg.3
0x224f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_baseamount_base()
0x224f8  ldc.i4.0
0x224f9  ldc.i4.0
0x224fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x224ff  ldarg.0
0x22500  ldstr    aCreatedby// "createdby"
0x22505  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2250a  ldarg.3
0x2250b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_createdby()
0x22510  ldc.i4.0
0x22511  ldc.i4.0
0x22512  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22517  ldarg.0
0x22518  ldstr    aCreatedon// "createdon"
0x2251d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22522  ldarg.3
0x22523  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_createdon()
0x22528  ldc.i4.0
0x22529  ldc.i4.0
0x2252a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2252f  ldarg.0
0x22530  ldstr    aDescription_0// "description"
0x22535  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2253a  ldarg.3
0x2253b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_description()
0x22540  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x22545  ldarg.0
0x22546  ldstr    aExchangerate// "exchangerate"
0x2254b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22550  ldarg.3
0x22551  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_exchangerate()
0x22556  ldc.i4.0
0x22557  ldc.i4.0
0x22558  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x2255d  ldarg.0
0x2255e  ldstr    aExtendedamount// "extendedamount"
0x22563  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22568  ldarg.3
0x22569  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_extendedamount()
0x2256e  ldc.i4.0
0x2256f  ldc.i4.0
0x22570  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x22575  ldarg.0
0x22576  ldstr    aExtendedamount_0// "extendedamount_base"
0x2257b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22580  ldarg.3
0x22581  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_extendedamount_base()
0x22586  ldc.i4.0
0x22587  ldc.i4.0
0x22588  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2258d  ldarg.0
0x2258e  ldstr    aImportsequence// "importsequencenumber"
0x22593  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22598  ldarg.3
0x22599  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_importsequencenumber()
0x2259e  ldc.i4.0
0x2259f  ldc.i4.0
0x225a0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x225a5  ldarg.0
0x225a6  ldstr    aIspriceoverrid// "ispriceoverridden"
0x225ab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x225b0  ldarg.3
0x225b1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_ispriceoverridden()
0x225b6  ldc.i4.0
0x225b7  ldc.i4.0
0x225b8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x225bd  ldarg.0
0x225be  ldstr    aIsproductoverr// "isproductoverridden"
0x225c3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x225c8  ldarg.3
0x225c9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_isproductoverridden()
0x225ce  ldc.i4.0
0x225cf  ldc.i4.0
0x225d0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x225d5  ldarg.0
0x225d6  ldstr    aManualdiscount// "manualdiscountamount"
0x225db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x225e0  ldarg.3
0x225e1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_manualdiscountamount()
0x225e6  ldc.i4.0
0x225e7  ldc.i4.0
0x225e8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x225ed  ldarg.0
0x225ee  ldstr    aManualdiscount_0// "manualdiscountamount_base"
0x225f3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x225f8  ldarg.3
0x225f9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_manualdiscountamount_base()
0x225fe  ldc.i4.0
0x225ff  ldc.i4.0
0x22600  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x22605  ldarg.0
0x22606  ldstr    aModifiedby// "modifiedby"
0x2260b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22610  ldarg.3
0x22611  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_modifiedby()
0x22616  ldc.i4.0
0x22617  ldc.i4.0
0x22618  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2261d  ldarg.0
0x2261e  ldstr    aModifiedon// "modifiedon"
0x22623  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22628  ldarg.3
0x22629  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_modifiedon()
0x2262e  ldc.i4.0
0x2262f  ldc.i4.0
0x22630  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22635  ldarg.0
0x22636  ldstr    aOpportunityid// "opportunityid"
0x2263b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22640  ldarg.3
0x22641  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_opportunityid()
0x22646  ldc.i4.0
0x22647  ldc.i4.0
0x22648  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2264d  ldarg.0
0x2264e  ldstr    aOpportunitypro_0// "opportunityproductid"
0x22653  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22658  ldarg.3
0x22659  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_opportunityproductid()
0x2265e  ldc.i4.0
0x2265f  ldc.i4.0
0x22660  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x22665  ldarg.0
0x22666  ldstr    aOpportunitysta_0// "opportunitystatecode"
0x2266b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22670  ldarg.3
0x22671  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_opportunitystatecode()
0x22676  ldc.i4.0
0x22677  ldc.i4.0
0x22678  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2267d  ldarg.0
0x2267e  ldstr    aOverriddencrea// "overriddencreatedon"
0x22683  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22688  ldarg.3
0x22689  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_overriddencreatedon()
0x2268e  ldc.i4.0
0x2268f  ldc.i4.0
0x22690  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22695  ldarg.0
0x22696  ldstr    aOwningbusiness// "owningbusinessunit"
0x2269b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x226a0  ldarg.3
0x226a1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_owningbusinessunit()
0x226a6  ldc.i4.0
0x226a7  ldc.i4.0
0x226a8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x226ad  ldarg.0
0x226ae  ldstr    aOwninguser// "owninguser"
0x226b3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x226b8  ldarg.3
0x226b9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_owninguser()
0x226be  ldc.i4.0
0x226bf  ldc.i4.0
0x226c0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x226c5  ldarg.0
0x226c6  ldstr    aPriceperunit// "priceperunit"
0x226cb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x226d0  ldarg.3
0x226d1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_priceperunit()
0x226d6  ldc.i4.0
0x226d7  ldc.i4.0
0x226d8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x226dd  ldarg.0
0x226de  ldstr    aPriceperunitBa// "priceperunit_base"
0x226e3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x226e8  ldarg.3
0x226e9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_priceperunit_base()
0x226ee  ldc.i4.0
0x226ef  ldc.i4.0
0x226f0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x226f5  ldarg.0
0x226f6  ldstr    aPricingerrorco// "pricingerrorcode"
0x226fb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22700  ldarg.3
0x22701  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_pricingerrorcode()
0x22706  ldc.i4.0
0x22707  ldc.i4.0
0x22708  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2270d  ldarg.0
0x2270e  ldstr    aProductdescrip// "productdescription"
0x22713  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22718  ldarg.3
0x22719  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_productdescription()
0x2271e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x22723  ldarg.0
0x22724  ldstr    aProductid// "productid"
0x22729  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2272e  ldarg.3
0x2272f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_productid()
0x22734  ldc.i4.0
0x22735  ldc.i4.0
0x22736  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2273b  ldarg.0
0x2273c  ldstr    aQuantity// "quantity"
0x22741  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22746  ldarg.3
0x22747  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_quantity()
0x2274c  ldc.i4.0
0x2274d  ldc.i4.0
0x2274e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x22753  ldarg.0
0x22754  ldstr    aTax// "tax"
0x22759  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2275e  ldarg.3
0x2275f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_tax()
0x22764  ldc.i4.0
0x22765  ldc.i4.0
0x22766  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2276b  ldarg.0
0x2276c  ldstr    aTaxBase// "tax_base"
0x22771  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22776  ldarg.3
0x22777  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_tax_base()
0x2277c  ldc.i4.0
0x2277d  ldc.i4.0
0x2277e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x22783  ldarg.0
0x22784  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x22789  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2278e  ldarg.3
0x2278f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_timezoneruleversionnumber()
0x22794  ldc.i4.0
0x22795  ldc.i4.0
0x22796  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2279b  ldarg.0
0x2279c  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x227a1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x227a6  ldarg.3
0x227a7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_transactioncurrencyid()
0x227ac  ldc.i4.0
0x227ad  ldc.i4.0
0x227ae  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x227b3  ldarg.0
0x227b4  ldstr    aUomid// "uomid"
0x227b9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x227be  ldarg.3
0x227bf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_uomid()
0x227c4  ldc.i4.0
0x227c5  ldc.i4.0
0x227c6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x227cb  ldarg.0
0x227cc  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x227d1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x227d6  ldarg.3
0x227d7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_utcconversiontimezonecode()
0x227dc  ldc.i4.0
0x227dd  ldc.i4.0
0x227de  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x227e3  ldarg.0
0x227e4  ldstr    aVolumediscount// "volumediscountamount"
0x227e9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x227ee  ldarg.3
0x227ef  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunityproduct::get_volumediscountamount()
  ... truncated ...
```
