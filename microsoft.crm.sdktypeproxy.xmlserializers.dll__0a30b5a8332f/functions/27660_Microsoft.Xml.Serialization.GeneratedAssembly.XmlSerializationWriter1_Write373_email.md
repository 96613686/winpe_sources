# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write373_email

- ea: `0x27660`
- end: `0x27ba6`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write373_email`
- size: `1350`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x374e0`
- `0x3ca30`
- `0x56970`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x19770`
- `0x27660`
- `0x27bb0`

## string_xrefs

- `0x276a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x276b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x276cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x276e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x276fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2771f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27735`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2775a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2777a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27791`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x277ba`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x277d2`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x277ea`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27802`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2781a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27832`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27848`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2786c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27883`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x278ae`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x278c6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x278de`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x278f6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2790c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27924`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2793a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27952`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2796a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27982`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2799a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x279b2`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x279ca`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x279e2`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x279fa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27a12`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27a2a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27a42`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27a5a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27a70`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27a88`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27aa0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27ab8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27ace`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27ae4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27afa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27b1e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27b35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27b60`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27b76`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27b8c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x277cd`: `createdby`
- `0x277e5`: `createdon`
- `0x2797d`: `overriddencreatedon`
- `0x27a25`: `scheduledend`
- `0x27a3d`: `scheduledstart`
- `0x27a6b`: `serviceid`
- `0x278d9`: `isworkflowcreated`
- `0x27a0d`: `scheduleddurationminutes`
- `0x277b5`: `compressed`
- `0x277fd`: `deliveryattempts`
- `0x279dd`: `readreceiptrequested`
- `0x27b71`: `trackingtoken`

## pseudocode

```c

```

## disassembly

```asm
0x27660  ldarg.3
0x27661  brtrue.s loc_27670
0x27663  ldarg.s  4
0x27665  brfalse.s loc_2766F
0x27667  ldarg.0
0x27668  ldarg.1
0x27669  ldarg.2
0x2766a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2766f  ret
0x27670  ldarg.s  5
0x27672  brtrue.s loc_27690
0x27674  ldarg.3
0x27675  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2767a  stloc.0
0x2767b  ldloc.0
0x2767c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email
0x27681  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27686  beq.s    loc_27690
0x27688  ldarg.0
0x27689  ldarg.3
0x2768a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2768f  throw
0x27690  ldarg.0
0x27691  ldarg.1
0x27692  ldarg.2
0x27693  ldarg.3
0x27694  ldc.i4.0
0x27695  ldnull
0x27696  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2769b  ldarg.s  5
0x2769d  brfalse.s loc_276AF
0x2769f  ldarg.0
0x276a0  ldstr    aEmail_0// "email"
0x276a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x276aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x276af  ldarg.0
0x276b0  ldstr    aActivityid_0// "activityid"
0x276b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x276ba  ldarg.3
0x276bb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_activityid()
0x276c0  ldc.i4.0
0x276c1  ldc.i4.0
0x276c2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x276c7  ldarg.0
0x276c8  ldstr    aActualduration// "actualdurationminutes"
0x276cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x276d2  ldarg.3
0x276d3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_actualdurationminutes()
0x276d8  ldc.i4.0
0x276d9  ldc.i4.0
0x276da  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x276df  ldarg.0
0x276e0  ldstr    aActualend// "actualend"
0x276e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x276ea  ldarg.3
0x276eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_actualend()
0x276f0  ldc.i4.0
0x276f1  ldc.i4.0
0x276f2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x276f7  ldarg.0
0x276f8  ldstr    aActualstart// "actualstart"
0x276fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27702  ldarg.3
0x27703  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_actualstart()
0x27708  ldc.i4.0
0x27709  ldc.i4.0
0x2770a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2770f  ldarg.3
0x27710  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_bcc()
0x27715  stloc.1
0x27716  ldloc.1
0x27717  brfalse.s loc_27754
0x27719  ldarg.0
0x2771a  ldstr    aBcc// "bcc"
0x2771f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27724  ldnull
0x27725  ldc.i4.0
0x27726  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x2772b  ldc.i4.0
0x2772c  stloc.2
0x2772d  br.s     loc_27748
0x2772f  ldarg.0
0x27730  ldstr    aActivityparty// "activityparty"
0x27735  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2773a  ldloc.1
0x2773b  ldloc.2
0x2773c  ldelem.ref
0x2773d  ldc.i4.0
0x2773e  ldc.i4.0
0x2773f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x27744  ldloc.2
0x27745  ldc.i4.1
0x27746  add
0x27747  stloc.2
0x27748  ldloc.2
0x27749  ldloc.1
0x2774a  ldlen
0x2774b  conv.i4
0x2774c  blt.s    loc_2772F
0x2774e  ldarg.0
0x2774f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x27754  ldarg.0
0x27755  ldstr    aCategory// "category"
0x2775a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2775f  ldarg.3
0x27760  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_category()
0x27765  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2776a  ldarg.3
0x2776b  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_cc()
0x27770  stloc.3
0x27771  ldloc.3
0x27772  brfalse.s loc_277B4
0x27774  ldarg.0
0x27775  ldstr    aCc// "cc"
0x2777a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2777f  ldnull
0x27780  ldc.i4.0
0x27781  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x27786  ldc.i4.0
0x27787  stloc.s  4
0x27789  br.s     loc_277A7
0x2778b  ldarg.0
0x2778c  ldstr    aActivityparty// "activityparty"
0x27791  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27796  ldloc.3
0x27797  ldloc.s  4
0x27799  ldelem.ref
0x2779a  ldc.i4.0
0x2779b  ldc.i4.0
0x2779c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x277a1  ldloc.s  4
0x277a3  ldc.i4.1
0x277a4  add
0x277a5  stloc.s  4
0x277a7  ldloc.s  4
0x277a9  ldloc.3
0x277aa  ldlen
0x277ab  conv.i4
0x277ac  blt.s    loc_2778B
0x277ae  ldarg.0
0x277af  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x277b4  ldarg.0
0x277b5  ldstr    aCompressed// "compressed"
0x277ba  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x277bf  ldarg.3
0x277c0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_compressed()
0x277c5  ldc.i4.0
0x277c6  ldc.i4.0
0x277c7  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x277cc  ldarg.0
0x277cd  ldstr    aCreatedby// "createdby"
0x277d2  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x277d7  ldarg.3
0x277d8  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_createdby()
0x277dd  ldc.i4.0
0x277de  ldc.i4.0
0x277df  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x277e4  ldarg.0
0x277e5  ldstr    aCreatedon// "createdon"
0x277ea  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x277ef  ldarg.3
0x277f0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_createdon()
0x277f5  ldc.i4.0
0x277f6  ldc.i4.0
0x277f7  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x277fc  ldarg.0
0x277fd  ldstr    aDeliveryattemp// "deliveryattempts"
0x27802  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27807  ldarg.3
0x27808  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_deliveryattempts()
0x2780d  ldc.i4.0
0x2780e  ldc.i4.0
0x2780f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x27814  ldarg.0
0x27815  ldstr    aDeliveryreceip// "deliveryreceiptrequested"
0x2781a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2781f  ldarg.3
0x27820  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_deliveryreceiptrequested()
0x27825  ldc.i4.0
0x27826  ldc.i4.0
0x27827  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2782c  ldarg.0
0x2782d  ldstr    aDescription_0// "description"
0x27832  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27837  ldarg.3
0x27838  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_description()
0x2783d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27842  ldarg.0
0x27843  ldstr    aDirectioncode// "directioncode"
0x27848  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2784d  ldarg.3
0x2784e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_directioncode()
0x27853  ldc.i4.0
0x27854  ldc.i4.0
0x27855  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2785a  ldarg.3
0x2785b  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_from()
0x27860  stloc.s  5
0x27862  ldloc.s  5
0x27864  brfalse.s loc_278A8
0x27866  ldarg.0
0x27867  ldstr    aFrom_0// "from"
0x2786c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27871  ldnull
0x27872  ldc.i4.0
0x27873  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x27878  ldc.i4.0
0x27879  stloc.s  6
0x2787b  br.s     loc_2789A
0x2787d  ldarg.0
0x2787e  ldstr    aActivityparty// "activityparty"
0x27883  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27888  ldloc.s  5
0x2788a  ldloc.s  6
0x2788c  ldelem.ref
0x2788d  ldc.i4.0
0x2788e  ldc.i4.0
0x2788f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x27894  ldloc.s  6
0x27896  ldc.i4.1
0x27897  add
0x27898  stloc.s  6
0x2789a  ldloc.s  6
0x2789c  ldloc.s  5
0x2789e  ldlen
0x2789f  conv.i4
0x278a0  blt.s    loc_2787D
0x278a2  ldarg.0
0x278a3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x278a8  ldarg.0
0x278a9  ldstr    aImportsequence// "importsequencenumber"
0x278ae  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x278b3  ldarg.3
0x278b4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_importsequencenumber()
0x278b9  ldc.i4.0
0x278ba  ldc.i4.0
0x278bb  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x278c0  ldarg.0
0x278c1  ldstr    aIsbilled// "isbilled"
0x278c6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x278cb  ldarg.3
0x278cc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_isbilled()
0x278d1  ldc.i4.0
0x278d2  ldc.i4.0
0x278d3  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x278d8  ldarg.0
0x278d9  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x278de  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x278e3  ldarg.3
0x278e4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_isworkflowcreated()
0x278e9  ldc.i4.0
0x278ea  ldc.i4.0
0x278eb  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x278f0  ldarg.0
0x278f1  ldstr    aMessageid// "messageid"
0x278f6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x278fb  ldarg.3
0x278fc  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_messageid()
0x27901  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27906  ldarg.0
0x27907  ldstr    aMessageiddupch// "messageiddupcheck"
0x2790c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27911  ldarg.3
0x27912  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_messageiddupcheck()
0x27917  ldc.i4.0
0x27918  ldc.i4.0
0x27919  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x2791e  ldarg.0
0x2791f  ldstr    aMimetype// "mimetype"
0x27924  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27929  ldarg.3
0x2792a  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_mimetype()
0x2792f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27934  ldarg.0
0x27935  ldstr    aModifiedby// "modifiedby"
0x2793a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2793f  ldarg.3
0x27940  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_modifiedby()
0x27945  ldc.i4.0
0x27946  ldc.i4.0
0x27947  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2794c  ldarg.0
0x2794d  ldstr    aModifiedon// "modifiedon"
0x27952  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27957  ldarg.3
0x27958  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_modifiedon()
0x2795d  ldc.i4.0
0x2795e  ldc.i4.0
0x2795f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x27964  ldarg.0
0x27965  ldstr    aNotifications// "notifications"
0x2796a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2796f  ldarg.3
0x27970  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::get_notifications()
0x27975  ldc.i4.0
0x27976  ldc.i4.0
0x27977  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2797c  ldarg.0
0x2797d  ldstr    aOverriddencrea// "overriddencreatedon"
0x27982  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
  ... truncated ...
```
