# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write267_productpricelevel

- ea: `0x20180`
- end: `0x20417`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write267_productpricelevel`
- size: `663`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36670`
- `0x55a20`

## callees

- `0x5cf0`
- `0x5e50`
- `0x150d0`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x15430`
- `0x20180`

## string_xrefs

- `0x201c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x201d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x201ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20205`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2021d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20235`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2024d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20265`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2027d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20295`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x202ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x202c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x202dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x202f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2030d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20325`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2033d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20355`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2036d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20385`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2039d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x203b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x203cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x203e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x203fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20200`: `createdby`
- `0x20218`: `createdon`
- `0x202c0`: `overriddencreatedon`
- `0x201d0`: `amount`
- `0x201e8`: `amount_base`
- `0x20368`: `roundingoptionamount`
- `0x20380`: `roundingoptionamount_base`

## pseudocode

```c

```

## disassembly

```asm
0x20180  ldarg.3
0x20181  brtrue.s loc_20190
0x20183  ldarg.s  4
0x20185  brfalse.s loc_2018F
0x20187  ldarg.0
0x20188  ldarg.1
0x20189  ldarg.2
0x2018a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2018f  ret
0x20190  ldarg.s  5
0x20192  brtrue.s loc_201B0
0x20194  ldarg.3
0x20195  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2019a  stloc.0
0x2019b  ldloc.0
0x2019c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel
0x201a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x201a6  beq.s    loc_201B0
0x201a8  ldarg.0
0x201a9  ldarg.3
0x201aa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x201af  throw
0x201b0  ldarg.0
0x201b1  ldarg.1
0x201b2  ldarg.2
0x201b3  ldarg.3
0x201b4  ldc.i4.0
0x201b5  ldnull
0x201b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x201bb  ldarg.s  5
0x201bd  brfalse.s loc_201CF
0x201bf  ldarg.0
0x201c0  ldstr    aProductpricele// "productpricelevel"
0x201c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x201ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x201cf  ldarg.0
0x201d0  ldstr    aAmount// "amount"
0x201d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x201da  ldarg.3
0x201db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_amount()
0x201e0  ldc.i4.0
0x201e1  ldc.i4.0
0x201e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x201e7  ldarg.0
0x201e8  ldstr    aAmountBase// "amount_base"
0x201ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x201f2  ldarg.3
0x201f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_amount_base()
0x201f8  ldc.i4.0
0x201f9  ldc.i4.0
0x201fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x201ff  ldarg.0
0x20200  ldstr    aCreatedby// "createdby"
0x20205  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2020a  ldarg.3
0x2020b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_createdby()
0x20210  ldc.i4.0
0x20211  ldc.i4.0
0x20212  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20217  ldarg.0
0x20218  ldstr    aCreatedon// "createdon"
0x2021d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20222  ldarg.3
0x20223  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_createdon()
0x20228  ldc.i4.0
0x20229  ldc.i4.0
0x2022a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2022f  ldarg.0
0x20230  ldstr    aDiscounttypeid// "discounttypeid"
0x20235  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2023a  ldarg.3
0x2023b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_discounttypeid()
0x20240  ldc.i4.0
0x20241  ldc.i4.0
0x20242  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20247  ldarg.0
0x20248  ldstr    aExchangerate// "exchangerate"
0x2024d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20252  ldarg.3
0x20253  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_exchangerate()
0x20258  ldc.i4.0
0x20259  ldc.i4.0
0x2025a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x2025f  ldarg.0
0x20260  ldstr    aImportsequence// "importsequencenumber"
0x20265  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2026a  ldarg.3
0x2026b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_importsequencenumber()
0x20270  ldc.i4.0
0x20271  ldc.i4.0
0x20272  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x20277  ldarg.0
0x20278  ldstr    aModifiedby// "modifiedby"
0x2027d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20282  ldarg.3
0x20283  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_modifiedby()
0x20288  ldc.i4.0
0x20289  ldc.i4.0
0x2028a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2028f  ldarg.0
0x20290  ldstr    aModifiedon// "modifiedon"
0x20295  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2029a  ldarg.3
0x2029b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_modifiedon()
0x202a0  ldc.i4.0
0x202a1  ldc.i4.0
0x202a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x202a7  ldarg.0
0x202a8  ldstr    aOrganizationid// "organizationid"
0x202ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x202b2  ldarg.3
0x202b3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_organizationid()
0x202b8  ldc.i4.0
0x202b9  ldc.i4.0
0x202ba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x202bf  ldarg.0
0x202c0  ldstr    aOverriddencrea// "overriddencreatedon"
0x202c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x202ca  ldarg.3
0x202cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_overriddencreatedon()
0x202d0  ldc.i4.0
0x202d1  ldc.i4.0
0x202d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x202d7  ldarg.0
0x202d8  ldstr    aPercentage// "percentage"
0x202dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x202e2  ldarg.3
0x202e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_percentage()
0x202e8  ldc.i4.0
0x202e9  ldc.i4.0
0x202ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x202ef  ldarg.0
0x202f0  ldstr    aPricelevelid// "pricelevelid"
0x202f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x202fa  ldarg.3
0x202fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_pricelevelid()
0x20300  ldc.i4.0
0x20301  ldc.i4.0
0x20302  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20307  ldarg.0
0x20308  ldstr    aPricingmethodc// "pricingmethodcode"
0x2030d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20312  ldarg.3
0x20313  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_pricingmethodcode()
0x20318  ldc.i4.0
0x20319  ldc.i4.0
0x2031a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2031f  ldarg.0
0x20320  ldstr    aProductid// "productid"
0x20325  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2032a  ldarg.3
0x2032b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_productid()
0x20330  ldc.i4.0
0x20331  ldc.i4.0
0x20332  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20337  ldarg.0
0x20338  ldstr    aProductpricele_0// "productpricelevelid"
0x2033d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20342  ldarg.3
0x20343  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_productpricelevelid()
0x20348  ldc.i4.0
0x20349  ldc.i4.0
0x2034a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2034f  ldarg.0
0x20350  ldstr    aQuantitysellin// "quantitysellingcode"
0x20355  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2035a  ldarg.3
0x2035b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_quantitysellingcode()
0x20360  ldc.i4.0
0x20361  ldc.i4.0
0x20362  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x20367  ldarg.0
0x20368  ldstr    aRoundingoption// "roundingoptionamount"
0x2036d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20372  ldarg.3
0x20373  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_roundingoptionamount()
0x20378  ldc.i4.0
0x20379  ldc.i4.0
0x2037a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2037f  ldarg.0
0x20380  ldstr    aRoundingoption_0// "roundingoptionamount_base"
0x20385  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2038a  ldarg.3
0x2038b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_roundingoptionamount_base()
0x20390  ldc.i4.0
0x20391  ldc.i4.0
0x20392  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x20397  ldarg.0
0x20398  ldstr    aRoundingoption_1// "roundingoptioncode"
0x2039d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x203a2  ldarg.3
0x203a3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_roundingoptioncode()
0x203a8  ldc.i4.0
0x203a9  ldc.i4.0
0x203aa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x203af  ldarg.0
0x203b0  ldstr    aRoundingpolicy// "roundingpolicycode"
0x203b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x203ba  ldarg.3
0x203bb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_roundingpolicycode()
0x203c0  ldc.i4.0
0x203c1  ldc.i4.0
0x203c2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x203c7  ldarg.0
0x203c8  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x203cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x203d2  ldarg.3
0x203d3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_transactioncurrencyid()
0x203d8  ldc.i4.0
0x203d9  ldc.i4.0
0x203da  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x203df  ldarg.0
0x203e0  ldstr    aUomid// "uomid"
0x203e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x203ea  ldarg.3
0x203eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_uomid()
0x203f0  ldc.i4.0
0x203f1  ldc.i4.0
0x203f2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x203f7  ldarg.0
0x203f8  ldstr    aUomscheduleid// "uomscheduleid"
0x203fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20402  ldarg.3
0x20403  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.productpricelevel::get_uomscheduleid()
0x20408  ldc.i4.0
0x20409  ldc.i4.0
0x2040a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2040f  ldarg.0
0x20410  ldarg.3
0x20411  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x20416  ret
```
