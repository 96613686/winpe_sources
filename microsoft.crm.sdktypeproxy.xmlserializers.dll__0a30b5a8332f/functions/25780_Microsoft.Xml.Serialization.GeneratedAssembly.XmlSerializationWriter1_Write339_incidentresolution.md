# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write339_incidentresolution

- ea: `0x25780`
- end: `0x25a6f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write339_incidentresolution`
- size: `751`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37080`
- `0x56510`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x25780`
- `0x25a70`

## string_xrefs

- `0x257c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x257d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x257ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25805`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2581d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25835`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2584b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25863`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2587b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25891`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x258a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x258c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x258d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x258f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25909`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25921`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25939`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25951`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25969`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25981`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25999`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x259b1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x259c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x259e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x259f9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25a0f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25a25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25a3d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25a55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25846`: `createdby`
- `0x2585e`: `createdon`
- `0x2591c`: `overriddencreatedon`
- `0x2597c`: `scheduledend`
- `0x25994`: `scheduledstart`
- `0x259ac`: `serviceid`
- `0x258d4`: `isworkflowcreated`
- `0x25964`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x25780  ldarg.3
0x25781  brtrue.s loc_25790
0x25783  ldarg.s  4
0x25785  brfalse.s loc_2578F
0x25787  ldarg.0
0x25788  ldarg.1
0x25789  ldarg.2
0x2578a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2578f  ret
0x25790  ldarg.s  5
0x25792  brtrue.s loc_257B0
0x25794  ldarg.3
0x25795  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2579a  stloc.0
0x2579b  ldloc.0
0x2579c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution
0x257a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x257a6  beq.s    loc_257B0
0x257a8  ldarg.0
0x257a9  ldarg.3
0x257aa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x257af  throw
0x257b0  ldarg.0
0x257b1  ldarg.1
0x257b2  ldarg.2
0x257b3  ldarg.3
0x257b4  ldc.i4.0
0x257b5  ldnull
0x257b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x257bb  ldarg.s  5
0x257bd  brfalse.s loc_257CF
0x257bf  ldarg.0
0x257c0  ldstr    aIncidentresolu_0// "incidentresolution"
0x257c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x257ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x257cf  ldarg.0
0x257d0  ldstr    aActivityid_0// "activityid"
0x257d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x257da  ldarg.3
0x257db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_activityid()
0x257e0  ldc.i4.0
0x257e1  ldc.i4.0
0x257e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x257e7  ldarg.0
0x257e8  ldstr    aActualduration// "actualdurationminutes"
0x257ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x257f2  ldarg.3
0x257f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_actualdurationminutes()
0x257f8  ldc.i4.0
0x257f9  ldc.i4.0
0x257fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x257ff  ldarg.0
0x25800  ldstr    aActualend// "actualend"
0x25805  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2580a  ldarg.3
0x2580b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_actualend()
0x25810  ldc.i4.0
0x25811  ldc.i4.0
0x25812  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x25817  ldarg.0
0x25818  ldstr    aActualstart// "actualstart"
0x2581d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25822  ldarg.3
0x25823  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_actualstart()
0x25828  ldc.i4.0
0x25829  ldc.i4.0
0x2582a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2582f  ldarg.0
0x25830  ldstr    aCategory// "category"
0x25835  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2583a  ldarg.3
0x2583b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_category()
0x25840  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x25845  ldarg.0
0x25846  ldstr    aCreatedby// "createdby"
0x2584b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25850  ldarg.3
0x25851  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_createdby()
0x25856  ldc.i4.0
0x25857  ldc.i4.0
0x25858  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2585d  ldarg.0
0x2585e  ldstr    aCreatedon// "createdon"
0x25863  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25868  ldarg.3
0x25869  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_createdon()
0x2586e  ldc.i4.0
0x2586f  ldc.i4.0
0x25870  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x25875  ldarg.0
0x25876  ldstr    aDescription_0// "description"
0x2587b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25880  ldarg.3
0x25881  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_description()
0x25886  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2588b  ldarg.0
0x2588c  ldstr    aImportsequence// "importsequencenumber"
0x25891  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25896  ldarg.3
0x25897  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_importsequencenumber()
0x2589c  ldc.i4.0
0x2589d  ldc.i4.0
0x2589e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x258a3  ldarg.0
0x258a4  ldstr    aIncidentid// "incidentid"
0x258a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x258ae  ldarg.3
0x258af  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_incidentid()
0x258b4  ldc.i4.0
0x258b5  ldc.i4.0
0x258b6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x258bb  ldarg.0
0x258bc  ldstr    aIsbilled// "isbilled"
0x258c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x258c6  ldarg.3
0x258c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_isbilled()
0x258cc  ldc.i4.0
0x258cd  ldc.i4.0
0x258ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x258d3  ldarg.0
0x258d4  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x258d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x258de  ldarg.3
0x258df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_isworkflowcreated()
0x258e4  ldc.i4.0
0x258e5  ldc.i4.0
0x258e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x258eb  ldarg.0
0x258ec  ldstr    aModifiedby// "modifiedby"
0x258f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x258f6  ldarg.3
0x258f7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_modifiedby()
0x258fc  ldc.i4.0
0x258fd  ldc.i4.0
0x258fe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25903  ldarg.0
0x25904  ldstr    aModifiedon// "modifiedon"
0x25909  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2590e  ldarg.3
0x2590f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_modifiedon()
0x25914  ldc.i4.0
0x25915  ldc.i4.0
0x25916  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2591b  ldarg.0
0x2591c  ldstr    aOverriddencrea// "overriddencreatedon"
0x25921  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25926  ldarg.3
0x25927  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_overriddencreatedon()
0x2592c  ldc.i4.0
0x2592d  ldc.i4.0
0x2592e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x25933  ldarg.0
0x25934  ldstr    aOwnerid// "ownerid"
0x25939  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2593e  ldarg.3
0x2593f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_ownerid()
0x25944  ldc.i4.0
0x25945  ldc.i4.0
0x25946  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2594b  ldarg.0
0x2594c  ldstr    aOwningbusiness// "owningbusinessunit"
0x25951  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25956  ldarg.3
0x25957  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_owningbusinessunit()
0x2595c  ldc.i4.0
0x2595d  ldc.i4.0
0x2595e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25963  ldarg.0
0x25964  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x25969  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2596e  ldarg.3
0x2596f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_scheduleddurationminutes()
0x25974  ldc.i4.0
0x25975  ldc.i4.0
0x25976  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2597b  ldarg.0
0x2597c  ldstr    aScheduledend// "scheduledend"
0x25981  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25986  ldarg.3
0x25987  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_scheduledend()
0x2598c  ldc.i4.0
0x2598d  ldc.i4.0
0x2598e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x25993  ldarg.0
0x25994  ldstr    aScheduledstart// "scheduledstart"
0x25999  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2599e  ldarg.3
0x2599f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_scheduledstart()
0x259a4  ldc.i4.0
0x259a5  ldc.i4.0
0x259a6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x259ab  ldarg.0
0x259ac  ldstr    aServiceid// "serviceid"
0x259b1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x259b6  ldarg.3
0x259b7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_serviceid()
0x259bc  ldc.i4.0
0x259bd  ldc.i4.0
0x259be  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x259c3  ldarg.0
0x259c4  ldstr    aStatecode// "statecode"
0x259c9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x259ce  ldarg.3
0x259cf  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.IncidentResolutionStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_statecode()
0x259d4  ldc.i4.0
0x259d5  ldc.i4.0
0x259d6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write338_IncidentResolutionStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.IncidentResolutionStateInfo o, bool isNullable, bool needType)
0x259db  ldarg.0
0x259dc  ldstr    aStatuscode// "statuscode"
0x259e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x259e6  ldarg.3
0x259e7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_statuscode()
0x259ec  ldc.i4.0
0x259ed  ldc.i4.0
0x259ee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x259f3  ldarg.0
0x259f4  ldstr    aSubcategory// "subcategory"
0x259f9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x259fe  ldarg.3
0x259ff  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_subcategory()
0x25a04  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x25a09  ldarg.0
0x25a0a  ldstr    aSubject// "subject"
0x25a0f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25a14  ldarg.3
0x25a15  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_subject()
0x25a1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x25a1f  ldarg.0
0x25a20  ldstr    aTimespent// "timespent"
0x25a25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25a2a  ldarg.3
0x25a2b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_timespent()
0x25a30  ldc.i4.0
0x25a31  ldc.i4.0
0x25a32  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x25a37  ldarg.0
0x25a38  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x25a3d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25a42  ldarg.3
0x25a43  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_timezoneruleversionnumber()
0x25a48  ldc.i4.0
0x25a49  ldc.i4.0
0x25a4a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x25a4f  ldarg.0
0x25a50  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x25a55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25a5a  ldarg.3
0x25a5b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incidentresolution::get_utcconversiontimezonecode()
0x25a60  ldc.i4.0
0x25a61  ldc.i4.0
0x25a62  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x25a67  ldarg.0
0x25a68  ldarg.3
0x25a69  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x25a6e  ret
```
