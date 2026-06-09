# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write424_campaign

- ea: `0x2b790`
- end: `0x2bb83`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write424_campaign`
- size: `1011`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37cc0`
- `0x57150`

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
- `0x2b790`
- `0x2bb90`

## string_xrefs

- `0x2b7d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b7e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b7fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b815`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b82d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b845`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b85d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b873`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b88b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b8a3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b8b9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b8d1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b8e9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b901`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b919`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b931`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b949`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b95f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b977`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b98f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b9a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b9bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b9d3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b9eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ba03`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ba1b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ba33`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ba4b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ba61`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ba79`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ba91`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2baa9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bac1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bad9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2baf1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bb09`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bb21`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bb39`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bb51`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2bb69`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b86e`: `createdby`
- `0x2b886`: `createdon`
- `0x2b9e6`: `overriddencreatedon`
- `0x2b92c`: `istemplate`

## pseudocode

```c

```

## disassembly

```asm
0x2b790  ldarg.3
0x2b791  brtrue.s loc_2B7A0
0x2b793  ldarg.s  4
0x2b795  brfalse.s loc_2B79F
0x2b797  ldarg.0
0x2b798  ldarg.1
0x2b799  ldarg.2
0x2b79a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2b79f  ret
0x2b7a0  ldarg.s  5
0x2b7a2  brtrue.s loc_2B7C0
0x2b7a4  ldarg.3
0x2b7a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2b7aa  stloc.0
0x2b7ab  ldloc.0
0x2b7ac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign
0x2b7b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b7b6  beq.s    loc_2B7C0
0x2b7b8  ldarg.0
0x2b7b9  ldarg.3
0x2b7ba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2b7bf  throw
0x2b7c0  ldarg.0
0x2b7c1  ldarg.1
0x2b7c2  ldarg.2
0x2b7c3  ldarg.3
0x2b7c4  ldc.i4.0
0x2b7c5  ldnull
0x2b7c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2b7cb  ldarg.s  5
0x2b7cd  brfalse.s loc_2B7DF
0x2b7cf  ldarg.0
0x2b7d0  ldstr    aCampaign// "campaign"
0x2b7d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b7da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2b7df  ldarg.0
0x2b7e0  ldstr    aActualend// "actualend"
0x2b7e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b7ea  ldarg.3
0x2b7eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_actualend()
0x2b7f0  ldc.i4.0
0x2b7f1  ldc.i4.0
0x2b7f2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2b7f7  ldarg.0
0x2b7f8  ldstr    aActualstart// "actualstart"
0x2b7fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b802  ldarg.3
0x2b803  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_actualstart()
0x2b808  ldc.i4.0
0x2b809  ldc.i4.0
0x2b80a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2b80f  ldarg.0
0x2b810  ldstr    aBudgetedcost// "budgetedcost"
0x2b815  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b81a  ldarg.3
0x2b81b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_budgetedcost()
0x2b820  ldc.i4.0
0x2b821  ldc.i4.0
0x2b822  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2b827  ldarg.0
0x2b828  ldstr    aBudgetedcostBa// "budgetedcost_base"
0x2b82d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b832  ldarg.3
0x2b833  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_budgetedcost_base()
0x2b838  ldc.i4.0
0x2b839  ldc.i4.0
0x2b83a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2b83f  ldarg.0
0x2b840  ldstr    aCampaignid// "campaignid"
0x2b845  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b84a  ldarg.3
0x2b84b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_campaignid()
0x2b850  ldc.i4.0
0x2b851  ldc.i4.0
0x2b852  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2b857  ldarg.0
0x2b858  ldstr    aCodename// "codename"
0x2b85d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b862  ldarg.3
0x2b863  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_codename()
0x2b868  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2b86d  ldarg.0
0x2b86e  ldstr    aCreatedby// "createdby"
0x2b873  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b878  ldarg.3
0x2b879  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_createdby()
0x2b87e  ldc.i4.0
0x2b87f  ldc.i4.0
0x2b880  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2b885  ldarg.0
0x2b886  ldstr    aCreatedon// "createdon"
0x2b88b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b890  ldarg.3
0x2b891  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_createdon()
0x2b896  ldc.i4.0
0x2b897  ldc.i4.0
0x2b898  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2b89d  ldarg.0
0x2b89e  ldstr    aDescription_0// "description"
0x2b8a3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b8a8  ldarg.3
0x2b8a9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_description()
0x2b8ae  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2b8b3  ldarg.0
0x2b8b4  ldstr    aExchangerate// "exchangerate"
0x2b8b9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b8be  ldarg.3
0x2b8bf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_exchangerate()
0x2b8c4  ldc.i4.0
0x2b8c5  ldc.i4.0
0x2b8c6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x2b8cb  ldarg.0
0x2b8cc  ldstr    aExpectedrespon// "expectedresponse"
0x2b8d1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b8d6  ldarg.3
0x2b8d7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_expectedresponse()
0x2b8dc  ldc.i4.0
0x2b8dd  ldc.i4.0
0x2b8de  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2b8e3  ldarg.0
0x2b8e4  ldstr    aExpectedrevenu// "expectedrevenue"
0x2b8e9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b8ee  ldarg.3
0x2b8ef  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_expectedrevenue()
0x2b8f4  ldc.i4.0
0x2b8f5  ldc.i4.0
0x2b8f6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2b8fb  ldarg.0
0x2b8fc  ldstr    aExpectedrevenu_0// "expectedrevenue_base"
0x2b901  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b906  ldarg.3
0x2b907  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_expectedrevenue_base()
0x2b90c  ldc.i4.0
0x2b90d  ldc.i4.0
0x2b90e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2b913  ldarg.0
0x2b914  ldstr    aImportsequence// "importsequencenumber"
0x2b919  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b91e  ldarg.3
0x2b91f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_importsequencenumber()
0x2b924  ldc.i4.0
0x2b925  ldc.i4.0
0x2b926  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2b92b  ldarg.0
0x2b92c  ldstr    aIstemplate// "istemplate"
0x2b931  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b936  ldarg.3
0x2b937  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_istemplate()
0x2b93c  ldc.i4.0
0x2b93d  ldc.i4.0
0x2b93e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2b943  ldarg.0
0x2b944  ldstr    aMessage// "message"
0x2b949  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b94e  ldarg.3
0x2b94f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_message()
0x2b954  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2b959  ldarg.0
0x2b95a  ldstr    aModifiedby// "modifiedby"
0x2b95f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b964  ldarg.3
0x2b965  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_modifiedby()
0x2b96a  ldc.i4.0
0x2b96b  ldc.i4.0
0x2b96c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2b971  ldarg.0
0x2b972  ldstr    aModifiedon// "modifiedon"
0x2b977  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b97c  ldarg.3
0x2b97d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_modifiedon()
0x2b982  ldc.i4.0
0x2b983  ldc.i4.0
0x2b984  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2b989  ldarg.0
0x2b98a  ldstr    aName// "name"
0x2b98f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b994  ldarg.3
0x2b995  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_name()
0x2b99a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2b99f  ldarg.0
0x2b9a0  ldstr    aObjective// "objective"
0x2b9a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b9aa  ldarg.3
0x2b9ab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_objective()
0x2b9b0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2b9b5  ldarg.0
0x2b9b6  ldstr    aOthercost// "othercost"
0x2b9bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b9c0  ldarg.3
0x2b9c1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_othercost()
0x2b9c6  ldc.i4.0
0x2b9c7  ldc.i4.0
0x2b9c8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2b9cd  ldarg.0
0x2b9ce  ldstr    aOthercostBase// "othercost_base"
0x2b9d3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b9d8  ldarg.3
0x2b9d9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_othercost_base()
0x2b9de  ldc.i4.0
0x2b9df  ldc.i4.0
0x2b9e0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2b9e5  ldarg.0
0x2b9e6  ldstr    aOverriddencrea// "overriddencreatedon"
0x2b9eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b9f0  ldarg.3
0x2b9f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_overriddencreatedon()
0x2b9f6  ldc.i4.0
0x2b9f7  ldc.i4.0
0x2b9f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2b9fd  ldarg.0
0x2b9fe  ldstr    aOwnerid// "ownerid"
0x2ba03  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ba08  ldarg.3
0x2ba09  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_ownerid()
0x2ba0e  ldc.i4.0
0x2ba0f  ldc.i4.0
0x2ba10  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2ba15  ldarg.0
0x2ba16  ldstr    aOwningbusiness// "owningbusinessunit"
0x2ba1b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ba20  ldarg.3
0x2ba21  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_owningbusinessunit()
0x2ba26  ldc.i4.0
0x2ba27  ldc.i4.0
0x2ba28  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2ba2d  ldarg.0
0x2ba2e  ldstr    aPricelistid// "pricelistid"
0x2ba33  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ba38  ldarg.3
0x2ba39  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_pricelistid()
0x2ba3e  ldc.i4.0
0x2ba3f  ldc.i4.0
0x2ba40  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2ba45  ldarg.0
0x2ba46  ldstr    aPromotioncoden// "promotioncodename"
0x2ba4b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ba50  ldarg.3
0x2ba51  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_promotioncodename()
0x2ba56  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ba5b  ldarg.0
0x2ba5c  ldstr    aProposedend// "proposedend"
0x2ba61  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ba66  ldarg.3
0x2ba67  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_proposedend()
0x2ba6c  ldc.i4.0
0x2ba6d  ldc.i4.0
0x2ba6e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2ba73  ldarg.0
0x2ba74  ldstr    aProposedstart// "proposedstart"
0x2ba79  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ba7e  ldarg.3
0x2ba7f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_proposedstart()
0x2ba84  ldc.i4.0
0x2ba85  ldc.i4.0
0x2ba86  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2ba8b  ldarg.0
0x2ba8c  ldstr    aStatecode// "statecode"
0x2ba91  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ba96  ldarg.3
0x2ba97  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CampaignStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_statecode()
0x2ba9c  ldc.i4.0
0x2ba9d  ldc.i4.0
0x2ba9e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write423_CampaignStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CampaignStateInfo o, bool isNullable, bool needType)
0x2baa3  ldarg.0
0x2baa4  ldstr    aStatuscode// "statuscode"
0x2baa9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2baae  ldarg.3
0x2baaf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_statuscode()
0x2bab4  ldc.i4.0
0x2bab5  ldc.i4.0
0x2bab6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x2babb  ldarg.0
0x2babc  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x2bac1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bac6  ldarg.3
0x2bac7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_timezoneruleversionnumber()
0x2bacc  ldc.i4.0
0x2bacd  ldc.i4.0
0x2bace  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2bad3  ldarg.0
0x2bad4  ldstr    aTotalactualcos// "totalactualcost"
0x2bad9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bade  ldarg.3
0x2badf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_totalactualcost()
0x2bae4  ldc.i4.0
0x2bae5  ldc.i4.0
0x2bae6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2baeb  ldarg.0
0x2baec  ldstr    aTotalactualcos_0// "totalactualcost_base"
0x2baf1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2baf6  ldarg.3
0x2baf7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_totalactualcost_base()
0x2bafc  ldc.i4.0
0x2bafd  ldc.i4.0
0x2bafe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2bb03  ldarg.0
0x2bb04  ldstr    aTotalcampaigna// "totalcampaignactivityactualcost"
0x2bb09  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2bb0e  ldarg.3
0x2bb0f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaign::get_totalcampaignactivityactualcost()
  ... truncated ...
```
