# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write301_opportunity

- ea: `0x22bf0`
- end: `0x22fa1`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write301_opportunity`
- size: `945`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36b40`
- `0x55f60`

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
- `0x16a10`
- `0x16cb0`
- `0x170c0`
- `0x22bf0`
- `0x22fb0`

## string_xrefs

- `0x22c35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22c45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22c5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22c75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22c8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22ca5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22cbd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22cd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22ced`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22d05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22d1b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22d33`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22d4b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22d63`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22d7b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22d93`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22dab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22dc3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22ddb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22df1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22e09`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22e21`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22e39`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22e51`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22e69`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22e81`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22e99`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22eb1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22ec9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22ee1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22ef9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22f11`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22f29`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22f41`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22f57`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22f6f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22f87`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22cb8`: `createdby`
- `0x22cd0`: `createdon`
- `0x22e34`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x22bf0  ldarg.3
0x22bf1  brtrue.s loc_22C00
0x22bf3  ldarg.s  4
0x22bf5  brfalse.s loc_22BFF
0x22bf7  ldarg.0
0x22bf8  ldarg.1
0x22bf9  ldarg.2
0x22bfa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x22bff  ret
0x22c00  ldarg.s  5
0x22c02  brtrue.s loc_22C20
0x22c04  ldarg.3
0x22c05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22c0a  stloc.0
0x22c0b  ldloc.0
0x22c0c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity
0x22c11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22c16  beq.s    loc_22C20
0x22c18  ldarg.0
0x22c19  ldarg.3
0x22c1a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x22c1f  throw
0x22c20  ldarg.0
0x22c21  ldarg.1
0x22c22  ldarg.2
0x22c23  ldarg.3
0x22c24  ldc.i4.0
0x22c25  ldnull
0x22c26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x22c2b  ldarg.s  5
0x22c2d  brfalse.s loc_22C3F
0x22c2f  ldarg.0
0x22c30  ldstr    aOpportunity// "opportunity"
0x22c35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22c3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x22c3f  ldarg.0
0x22c40  ldstr    aActualclosedat// "actualclosedate"
0x22c45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22c4a  ldarg.3
0x22c4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_actualclosedate()
0x22c50  ldc.i4.0
0x22c51  ldc.i4.0
0x22c52  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22c57  ldarg.0
0x22c58  ldstr    aActualvalue// "actualvalue"
0x22c5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22c62  ldarg.3
0x22c63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_actualvalue()
0x22c68  ldc.i4.0
0x22c69  ldc.i4.0
0x22c6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x22c6f  ldarg.0
0x22c70  ldstr    aActualvalueBas// "actualvalue_base"
0x22c75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22c7a  ldarg.3
0x22c7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_actualvalue_base()
0x22c80  ldc.i4.0
0x22c81  ldc.i4.0
0x22c82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x22c87  ldarg.0
0x22c88  ldstr    aCampaignid// "campaignid"
0x22c8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22c92  ldarg.3
0x22c93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_campaignid()
0x22c98  ldc.i4.0
0x22c99  ldc.i4.0
0x22c9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22c9f  ldarg.0
0x22ca0  ldstr    aCloseprobabili// "closeprobability"
0x22ca5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22caa  ldarg.3
0x22cab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_closeprobability()
0x22cb0  ldc.i4.0
0x22cb1  ldc.i4.0
0x22cb2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x22cb7  ldarg.0
0x22cb8  ldstr    aCreatedby// "createdby"
0x22cbd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22cc2  ldarg.3
0x22cc3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_createdby()
0x22cc8  ldc.i4.0
0x22cc9  ldc.i4.0
0x22cca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22ccf  ldarg.0
0x22cd0  ldstr    aCreatedon// "createdon"
0x22cd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22cda  ldarg.3
0x22cdb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_createdon()
0x22ce0  ldc.i4.0
0x22ce1  ldc.i4.0
0x22ce2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22ce7  ldarg.0
0x22ce8  ldstr    aCustomerid// "customerid"
0x22ced  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22cf2  ldarg.3
0x22cf3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_customerid()
0x22cf8  ldc.i4.0
0x22cf9  ldc.i4.0
0x22cfa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write124_Customer(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer o, bool isNullable, bool needType)
0x22cff  ldarg.0
0x22d00  ldstr    aDescription_0// "description"
0x22d05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22d0a  ldarg.3
0x22d0b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_description()
0x22d10  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x22d15  ldarg.0
0x22d16  ldstr    aEstimatedclose// "estimatedclosedate"
0x22d1b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22d20  ldarg.3
0x22d21  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_estimatedclosedate()
0x22d26  ldc.i4.0
0x22d27  ldc.i4.0
0x22d28  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22d2d  ldarg.0
0x22d2e  ldstr    aEstimatedvalue// "estimatedvalue"
0x22d33  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22d38  ldarg.3
0x22d39  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_estimatedvalue()
0x22d3e  ldc.i4.0
0x22d3f  ldc.i4.0
0x22d40  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x22d45  ldarg.0
0x22d46  ldstr    aEstimatedvalue_0// "estimatedvalue_base"
0x22d4b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22d50  ldarg.3
0x22d51  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_estimatedvalue_base()
0x22d56  ldc.i4.0
0x22d57  ldc.i4.0
0x22d58  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x22d5d  ldarg.0
0x22d5e  ldstr    aExchangerate// "exchangerate"
0x22d63  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22d68  ldarg.3
0x22d69  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_exchangerate()
0x22d6e  ldc.i4.0
0x22d6f  ldc.i4.0
0x22d70  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x22d75  ldarg.0
0x22d76  ldstr    aImportsequence// "importsequencenumber"
0x22d7b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22d80  ldarg.3
0x22d81  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_importsequencenumber()
0x22d86  ldc.i4.0
0x22d87  ldc.i4.0
0x22d88  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x22d8d  ldarg.0
0x22d8e  ldstr    aIsrevenuesyste// "isrevenuesystemcalculated"
0x22d93  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22d98  ldarg.3
0x22d99  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_isrevenuesystemcalculated()
0x22d9e  ldc.i4.0
0x22d9f  ldc.i4.0
0x22da0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x22da5  ldarg.0
0x22da6  ldstr    aModifiedby// "modifiedby"
0x22dab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22db0  ldarg.3
0x22db1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_modifiedby()
0x22db6  ldc.i4.0
0x22db7  ldc.i4.0
0x22db8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22dbd  ldarg.0
0x22dbe  ldstr    aModifiedon// "modifiedon"
0x22dc3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22dc8  ldarg.3
0x22dc9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_modifiedon()
0x22dce  ldc.i4.0
0x22dcf  ldc.i4.0
0x22dd0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22dd5  ldarg.0
0x22dd6  ldstr    aName// "name"
0x22ddb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22de0  ldarg.3
0x22de1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_name()
0x22de6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x22deb  ldarg.0
0x22dec  ldstr    aOpportunityid// "opportunityid"
0x22df1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22df6  ldarg.3
0x22df7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_opportunityid()
0x22dfc  ldc.i4.0
0x22dfd  ldc.i4.0
0x22dfe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x22e03  ldarg.0
0x22e04  ldstr    aOpportunityrat// "opportunityratingcode"
0x22e09  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22e0e  ldarg.3
0x22e0f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_opportunityratingcode()
0x22e14  ldc.i4.0
0x22e15  ldc.i4.0
0x22e16  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x22e1b  ldarg.0
0x22e1c  ldstr    aOriginatinglea// "originatingleadid"
0x22e21  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22e26  ldarg.3
0x22e27  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_originatingleadid()
0x22e2c  ldc.i4.0
0x22e2d  ldc.i4.0
0x22e2e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22e33  ldarg.0
0x22e34  ldstr    aOverriddencrea// "overriddencreatedon"
0x22e39  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22e3e  ldarg.3
0x22e3f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_overriddencreatedon()
0x22e44  ldc.i4.0
0x22e45  ldc.i4.0
0x22e46  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22e4b  ldarg.0
0x22e4c  ldstr    aOwnerid// "ownerid"
0x22e51  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22e56  ldarg.3
0x22e57  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_ownerid()
0x22e5c  ldc.i4.0
0x22e5d  ldc.i4.0
0x22e5e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x22e63  ldarg.0
0x22e64  ldstr    aOwningbusiness// "owningbusinessunit"
0x22e69  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22e6e  ldarg.3
0x22e6f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_owningbusinessunit()
0x22e74  ldc.i4.0
0x22e75  ldc.i4.0
0x22e76  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22e7b  ldarg.0
0x22e7c  ldstr    aParticipatesin// "participatesinworkflow"
0x22e81  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22e86  ldarg.3
0x22e87  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_participatesinworkflow()
0x22e8c  ldc.i4.0
0x22e8d  ldc.i4.0
0x22e8e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x22e93  ldarg.0
0x22e94  ldstr    aPricelevelid// "pricelevelid"
0x22e99  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22e9e  ldarg.3
0x22e9f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_pricelevelid()
0x22ea4  ldc.i4.0
0x22ea5  ldc.i4.0
0x22ea6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22eab  ldarg.0
0x22eac  ldstr    aPricingerrorco// "pricingerrorcode"
0x22eb1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22eb6  ldarg.3
0x22eb7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_pricingerrorcode()
0x22ebc  ldc.i4.0
0x22ebd  ldc.i4.0
0x22ebe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x22ec3  ldarg.0
0x22ec4  ldstr    aPrioritycode// "prioritycode"
0x22ec9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22ece  ldarg.3
0x22ecf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_prioritycode()
0x22ed4  ldc.i4.0
0x22ed5  ldc.i4.0
0x22ed6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x22edb  ldarg.0
0x22edc  ldstr    aSalesstagecode// "salesstagecode"
0x22ee1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22ee6  ldarg.3
0x22ee7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_salesstagecode()
0x22eec  ldc.i4.0
0x22eed  ldc.i4.0
0x22eee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x22ef3  ldarg.0
0x22ef4  ldstr    aStatecode// "statecode"
0x22ef9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22efe  ldarg.3
0x22eff  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.OpportunityStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_statecode()
0x22f04  ldc.i4.0
0x22f05  ldc.i4.0
0x22f06  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write300_OpportunityStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.OpportunityStateInfo o, bool isNullable, bool needType)
0x22f0b  ldarg.0
0x22f0c  ldstr    aStatuscode// "statuscode"
0x22f11  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22f16  ldarg.3
0x22f17  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_statuscode()
0x22f1c  ldc.i4.0
0x22f1d  ldc.i4.0
0x22f1e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x22f23  ldarg.0
0x22f24  ldstr    aStepid// "stepid"
0x22f29  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22f2e  ldarg.3
0x22f2f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_stepid()
0x22f34  ldc.i4.0
0x22f35  ldc.i4.0
0x22f36  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x22f3b  ldarg.0
0x22f3c  ldstr    aStepname// "stepname"
0x22f41  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22f46  ldarg.3
0x22f47  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_stepname()
0x22f4c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x22f51  ldarg.0
0x22f52  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x22f57  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22f5c  ldarg.3
0x22f5d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.opportunity::get_timezoneruleversionnumber()
0x22f62  ldc.i4.0
0x22f63  ldc.i4.0
  ... truncated ...
```
