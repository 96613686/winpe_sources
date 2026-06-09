# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write311_list

- ea: `0x23710`
- end: `0x239ff`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write311_list`
- size: `751`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36c90`
- `0x56120`

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
- `0x23710`
- `0x23a00`

## string_xrefs

- `0x23755`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23765`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2377d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23795`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x237ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x237c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x237dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x237f3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2380b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23823`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2383b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23853`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2386b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23883`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23899`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x238b1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x238c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x238e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x238f9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23911`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23929`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23941`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23959`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2396f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23985`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2399d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x239b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x239cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x239e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23790`: `createdby`
- `0x237c0`: `createdon`
- `0x2390c`: `overriddencreatedon`
- `0x237a8`: `createdfromcode`

## pseudocode

```c

```

## disassembly

```asm
0x23710  ldarg.3
0x23711  brtrue.s loc_23720
0x23713  ldarg.s  4
0x23715  brfalse.s loc_2371F
0x23717  ldarg.0
0x23718  ldarg.1
0x23719  ldarg.2
0x2371a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2371f  ret
0x23720  ldarg.s  5
0x23722  brtrue.s loc_23740
0x23724  ldarg.3
0x23725  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2372a  stloc.0
0x2372b  ldloc.0
0x2372c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list
0x23731  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23736  beq.s    loc_23740
0x23738  ldarg.0
0x23739  ldarg.3
0x2373a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2373f  throw
0x23740  ldarg.0
0x23741  ldarg.1
0x23742  ldarg.2
0x23743  ldarg.3
0x23744  ldc.i4.0
0x23745  ldnull
0x23746  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2374b  ldarg.s  5
0x2374d  brfalse.s loc_2375F
0x2374f  ldarg.0
0x23750  ldstr    aList// "list"
0x23755  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2375a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2375f  ldarg.0
0x23760  ldstr    aCost// "cost"
0x23765  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2376a  ldarg.3
0x2376b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_cost()
0x23770  ldc.i4.0
0x23771  ldc.i4.0
0x23772  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x23777  ldarg.0
0x23778  ldstr    aCostBase// "cost_base"
0x2377d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23782  ldarg.3
0x23783  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_cost_base()
0x23788  ldc.i4.0
0x23789  ldc.i4.0
0x2378a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2378f  ldarg.0
0x23790  ldstr    aCreatedby// "createdby"
0x23795  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2379a  ldarg.3
0x2379b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_createdby()
0x237a0  ldc.i4.0
0x237a1  ldc.i4.0
0x237a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x237a7  ldarg.0
0x237a8  ldstr    aCreatedfromcod// "createdfromcode"
0x237ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x237b2  ldarg.3
0x237b3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_createdfromcode()
0x237b8  ldc.i4.0
0x237b9  ldc.i4.0
0x237ba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x237bf  ldarg.0
0x237c0  ldstr    aCreatedon// "createdon"
0x237c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x237ca  ldarg.3
0x237cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_createdon()
0x237d0  ldc.i4.0
0x237d1  ldc.i4.0
0x237d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x237d7  ldarg.0
0x237d8  ldstr    aDescription_0// "description"
0x237dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x237e2  ldarg.3
0x237e3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_description()
0x237e8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x237ed  ldarg.0
0x237ee  ldstr    aDonotsendonopt// "donotsendonoptout"
0x237f3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x237f8  ldarg.3
0x237f9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_donotsendonoptout()
0x237fe  ldc.i4.0
0x237ff  ldc.i4.0
0x23800  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x23805  ldarg.0
0x23806  ldstr    aExchangerate// "exchangerate"
0x2380b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23810  ldarg.3
0x23811  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_exchangerate()
0x23816  ldc.i4.0
0x23817  ldc.i4.0
0x23818  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x2381d  ldarg.0
0x2381e  ldstr    aIgnoreinactive// "ignoreinactivelistmembers"
0x23823  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23828  ldarg.3
0x23829  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_ignoreinactivelistmembers()
0x2382e  ldc.i4.0
0x2382f  ldc.i4.0
0x23830  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x23835  ldarg.0
0x23836  ldstr    aImportsequence// "importsequencenumber"
0x2383b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23840  ldarg.3
0x23841  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_importsequencenumber()
0x23846  ldc.i4.0
0x23847  ldc.i4.0
0x23848  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2384d  ldarg.0
0x2384e  ldstr    aLastusedon// "lastusedon"
0x23853  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23858  ldarg.3
0x23859  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_lastusedon()
0x2385e  ldc.i4.0
0x2385f  ldc.i4.0
0x23860  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x23865  ldarg.0
0x23866  ldstr    aListid// "listid"
0x2386b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23870  ldarg.3
0x23871  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_listid()
0x23876  ldc.i4.0
0x23877  ldc.i4.0
0x23878  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2387d  ldarg.0
0x2387e  ldstr    aListname// "listname"
0x23883  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23888  ldarg.3
0x23889  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_listname()
0x2388e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x23893  ldarg.0
0x23894  ldstr    aLockstatus// "lockstatus"
0x23899  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2389e  ldarg.3
0x2389f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_lockstatus()
0x238a4  ldc.i4.0
0x238a5  ldc.i4.0
0x238a6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x238ab  ldarg.0
0x238ac  ldstr    aMembercount// "membercount"
0x238b1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x238b6  ldarg.3
0x238b7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_membercount()
0x238bc  ldc.i4.0
0x238bd  ldc.i4.0
0x238be  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x238c3  ldarg.0
0x238c4  ldstr    aMembertype// "membertype"
0x238c9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x238ce  ldarg.3
0x238cf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_membertype()
0x238d4  ldc.i4.0
0x238d5  ldc.i4.0
0x238d6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x238db  ldarg.0
0x238dc  ldstr    aModifiedby// "modifiedby"
0x238e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x238e6  ldarg.3
0x238e7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_modifiedby()
0x238ec  ldc.i4.0
0x238ed  ldc.i4.0
0x238ee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x238f3  ldarg.0
0x238f4  ldstr    aModifiedon// "modifiedon"
0x238f9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x238fe  ldarg.3
0x238ff  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_modifiedon()
0x23904  ldc.i4.0
0x23905  ldc.i4.0
0x23906  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2390b  ldarg.0
0x2390c  ldstr    aOverriddencrea// "overriddencreatedon"
0x23911  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23916  ldarg.3
0x23917  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_overriddencreatedon()
0x2391c  ldc.i4.0
0x2391d  ldc.i4.0
0x2391e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x23923  ldarg.0
0x23924  ldstr    aOwnerid// "ownerid"
0x23929  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2392e  ldarg.3
0x2392f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_ownerid()
0x23934  ldc.i4.0
0x23935  ldc.i4.0
0x23936  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2393b  ldarg.0
0x2393c  ldstr    aOwningbusiness// "owningbusinessunit"
0x23941  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23946  ldarg.3
0x23947  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_owningbusinessunit()
0x2394c  ldc.i4.0
0x2394d  ldc.i4.0
0x2394e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x23953  ldarg.0
0x23954  ldstr    aPurpose// "purpose"
0x23959  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2395e  ldarg.3
0x2395f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_purpose()
0x23964  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x23969  ldarg.0
0x2396a  ldstr    aSource// "source"
0x2396f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23974  ldarg.3
0x23975  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_source()
0x2397a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2397f  ldarg.0
0x23980  ldstr    aStatecode// "statecode"
0x23985  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2398a  ldarg.3
0x2398b  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ListStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_statecode()
0x23990  ldc.i4.0
0x23991  ldc.i4.0
0x23992  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write310_ListStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ListStateInfo o, bool isNullable, bool needType)
0x23997  ldarg.0
0x23998  ldstr    aStatuscode// "statuscode"
0x2399d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x239a2  ldarg.3
0x239a3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_statuscode()
0x239a8  ldc.i4.0
0x239a9  ldc.i4.0
0x239aa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x239af  ldarg.0
0x239b0  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x239b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x239ba  ldarg.3
0x239bb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_timezoneruleversionnumber()
0x239c0  ldc.i4.0
0x239c1  ldc.i4.0
0x239c2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x239c7  ldarg.0
0x239c8  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x239cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x239d2  ldarg.3
0x239d3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_transactioncurrencyid()
0x239d8  ldc.i4.0
0x239d9  ldc.i4.0
0x239da  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x239df  ldarg.0
0x239e0  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x239e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x239ea  ldarg.3
0x239eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.list::get_utcconversiontimezonecode()
0x239f0  ldc.i4.0
0x239f1  ldc.i4.0
0x239f2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x239f7  ldarg.0
0x239f8  ldarg.3
0x239f9  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x239fe  ret
```
