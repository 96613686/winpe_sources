# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write199_task

- ea: `0x1b380`
- end: `0x1b69f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write199_task`
- size: `799`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35a30`
- `0x54de0`

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
- `0x1b380`
- `0x1b6a0`

## string_xrefs

- `0x1b3c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b3d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b3ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b405`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b41d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b435`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b44b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b463`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b47b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b491`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b4a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b4c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b4d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b4f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b509`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b521`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b539`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b551`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b569`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b581`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b599`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b5b1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b5c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b5e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b5f9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b611`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b629`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b63f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b655`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b66d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b685`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1b446`: `createdby`
- `0x1b45e`: `createdon`
- `0x1b504`: `overriddencreatedon`
- `0x1b5ac`: `scheduledend`
- `0x1b5c4`: `scheduledstart`
- `0x1b5dc`: `serviceid`
- `0x1b4bc`: `isworkflowcreated`
- `0x1b54c`: `percentcomplete`
- `0x1b594`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x1b380  ldarg.3
0x1b381  brtrue.s loc_1B390
0x1b383  ldarg.s  4
0x1b385  brfalse.s loc_1B38F
0x1b387  ldarg.0
0x1b388  ldarg.1
0x1b389  ldarg.2
0x1b38a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1b38f  ret
0x1b390  ldarg.s  5
0x1b392  brtrue.s loc_1B3B0
0x1b394  ldarg.3
0x1b395  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1b39a  stloc.0
0x1b39b  ldloc.0
0x1b39c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task
0x1b3a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b3a6  beq.s    loc_1B3B0
0x1b3a8  ldarg.0
0x1b3a9  ldarg.3
0x1b3aa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1b3af  throw
0x1b3b0  ldarg.0
0x1b3b1  ldarg.1
0x1b3b2  ldarg.2
0x1b3b3  ldarg.3
0x1b3b4  ldc.i4.0
0x1b3b5  ldnull
0x1b3b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1b3bb  ldarg.s  5
0x1b3bd  brfalse.s loc_1B3CF
0x1b3bf  ldarg.0
0x1b3c0  ldstr    aTask// "task"
0x1b3c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b3ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1b3cf  ldarg.0
0x1b3d0  ldstr    aActivityid_0// "activityid"
0x1b3d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b3da  ldarg.3
0x1b3db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_activityid()
0x1b3e0  ldc.i4.0
0x1b3e1  ldc.i4.0
0x1b3e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1b3e7  ldarg.0
0x1b3e8  ldstr    aActualduration// "actualdurationminutes"
0x1b3ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b3f2  ldarg.3
0x1b3f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_actualdurationminutes()
0x1b3f8  ldc.i4.0
0x1b3f9  ldc.i4.0
0x1b3fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1b3ff  ldarg.0
0x1b400  ldstr    aActualend// "actualend"
0x1b405  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b40a  ldarg.3
0x1b40b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_actualend()
0x1b410  ldc.i4.0
0x1b411  ldc.i4.0
0x1b412  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b417  ldarg.0
0x1b418  ldstr    aActualstart// "actualstart"
0x1b41d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b422  ldarg.3
0x1b423  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_actualstart()
0x1b428  ldc.i4.0
0x1b429  ldc.i4.0
0x1b42a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b42f  ldarg.0
0x1b430  ldstr    aCategory// "category"
0x1b435  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b43a  ldarg.3
0x1b43b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_category()
0x1b440  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b445  ldarg.0
0x1b446  ldstr    aCreatedby// "createdby"
0x1b44b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b450  ldarg.3
0x1b451  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_createdby()
0x1b456  ldc.i4.0
0x1b457  ldc.i4.0
0x1b458  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1b45d  ldarg.0
0x1b45e  ldstr    aCreatedon// "createdon"
0x1b463  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b468  ldarg.3
0x1b469  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_createdon()
0x1b46e  ldc.i4.0
0x1b46f  ldc.i4.0
0x1b470  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b475  ldarg.0
0x1b476  ldstr    aDescription_0// "description"
0x1b47b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b480  ldarg.3
0x1b481  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_description()
0x1b486  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b48b  ldarg.0
0x1b48c  ldstr    aImportsequence// "importsequencenumber"
0x1b491  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b496  ldarg.3
0x1b497  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_importsequencenumber()
0x1b49c  ldc.i4.0
0x1b49d  ldc.i4.0
0x1b49e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1b4a3  ldarg.0
0x1b4a4  ldstr    aIsbilled// "isbilled"
0x1b4a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b4ae  ldarg.3
0x1b4af  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_isbilled()
0x1b4b4  ldc.i4.0
0x1b4b5  ldc.i4.0
0x1b4b6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1b4bb  ldarg.0
0x1b4bc  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x1b4c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b4c6  ldarg.3
0x1b4c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_isworkflowcreated()
0x1b4cc  ldc.i4.0
0x1b4cd  ldc.i4.0
0x1b4ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1b4d3  ldarg.0
0x1b4d4  ldstr    aModifiedby// "modifiedby"
0x1b4d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b4de  ldarg.3
0x1b4df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_modifiedby()
0x1b4e4  ldc.i4.0
0x1b4e5  ldc.i4.0
0x1b4e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1b4eb  ldarg.0
0x1b4ec  ldstr    aModifiedon// "modifiedon"
0x1b4f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b4f6  ldarg.3
0x1b4f7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_modifiedon()
0x1b4fc  ldc.i4.0
0x1b4fd  ldc.i4.0
0x1b4fe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b503  ldarg.0
0x1b504  ldstr    aOverriddencrea// "overriddencreatedon"
0x1b509  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b50e  ldarg.3
0x1b50f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_overriddencreatedon()
0x1b514  ldc.i4.0
0x1b515  ldc.i4.0
0x1b516  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b51b  ldarg.0
0x1b51c  ldstr    aOwnerid// "ownerid"
0x1b521  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b526  ldarg.3
0x1b527  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_ownerid()
0x1b52c  ldc.i4.0
0x1b52d  ldc.i4.0
0x1b52e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x1b533  ldarg.0
0x1b534  ldstr    aOwningbusiness// "owningbusinessunit"
0x1b539  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b53e  ldarg.3
0x1b53f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_owningbusinessunit()
0x1b544  ldc.i4.0
0x1b545  ldc.i4.0
0x1b546  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1b54b  ldarg.0
0x1b54c  ldstr    aPercentcomplet// "percentcomplete"
0x1b551  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b556  ldarg.3
0x1b557  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_percentcomplete()
0x1b55c  ldc.i4.0
0x1b55d  ldc.i4.0
0x1b55e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1b563  ldarg.0
0x1b564  ldstr    aPrioritycode// "prioritycode"
0x1b569  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b56e  ldarg.3
0x1b56f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_prioritycode()
0x1b574  ldc.i4.0
0x1b575  ldc.i4.0
0x1b576  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1b57b  ldarg.0
0x1b57c  ldstr    aRegardingobjec// "regardingobjectid"
0x1b581  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b586  ldarg.3
0x1b587  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_regardingobjectid()
0x1b58c  ldc.i4.0
0x1b58d  ldc.i4.0
0x1b58e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1b593  ldarg.0
0x1b594  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x1b599  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b59e  ldarg.3
0x1b59f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_scheduleddurationminutes()
0x1b5a4  ldc.i4.0
0x1b5a5  ldc.i4.0
0x1b5a6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1b5ab  ldarg.0
0x1b5ac  ldstr    aScheduledend// "scheduledend"
0x1b5b1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b5b6  ldarg.3
0x1b5b7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_scheduledend()
0x1b5bc  ldc.i4.0
0x1b5bd  ldc.i4.0
0x1b5be  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b5c3  ldarg.0
0x1b5c4  ldstr    aScheduledstart// "scheduledstart"
0x1b5c9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b5ce  ldarg.3
0x1b5cf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_scheduledstart()
0x1b5d4  ldc.i4.0
0x1b5d5  ldc.i4.0
0x1b5d6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1b5db  ldarg.0
0x1b5dc  ldstr    aServiceid// "serviceid"
0x1b5e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b5e6  ldarg.3
0x1b5e7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_serviceid()
0x1b5ec  ldc.i4.0
0x1b5ed  ldc.i4.0
0x1b5ee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1b5f3  ldarg.0
0x1b5f4  ldstr    aStatecode// "statecode"
0x1b5f9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b5fe  ldarg.3
0x1b5ff  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TaskStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_statecode()
0x1b604  ldc.i4.0
0x1b605  ldc.i4.0
0x1b606  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write198_TaskStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TaskStateInfo o, bool isNullable, bool needType)
0x1b60b  ldarg.0
0x1b60c  ldstr    aStatuscode// "statuscode"
0x1b611  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b616  ldarg.3
0x1b617  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_statuscode()
0x1b61c  ldc.i4.0
0x1b61d  ldc.i4.0
0x1b61e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x1b623  ldarg.0
0x1b624  ldstr    aSubcategory// "subcategory"
0x1b629  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b62e  ldarg.3
0x1b62f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_subcategory()
0x1b634  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b639  ldarg.0
0x1b63a  ldstr    aSubject// "subject"
0x1b63f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b644  ldarg.3
0x1b645  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_subject()
0x1b64a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1b64f  ldarg.0
0x1b650  ldstr    aSubscriptionid// "subscriptionid"
0x1b655  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b65a  ldarg.3
0x1b65b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_subscriptionid()
0x1b660  ldc.i4.0
0x1b661  ldc.i4.0
0x1b662  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1b667  ldarg.0
0x1b668  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x1b66d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b672  ldarg.3
0x1b673  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_timezoneruleversionnumber()
0x1b678  ldc.i4.0
0x1b679  ldc.i4.0
0x1b67a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1b67f  ldarg.0
0x1b680  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x1b685  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1b68a  ldarg.3
0x1b68b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.task::get_utcconversiontimezonecode()
0x1b690  ldc.i4.0
0x1b691  ldc.i4.0
0x1b692  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1b697  ldarg.0
0x1b698  ldarg.3
0x1b699  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1b69e  ret
```
