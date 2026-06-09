# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write440_appointment

- ea: `0x2caf0`
- end: `0x2cf30`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write440_appointment`
- size: `1088`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37ef0`
- `0x48120`
- `0x57460`

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
- `0x2caf0`
- `0x2cf30`

## string_xrefs

- `0x2cb35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cb45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cb5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cb75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cb8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cba5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cbbb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cbd3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cbeb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cc01`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cc17`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cc2f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cc47`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cc5f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cc77`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cc8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cca5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ccc7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ccdd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cd0c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cd23`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cd4c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cd64`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cd7c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cd94`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cdac`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cdc4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cde8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cdff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ce2a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ce42`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ce5a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ce72`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ce8a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cea2`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ceba`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ced0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cee6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cefe`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cf16`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2cbb6`: `createdby`
- `0x2cbce`: `createdon`
- `0x2cd5f`: `overriddencreatedon`
- `0x2ce3d`: `scheduledend`
- `0x2ce55`: `scheduledstart`
- `0x2ce6d`: `serviceid`
- `0x2cc5a`: `isworkflowcreated`
- `0x2ce25`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x2caf0  ldarg.3
0x2caf1  brtrue.s loc_2CB00
0x2caf3  ldarg.s  4
0x2caf5  brfalse.s loc_2CAFF
0x2caf7  ldarg.0
0x2caf8  ldarg.1
0x2caf9  ldarg.2
0x2cafa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2caff  ret
0x2cb00  ldarg.s  5
0x2cb02  brtrue.s loc_2CB20
0x2cb04  ldarg.3
0x2cb05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2cb0a  stloc.0
0x2cb0b  ldloc.0
0x2cb0c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment
0x2cb11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cb16  beq.s    loc_2CB20
0x2cb18  ldarg.0
0x2cb19  ldarg.3
0x2cb1a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2cb1f  throw
0x2cb20  ldarg.0
0x2cb21  ldarg.1
0x2cb22  ldarg.2
0x2cb23  ldarg.3
0x2cb24  ldc.i4.0
0x2cb25  ldnull
0x2cb26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2cb2b  ldarg.s  5
0x2cb2d  brfalse.s loc_2CB3F
0x2cb2f  ldarg.0
0x2cb30  ldstr    aAppointment_0// "appointment"
0x2cb35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cb3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2cb3f  ldarg.0
0x2cb40  ldstr    aActivityid_0// "activityid"
0x2cb45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cb4a  ldarg.3
0x2cb4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_activityid()
0x2cb50  ldc.i4.0
0x2cb51  ldc.i4.0
0x2cb52  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2cb57  ldarg.0
0x2cb58  ldstr    aActualduration// "actualdurationminutes"
0x2cb5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cb62  ldarg.3
0x2cb63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_actualdurationminutes()
0x2cb68  ldc.i4.0
0x2cb69  ldc.i4.0
0x2cb6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2cb6f  ldarg.0
0x2cb70  ldstr    aActualend// "actualend"
0x2cb75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cb7a  ldarg.3
0x2cb7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_actualend()
0x2cb80  ldc.i4.0
0x2cb81  ldc.i4.0
0x2cb82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2cb87  ldarg.0
0x2cb88  ldstr    aActualstart// "actualstart"
0x2cb8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cb92  ldarg.3
0x2cb93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_actualstart()
0x2cb98  ldc.i4.0
0x2cb99  ldc.i4.0
0x2cb9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2cb9f  ldarg.0
0x2cba0  ldstr    aCategory// "category"
0x2cba5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cbaa  ldarg.3
0x2cbab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_category()
0x2cbb0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2cbb5  ldarg.0
0x2cbb6  ldstr    aCreatedby// "createdby"
0x2cbbb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cbc0  ldarg.3
0x2cbc1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_createdby()
0x2cbc6  ldc.i4.0
0x2cbc7  ldc.i4.0
0x2cbc8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2cbcd  ldarg.0
0x2cbce  ldstr    aCreatedon// "createdon"
0x2cbd3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cbd8  ldarg.3
0x2cbd9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_createdon()
0x2cbde  ldc.i4.0
0x2cbdf  ldc.i4.0
0x2cbe0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2cbe5  ldarg.0
0x2cbe6  ldstr    aDescription_0// "description"
0x2cbeb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cbf0  ldarg.3
0x2cbf1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_description()
0x2cbf6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2cbfb  ldarg.0
0x2cbfc  ldstr    aGlobalobjectid// "globalobjectid"
0x2cc01  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cc06  ldarg.3
0x2cc07  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_globalobjectid()
0x2cc0c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2cc11  ldarg.0
0x2cc12  ldstr    aImportsequence// "importsequencenumber"
0x2cc17  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cc1c  ldarg.3
0x2cc1d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_importsequencenumber()
0x2cc22  ldc.i4.0
0x2cc23  ldc.i4.0
0x2cc24  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2cc29  ldarg.0
0x2cc2a  ldstr    aIsalldayevent// "isalldayevent"
0x2cc2f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cc34  ldarg.3
0x2cc35  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_isalldayevent()
0x2cc3a  ldc.i4.0
0x2cc3b  ldc.i4.0
0x2cc3c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2cc41  ldarg.0
0x2cc42  ldstr    aIsbilled// "isbilled"
0x2cc47  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cc4c  ldarg.3
0x2cc4d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_isbilled()
0x2cc52  ldc.i4.0
0x2cc53  ldc.i4.0
0x2cc54  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2cc59  ldarg.0
0x2cc5a  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x2cc5f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cc64  ldarg.3
0x2cc65  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_isworkflowcreated()
0x2cc6a  ldc.i4.0
0x2cc6b  ldc.i4.0
0x2cc6c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2cc71  ldarg.0
0x2cc72  ldstr    aLocation// "location"
0x2cc77  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cc7c  ldarg.3
0x2cc7d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_location()
0x2cc82  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2cc87  ldarg.0
0x2cc88  ldstr    aModifiedby// "modifiedby"
0x2cc8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cc92  ldarg.3
0x2cc93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_modifiedby()
0x2cc98  ldc.i4.0
0x2cc99  ldc.i4.0
0x2cc9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2cc9f  ldarg.0
0x2cca0  ldstr    aModifiedon// "modifiedon"
0x2cca5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ccaa  ldarg.3
0x2ccab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_modifiedon()
0x2ccb0  ldc.i4.0
0x2ccb1  ldc.i4.0
0x2ccb2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2ccb7  ldarg.3
0x2ccb8  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_optionalattendees()
0x2ccbd  stloc.1
0x2ccbe  ldloc.1
0x2ccbf  brfalse.s loc_2CCFC
0x2ccc1  ldarg.0
0x2ccc2  ldstr    aOptionalattend// "optionalattendees"
0x2ccc7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cccc  ldnull
0x2cccd  ldc.i4.0
0x2ccce  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x2ccd3  ldc.i4.0
0x2ccd4  stloc.2
0x2ccd5  br.s     loc_2CCF0
0x2ccd7  ldarg.0
0x2ccd8  ldstr    aActivityparty// "activityparty"
0x2ccdd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cce2  ldloc.1
0x2cce3  ldloc.2
0x2cce4  ldelem.ref
0x2cce5  ldc.i4.0
0x2cce6  ldc.i4.0
0x2cce7  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x2ccec  ldloc.2
0x2cced  ldc.i4.1
0x2ccee  add
0x2ccef  stloc.2
0x2ccf0  ldloc.2
0x2ccf1  ldloc.1
0x2ccf2  ldlen
0x2ccf3  conv.i4
0x2ccf4  blt.s    loc_2CCD7
0x2ccf6  ldarg.0
0x2ccf7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x2ccfc  ldarg.3
0x2ccfd  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_organizer()
0x2cd02  stloc.3
0x2cd03  ldloc.3
0x2cd04  brfalse.s loc_2CD46
0x2cd06  ldarg.0
0x2cd07  ldstr    aOrganizer// "organizer"
0x2cd0c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cd11  ldnull
0x2cd12  ldc.i4.0
0x2cd13  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x2cd18  ldc.i4.0
0x2cd19  stloc.s  4
0x2cd1b  br.s     loc_2CD39
0x2cd1d  ldarg.0
0x2cd1e  ldstr    aActivityparty// "activityparty"
0x2cd23  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cd28  ldloc.3
0x2cd29  ldloc.s  4
0x2cd2b  ldelem.ref
0x2cd2c  ldc.i4.0
0x2cd2d  ldc.i4.0
0x2cd2e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x2cd33  ldloc.s  4
0x2cd35  ldc.i4.1
0x2cd36  add
0x2cd37  stloc.s  4
0x2cd39  ldloc.s  4
0x2cd3b  ldloc.3
0x2cd3c  ldlen
0x2cd3d  conv.i4
0x2cd3e  blt.s    loc_2CD1D
0x2cd40  ldarg.0
0x2cd41  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x2cd46  ldarg.0
0x2cd47  ldstr    aOutlookownerap// "outlookownerapptid"
0x2cd4c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cd51  ldarg.3
0x2cd52  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_outlookownerapptid()
0x2cd57  ldc.i4.0
0x2cd58  ldc.i4.0
0x2cd59  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2cd5e  ldarg.0
0x2cd5f  ldstr    aOverriddencrea// "overriddencreatedon"
0x2cd64  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cd69  ldarg.3
0x2cd6a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_overriddencreatedon()
0x2cd6f  ldc.i4.0
0x2cd70  ldc.i4.0
0x2cd71  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2cd76  ldarg.0
0x2cd77  ldstr    aOwnerid// "ownerid"
0x2cd7c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cd81  ldarg.3
0x2cd82  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_ownerid()
0x2cd87  ldc.i4.0
0x2cd88  ldc.i4.0
0x2cd89  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2cd8e  ldarg.0
0x2cd8f  ldstr    aOwningbusiness// "owningbusinessunit"
0x2cd94  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cd99  ldarg.3
0x2cd9a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_owningbusinessunit()
0x2cd9f  ldc.i4.0
0x2cda0  ldc.i4.0
0x2cda1  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2cda6  ldarg.0
0x2cda7  ldstr    aPrioritycode// "prioritycode"
0x2cdac  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cdb1  ldarg.3
0x2cdb2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_prioritycode()
0x2cdb7  ldc.i4.0
0x2cdb8  ldc.i4.0
0x2cdb9  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2cdbe  ldarg.0
0x2cdbf  ldstr    aRegardingobjec// "regardingobjectid"
0x2cdc4  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cdc9  ldarg.3
0x2cdca  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_regardingobjectid()
0x2cdcf  ldc.i4.0
0x2cdd0  ldc.i4.0
0x2cdd1  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2cdd6  ldarg.3
0x2cdd7  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::get_requiredattendees()
0x2cddc  stloc.s  5
0x2cdde  ldloc.s  5
0x2cde0  brfalse.s loc_2CE24
0x2cde2  ldarg.0
0x2cde3  ldstr    aRequiredattend// "requiredattendees"
0x2cde8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cded  ldnull
0x2cdee  ldc.i4.0
0x2cdef  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x2cdf4  ldc.i4.0
0x2cdf5  stloc.s  6
0x2cdf7  br.s     loc_2CE16
0x2cdf9  ldarg.0
0x2cdfa  ldstr    aActivityparty// "activityparty"
0x2cdff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ce04  ldloc.s  5
0x2ce06  ldloc.s  6
0x2ce08  ldelem.ref
0x2ce09  ldc.i4.0
0x2ce0a  ldc.i4.0
0x2ce0b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x2ce10  ldloc.s  6
0x2ce12  ldc.i4.1
0x2ce13  add
0x2ce14  stloc.s  6
0x2ce16  ldloc.s  6
0x2ce18  ldloc.s  5
  ... truncated ...
```
