# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write388_discount

- ea: `0x28280`
- end: `0x28487`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write388_discount`
- size: `519`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37780`
- `0x56ba0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x150d0`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x15430`
- `0x16cb0`
- `0x28280`

## string_xrefs

- `0x282c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x282d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x282ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28305`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2831d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28335`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2834d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28365`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2837d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28395`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x283ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x283c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x283dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x283f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2840d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28425`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2843d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28455`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2846d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28300`: `createdby`
- `0x28318`: `createdon`
- `0x28420`: `overriddencreatedon`
- `0x282d0`: `amount`
- `0x282e8`: `amount_base`
- `0x283a8`: `isamounttype`

## pseudocode

```c

```

## disassembly

```asm
0x28280  ldarg.3
0x28281  brtrue.s loc_28290
0x28283  ldarg.s  4
0x28285  brfalse.s loc_2828F
0x28287  ldarg.0
0x28288  ldarg.1
0x28289  ldarg.2
0x2828a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2828f  ret
0x28290  ldarg.s  5
0x28292  brtrue.s loc_282B0
0x28294  ldarg.3
0x28295  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2829a  stloc.0
0x2829b  ldloc.0
0x2829c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount
0x282a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x282a6  beq.s    loc_282B0
0x282a8  ldarg.0
0x282a9  ldarg.3
0x282aa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x282af  throw
0x282b0  ldarg.0
0x282b1  ldarg.1
0x282b2  ldarg.2
0x282b3  ldarg.3
0x282b4  ldc.i4.0
0x282b5  ldnull
0x282b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x282bb  ldarg.s  5
0x282bd  brfalse.s loc_282CF
0x282bf  ldarg.0
0x282c0  ldstr    aDiscount// "discount"
0x282c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x282ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x282cf  ldarg.0
0x282d0  ldstr    aAmount// "amount"
0x282d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x282da  ldarg.3
0x282db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_amount()
0x282e0  ldc.i4.0
0x282e1  ldc.i4.0
0x282e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x282e7  ldarg.0
0x282e8  ldstr    aAmountBase// "amount_base"
0x282ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x282f2  ldarg.3
0x282f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_amount_base()
0x282f8  ldc.i4.0
0x282f9  ldc.i4.0
0x282fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x282ff  ldarg.0
0x28300  ldstr    aCreatedby// "createdby"
0x28305  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2830a  ldarg.3
0x2830b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_createdby()
0x28310  ldc.i4.0
0x28311  ldc.i4.0
0x28312  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28317  ldarg.0
0x28318  ldstr    aCreatedon// "createdon"
0x2831d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28322  ldarg.3
0x28323  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_createdon()
0x28328  ldc.i4.0
0x28329  ldc.i4.0
0x2832a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2832f  ldarg.0
0x28330  ldstr    aDiscountid// "discountid"
0x28335  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2833a  ldarg.3
0x2833b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_discountid()
0x28340  ldc.i4.0
0x28341  ldc.i4.0
0x28342  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x28347  ldarg.0
0x28348  ldstr    aDiscounttypeid// "discounttypeid"
0x2834d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28352  ldarg.3
0x28353  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_discounttypeid()
0x28358  ldc.i4.0
0x28359  ldc.i4.0
0x2835a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2835f  ldarg.0
0x28360  ldstr    aExchangerate// "exchangerate"
0x28365  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2836a  ldarg.3
0x2836b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_exchangerate()
0x28370  ldc.i4.0
0x28371  ldc.i4.0
0x28372  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x28377  ldarg.0
0x28378  ldstr    aHighquantity// "highquantity"
0x2837d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28382  ldarg.3
0x28383  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_highquantity()
0x28388  ldc.i4.0
0x28389  ldc.i4.0
0x2838a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x2838f  ldarg.0
0x28390  ldstr    aImportsequence// "importsequencenumber"
0x28395  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2839a  ldarg.3
0x2839b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_importsequencenumber()
0x283a0  ldc.i4.0
0x283a1  ldc.i4.0
0x283a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x283a7  ldarg.0
0x283a8  ldstr    aIsamounttype// "isamounttype"
0x283ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x283b2  ldarg.3
0x283b3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_isamounttype()
0x283b8  ldc.i4.0
0x283b9  ldc.i4.0
0x283ba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x283bf  ldarg.0
0x283c0  ldstr    aLowquantity// "lowquantity"
0x283c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x283ca  ldarg.3
0x283cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_lowquantity()
0x283d0  ldc.i4.0
0x283d1  ldc.i4.0
0x283d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x283d7  ldarg.0
0x283d8  ldstr    aModifiedby// "modifiedby"
0x283dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x283e2  ldarg.3
0x283e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_modifiedby()
0x283e8  ldc.i4.0
0x283e9  ldc.i4.0
0x283ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x283ef  ldarg.0
0x283f0  ldstr    aModifiedon// "modifiedon"
0x283f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x283fa  ldarg.3
0x283fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_modifiedon()
0x28400  ldc.i4.0
0x28401  ldc.i4.0
0x28402  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28407  ldarg.0
0x28408  ldstr    aOrganizationid// "organizationid"
0x2840d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28412  ldarg.3
0x28413  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_organizationid()
0x28418  ldc.i4.0
0x28419  ldc.i4.0
0x2841a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x2841f  ldarg.0
0x28420  ldstr    aOverriddencrea// "overriddencreatedon"
0x28425  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2842a  ldarg.3
0x2842b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_overriddencreatedon()
0x28430  ldc.i4.0
0x28431  ldc.i4.0
0x28432  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28437  ldarg.0
0x28438  ldstr    aPercentage// "percentage"
0x2843d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28442  ldarg.3
0x28443  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_percentage()
0x28448  ldc.i4.0
0x28449  ldc.i4.0
0x2844a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x2844f  ldarg.0
0x28450  ldstr    aStatuscode// "statuscode"
0x28455  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2845a  ldarg.3
0x2845b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_statuscode()
0x28460  ldc.i4.0
0x28461  ldc.i4.0
0x28462  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x28467  ldarg.0
0x28468  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x2846d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28472  ldarg.3
0x28473  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discount::get_transactioncurrencyid()
0x28478  ldc.i4.0
0x28479  ldc.i4.0
0x2847a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2847f  ldarg.0
0x28480  ldarg.3
0x28481  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x28486  ret
```
