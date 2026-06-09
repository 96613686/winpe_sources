# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write257_quoteclose

- ea: `0x1f1a0`
- end: `0x1f4a5`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write257_quoteclose`
- size: `773`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x364b0`
- `0x55860`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x1f1a0`
- `0x1f4b0`

## string_xrefs

- `0x1f1e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f1f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f20d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f225`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f23d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f255`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f26b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f283`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f29b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f2b1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f2c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f2e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f2f9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f311`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f329`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f341`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f359`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f371`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f389`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f39f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f3b7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f3cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f3e7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f3ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f417`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f42f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f447`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f45d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f473`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f48b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f266`: `createdby`
- `0x1f27e`: `createdon`
- `0x1f324`: `overriddencreatedon`
- `0x1f3ca`: `scheduledend`
- `0x1f3e2`: `scheduledstart`
- `0x1f3fa`: `serviceid`
- `0x1f2dc`: `isworkflowcreated`
- `0x1f3b2`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x1f1a0  ldarg.3
0x1f1a1  brtrue.s loc_1F1B0
0x1f1a3  ldarg.s  4
0x1f1a5  brfalse.s loc_1F1AF
0x1f1a7  ldarg.0
0x1f1a8  ldarg.1
0x1f1a9  ldarg.2
0x1f1aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1f1af  ret
0x1f1b0  ldarg.s  5
0x1f1b2  brtrue.s loc_1F1D0
0x1f1b4  ldarg.3
0x1f1b5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1f1ba  stloc.0
0x1f1bb  ldloc.0
0x1f1bc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose
0x1f1c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f1c6  beq.s    loc_1F1D0
0x1f1c8  ldarg.0
0x1f1c9  ldarg.3
0x1f1ca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1f1cf  throw
0x1f1d0  ldarg.0
0x1f1d1  ldarg.1
0x1f1d2  ldarg.2
0x1f1d3  ldarg.3
0x1f1d4  ldc.i4.0
0x1f1d5  ldnull
0x1f1d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1f1db  ldarg.s  5
0x1f1dd  brfalse.s loc_1F1EF
0x1f1df  ldarg.0
0x1f1e0  ldstr    aQuoteclose// "quoteclose"
0x1f1e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f1ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1f1ef  ldarg.0
0x1f1f0  ldstr    aActivityid_0// "activityid"
0x1f1f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f1fa  ldarg.3
0x1f1fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_activityid()
0x1f200  ldc.i4.0
0x1f201  ldc.i4.0
0x1f202  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1f207  ldarg.0
0x1f208  ldstr    aActualduration// "actualdurationminutes"
0x1f20d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f212  ldarg.3
0x1f213  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_actualdurationminutes()
0x1f218  ldc.i4.0
0x1f219  ldc.i4.0
0x1f21a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1f21f  ldarg.0
0x1f220  ldstr    aActualend// "actualend"
0x1f225  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f22a  ldarg.3
0x1f22b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_actualend()
0x1f230  ldc.i4.0
0x1f231  ldc.i4.0
0x1f232  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1f237  ldarg.0
0x1f238  ldstr    aActualstart// "actualstart"
0x1f23d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f242  ldarg.3
0x1f243  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_actualstart()
0x1f248  ldc.i4.0
0x1f249  ldc.i4.0
0x1f24a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1f24f  ldarg.0
0x1f250  ldstr    aCategory// "category"
0x1f255  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f25a  ldarg.3
0x1f25b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_category()
0x1f260  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1f265  ldarg.0
0x1f266  ldstr    aCreatedby// "createdby"
0x1f26b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f270  ldarg.3
0x1f271  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_createdby()
0x1f276  ldc.i4.0
0x1f277  ldc.i4.0
0x1f278  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1f27d  ldarg.0
0x1f27e  ldstr    aCreatedon// "createdon"
0x1f283  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f288  ldarg.3
0x1f289  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_createdon()
0x1f28e  ldc.i4.0
0x1f28f  ldc.i4.0
0x1f290  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1f295  ldarg.0
0x1f296  ldstr    aDescription_0// "description"
0x1f29b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f2a0  ldarg.3
0x1f2a1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_description()
0x1f2a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1f2ab  ldarg.0
0x1f2ac  ldstr    aImportsequence// "importsequencenumber"
0x1f2b1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f2b6  ldarg.3
0x1f2b7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_importsequencenumber()
0x1f2bc  ldc.i4.0
0x1f2bd  ldc.i4.0
0x1f2be  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1f2c3  ldarg.0
0x1f2c4  ldstr    aIsbilled// "isbilled"
0x1f2c9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f2ce  ldarg.3
0x1f2cf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_isbilled()
0x1f2d4  ldc.i4.0
0x1f2d5  ldc.i4.0
0x1f2d6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1f2db  ldarg.0
0x1f2dc  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x1f2e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f2e6  ldarg.3
0x1f2e7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_isworkflowcreated()
0x1f2ec  ldc.i4.0
0x1f2ed  ldc.i4.0
0x1f2ee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1f2f3  ldarg.0
0x1f2f4  ldstr    aModifiedby// "modifiedby"
0x1f2f9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f2fe  ldarg.3
0x1f2ff  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_modifiedby()
0x1f304  ldc.i4.0
0x1f305  ldc.i4.0
0x1f306  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1f30b  ldarg.0
0x1f30c  ldstr    aModifiedon// "modifiedon"
0x1f311  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f316  ldarg.3
0x1f317  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_modifiedon()
0x1f31c  ldc.i4.0
0x1f31d  ldc.i4.0
0x1f31e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1f323  ldarg.0
0x1f324  ldstr    aOverriddencrea// "overriddencreatedon"
0x1f329  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f32e  ldarg.3
0x1f32f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_overriddencreatedon()
0x1f334  ldc.i4.0
0x1f335  ldc.i4.0
0x1f336  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1f33b  ldarg.0
0x1f33c  ldstr    aOwnerid// "ownerid"
0x1f341  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f346  ldarg.3
0x1f347  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_ownerid()
0x1f34c  ldc.i4.0
0x1f34d  ldc.i4.0
0x1f34e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x1f353  ldarg.0
0x1f354  ldstr    aOwningbusiness// "owningbusinessunit"
0x1f359  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f35e  ldarg.3
0x1f35f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_owningbusinessunit()
0x1f364  ldc.i4.0
0x1f365  ldc.i4.0
0x1f366  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1f36b  ldarg.0
0x1f36c  ldstr    aQuoteid// "quoteid"
0x1f371  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f376  ldarg.3
0x1f377  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_quoteid()
0x1f37c  ldc.i4.0
0x1f37d  ldc.i4.0
0x1f37e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1f383  ldarg.0
0x1f384  ldstr    aQuotenumber// "quotenumber"
0x1f389  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f38e  ldarg.3
0x1f38f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_quotenumber()
0x1f394  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1f399  ldarg.0
0x1f39a  ldstr    aRevision// "revision"
0x1f39f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f3a4  ldarg.3
0x1f3a5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_revision()
0x1f3aa  ldc.i4.0
0x1f3ab  ldc.i4.0
0x1f3ac  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1f3b1  ldarg.0
0x1f3b2  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x1f3b7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f3bc  ldarg.3
0x1f3bd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_scheduleddurationminutes()
0x1f3c2  ldc.i4.0
0x1f3c3  ldc.i4.0
0x1f3c4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1f3c9  ldarg.0
0x1f3ca  ldstr    aScheduledend// "scheduledend"
0x1f3cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f3d4  ldarg.3
0x1f3d5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_scheduledend()
0x1f3da  ldc.i4.0
0x1f3db  ldc.i4.0
0x1f3dc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1f3e1  ldarg.0
0x1f3e2  ldstr    aScheduledstart// "scheduledstart"
0x1f3e7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f3ec  ldarg.3
0x1f3ed  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_scheduledstart()
0x1f3f2  ldc.i4.0
0x1f3f3  ldc.i4.0
0x1f3f4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1f3f9  ldarg.0
0x1f3fa  ldstr    aServiceid// "serviceid"
0x1f3ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f404  ldarg.3
0x1f405  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_serviceid()
0x1f40a  ldc.i4.0
0x1f40b  ldc.i4.0
0x1f40c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1f411  ldarg.0
0x1f412  ldstr    aStatecode// "statecode"
0x1f417  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f41c  ldarg.3
0x1f41d  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QuoteCloseStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_statecode()
0x1f422  ldc.i4.0
0x1f423  ldc.i4.0
0x1f424  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write256_QuoteCloseStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QuoteCloseStateInfo o, bool isNullable, bool needType)
0x1f429  ldarg.0
0x1f42a  ldstr    aStatuscode// "statuscode"
0x1f42f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f434  ldarg.3
0x1f435  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_statuscode()
0x1f43a  ldc.i4.0
0x1f43b  ldc.i4.0
0x1f43c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x1f441  ldarg.0
0x1f442  ldstr    aSubcategory// "subcategory"
0x1f447  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f44c  ldarg.3
0x1f44d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_subcategory()
0x1f452  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1f457  ldarg.0
0x1f458  ldstr    aSubject// "subject"
0x1f45d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f462  ldarg.3
0x1f463  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_subject()
0x1f468  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1f46d  ldarg.0
0x1f46e  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x1f473  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f478  ldarg.3
0x1f479  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_timezoneruleversionnumber()
0x1f47e  ldc.i4.0
0x1f47f  ldc.i4.0
0x1f480  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1f485  ldarg.0
0x1f486  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x1f48b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f490  ldarg.3
0x1f491  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.quoteclose::get_utcconversiontimezonecode()
0x1f496  ldc.i4.0
0x1f497  ldc.i4.0
0x1f498  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1f49d  ldarg.0
0x1f49e  ldarg.3
0x1f49f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1f4a4  ret
```
