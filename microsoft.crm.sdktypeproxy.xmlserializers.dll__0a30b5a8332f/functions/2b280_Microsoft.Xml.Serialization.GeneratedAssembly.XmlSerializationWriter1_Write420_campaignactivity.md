# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write420_campaignactivity

- ea: `0x2b280`
- end: `0x2b706`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write420_campaignactivity`
- size: `1158`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37c50`
- `0x570e0`

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
- `0x19770`
- `0x2b280`
- `0x2b710`

## string_xrefs

- `0x2b2c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b2d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b2ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b305`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b31d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b335`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b34d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b365`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b37d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b395`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b3ab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b3c3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b3db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b3f3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b409`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b421`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b439`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b45b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b471`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b496`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b4ae`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b4c6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b4de`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b4f6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b50e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b526`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b53e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b556`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b578`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b58f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b5b8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b5d0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b5e8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b600`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b618`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b630`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b648`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b660`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b678`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b68e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b6a4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b6bc`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b6d4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b6ec`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b3be`: `createdby`
- `0x2b3d6`: `createdon`
- `0x2b521`: `overriddencreatedon`
- `0x2b5fb`: `scheduledend`
- `0x2b613`: `scheduledstart`
- `0x2b62b`: `serviceid`
- `0x2b4d9`: `isworkflowcreated`
- `0x2b5e3`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x2b280  ldarg.3
0x2b281  brtrue.s loc_2B290
0x2b283  ldarg.s  4
0x2b285  brfalse.s loc_2B28F
0x2b287  ldarg.0
0x2b288  ldarg.1
0x2b289  ldarg.2
0x2b28a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2b28f  ret
0x2b290  ldarg.s  5
0x2b292  brtrue.s loc_2B2B0
0x2b294  ldarg.3
0x2b295  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2b29a  stloc.0
0x2b29b  ldloc.0
0x2b29c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity
0x2b2a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b2a6  beq.s    loc_2B2B0
0x2b2a8  ldarg.0
0x2b2a9  ldarg.3
0x2b2aa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2b2af  throw
0x2b2b0  ldarg.0
0x2b2b1  ldarg.1
0x2b2b2  ldarg.2
0x2b2b3  ldarg.3
0x2b2b4  ldc.i4.0
0x2b2b5  ldnull
0x2b2b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2b2bb  ldarg.s  5
0x2b2bd  brfalse.s loc_2B2CF
0x2b2bf  ldarg.0
0x2b2c0  ldstr    aCampaignactivi_0// "campaignactivity"
0x2b2c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b2ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2b2cf  ldarg.0
0x2b2d0  ldstr    aActivityid_0// "activityid"
0x2b2d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b2da  ldarg.3
0x2b2db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_activityid()
0x2b2e0  ldc.i4.0
0x2b2e1  ldc.i4.0
0x2b2e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2b2e7  ldarg.0
0x2b2e8  ldstr    aActualcost// "actualcost"
0x2b2ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b2f2  ldarg.3
0x2b2f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_actualcost()
0x2b2f8  ldc.i4.0
0x2b2f9  ldc.i4.0
0x2b2fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2b2ff  ldarg.0
0x2b300  ldstr    aActualcostBase// "actualcost_base"
0x2b305  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b30a  ldarg.3
0x2b30b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_actualcost_base()
0x2b310  ldc.i4.0
0x2b311  ldc.i4.0
0x2b312  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2b317  ldarg.0
0x2b318  ldstr    aActualduration// "actualdurationminutes"
0x2b31d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b322  ldarg.3
0x2b323  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_actualdurationminutes()
0x2b328  ldc.i4.0
0x2b329  ldc.i4.0
0x2b32a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2b32f  ldarg.0
0x2b330  ldstr    aActualend// "actualend"
0x2b335  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b33a  ldarg.3
0x2b33b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_actualend()
0x2b340  ldc.i4.0
0x2b341  ldc.i4.0
0x2b342  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2b347  ldarg.0
0x2b348  ldstr    aActualstart// "actualstart"
0x2b34d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b352  ldarg.3
0x2b353  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_actualstart()
0x2b358  ldc.i4.0
0x2b359  ldc.i4.0
0x2b35a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2b35f  ldarg.0
0x2b360  ldstr    aBudgetedcost// "budgetedcost"
0x2b365  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b36a  ldarg.3
0x2b36b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_budgetedcost()
0x2b370  ldc.i4.0
0x2b371  ldc.i4.0
0x2b372  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2b377  ldarg.0
0x2b378  ldstr    aBudgetedcostBa// "budgetedcost_base"
0x2b37d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b382  ldarg.3
0x2b383  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_budgetedcost_base()
0x2b388  ldc.i4.0
0x2b389  ldc.i4.0
0x2b38a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2b38f  ldarg.0
0x2b390  ldstr    aCategory// "category"
0x2b395  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b39a  ldarg.3
0x2b39b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_category()
0x2b3a0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2b3a5  ldarg.0
0x2b3a6  ldstr    aChanneltypecod// "channeltypecode"
0x2b3ab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b3b0  ldarg.3
0x2b3b1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_channeltypecode()
0x2b3b6  ldc.i4.0
0x2b3b7  ldc.i4.0
0x2b3b8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2b3bd  ldarg.0
0x2b3be  ldstr    aCreatedby// "createdby"
0x2b3c3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b3c8  ldarg.3
0x2b3c9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_createdby()
0x2b3ce  ldc.i4.0
0x2b3cf  ldc.i4.0
0x2b3d0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2b3d5  ldarg.0
0x2b3d6  ldstr    aCreatedon// "createdon"
0x2b3db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b3e0  ldarg.3
0x2b3e1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_createdon()
0x2b3e6  ldc.i4.0
0x2b3e7  ldc.i4.0
0x2b3e8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2b3ed  ldarg.0
0x2b3ee  ldstr    aDescription_0// "description"
0x2b3f3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b3f8  ldarg.3
0x2b3f9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_description()
0x2b3fe  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2b403  ldarg.0
0x2b404  ldstr    aDonotsendonopt// "donotsendonoptout"
0x2b409  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b40e  ldarg.3
0x2b40f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_donotsendonoptout()
0x2b414  ldc.i4.0
0x2b415  ldc.i4.0
0x2b416  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2b41b  ldarg.0
0x2b41c  ldstr    aExchangerate// "exchangerate"
0x2b421  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b426  ldarg.3
0x2b427  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_exchangerate()
0x2b42c  ldc.i4.0
0x2b42d  ldc.i4.0
0x2b42e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x2b433  ldarg.0
0x2b434  ldstr    aExcludeifconta// "excludeifcontactedinxdays"
0x2b439  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b43e  ldarg.3
0x2b43f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_excludeifcontactedinxdays()
0x2b444  ldc.i4.0
0x2b445  ldc.i4.0
0x2b446  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2b44b  ldarg.3
0x2b44c  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_from()
0x2b451  stloc.1
0x2b452  ldloc.1
0x2b453  brfalse.s loc_2B490
0x2b455  ldarg.0
0x2b456  ldstr    aFrom_0// "from"
0x2b45b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b460  ldnull
0x2b461  ldc.i4.0
0x2b462  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x2b467  ldc.i4.0
0x2b468  stloc.2
0x2b469  br.s     loc_2B484
0x2b46b  ldarg.0
0x2b46c  ldstr    aActivityparty// "activityparty"
0x2b471  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b476  ldloc.1
0x2b477  ldloc.2
0x2b478  ldelem.ref
0x2b479  ldc.i4.0
0x2b47a  ldc.i4.0
0x2b47b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x2b480  ldloc.2
0x2b481  ldc.i4.1
0x2b482  add
0x2b483  stloc.2
0x2b484  ldloc.2
0x2b485  ldloc.1
0x2b486  ldlen
0x2b487  conv.i4
0x2b488  blt.s    loc_2B46B
0x2b48a  ldarg.0
0x2b48b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x2b490  ldarg.0
0x2b491  ldstr    aIgnoreinactive// "ignoreinactivelistmembers"
0x2b496  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b49b  ldarg.3
0x2b49c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_ignoreinactivelistmembers()
0x2b4a1  ldc.i4.0
0x2b4a2  ldc.i4.0
0x2b4a3  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2b4a8  ldarg.0
0x2b4a9  ldstr    aImportsequence// "importsequencenumber"
0x2b4ae  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b4b3  ldarg.3
0x2b4b4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_importsequencenumber()
0x2b4b9  ldc.i4.0
0x2b4ba  ldc.i4.0
0x2b4bb  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2b4c0  ldarg.0
0x2b4c1  ldstr    aIsbilled// "isbilled"
0x2b4c6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b4cb  ldarg.3
0x2b4cc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_isbilled()
0x2b4d1  ldc.i4.0
0x2b4d2  ldc.i4.0
0x2b4d3  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2b4d8  ldarg.0
0x2b4d9  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x2b4de  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b4e3  ldarg.3
0x2b4e4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_isworkflowcreated()
0x2b4e9  ldc.i4.0
0x2b4ea  ldc.i4.0
0x2b4eb  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2b4f0  ldarg.0
0x2b4f1  ldstr    aModifiedby// "modifiedby"
0x2b4f6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b4fb  ldarg.3
0x2b4fc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_modifiedby()
0x2b501  ldc.i4.0
0x2b502  ldc.i4.0
0x2b503  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2b508  ldarg.0
0x2b509  ldstr    aModifiedon// "modifiedon"
0x2b50e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b513  ldarg.3
0x2b514  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_modifiedon()
0x2b519  ldc.i4.0
0x2b51a  ldc.i4.0
0x2b51b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2b520  ldarg.0
0x2b521  ldstr    aOverriddencrea// "overriddencreatedon"
0x2b526  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b52b  ldarg.3
0x2b52c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_overriddencreatedon()
0x2b531  ldc.i4.0
0x2b532  ldc.i4.0
0x2b533  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2b538  ldarg.0
0x2b539  ldstr    aOwnerid// "ownerid"
0x2b53e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b543  ldarg.3
0x2b544  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_ownerid()
0x2b549  ldc.i4.0
0x2b54a  ldc.i4.0
0x2b54b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2b550  ldarg.0
0x2b551  ldstr    aOwningbusiness// "owningbusinessunit"
0x2b556  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b55b  ldarg.3
0x2b55c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_owningbusinessunit()
0x2b561  ldc.i4.0
0x2b562  ldc.i4.0
0x2b563  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2b568  ldarg.3
0x2b569  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::get_partners()
0x2b56e  stloc.3
0x2b56f  ldloc.3
0x2b570  brfalse.s loc_2B5B2
0x2b572  ldarg.0
0x2b573  ldstr    aPartners// "partners"
0x2b578  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b57d  ldnull
0x2b57e  ldc.i4.0
0x2b57f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x2b584  ldc.i4.0
0x2b585  stloc.s  4
0x2b587  br.s     loc_2B5A5
0x2b589  ldarg.0
0x2b58a  ldstr    aActivityparty// "activityparty"
0x2b58f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b594  ldloc.3
0x2b595  ldloc.s  4
0x2b597  ldelem.ref
0x2b598  ldc.i4.0
0x2b599  ldc.i4.0
0x2b59a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x2b59f  ldloc.s  4
0x2b5a1  ldc.i4.1
0x2b5a2  add
0x2b5a3  stloc.s  4
0x2b5a5  ldloc.s  4
0x2b5a7  ldloc.3
0x2b5a8  ldlen
0x2b5a9  conv.i4
0x2b5aa  blt.s    loc_2B589
0x2b5ac  ldarg.0
0x2b5ad  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x2b5b2  ldarg.0
  ... truncated ...
```
