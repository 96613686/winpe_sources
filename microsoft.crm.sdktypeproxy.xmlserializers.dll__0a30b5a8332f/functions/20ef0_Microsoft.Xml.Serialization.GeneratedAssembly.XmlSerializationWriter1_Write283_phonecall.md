# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write283_phonecall

- ea: `0x20ef0`
- end: `0x212b4`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write283_phonecall`
- size: `964`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x368a0`
- `0x55cc0`

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
- `0x20ef0`
- `0x212c0`

## string_xrefs

- `0x20f35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20f45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20f5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20f75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20f8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20fa5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20fbb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20fd3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20feb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21001`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21023`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21039`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2105e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21076`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2108e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x210a6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x210be`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x210d6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x210ee`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21106`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2111e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21134`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2114c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21164`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2117c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21194`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x211ac`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x211c4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x211dc`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x211f4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2120a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21220`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21238`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2125a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21271`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2129a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20fb6`: `createdby`
- `0x20fce`: `createdon`
- `0x210d1`: `overriddencreatedon`
- `0x21177`: `scheduledend`
- `0x2118f`: `scheduledstart`
- `0x211a7`: `serviceid`
- `0x21089`: `isworkflowcreated`
- `0x2115f`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x20ef0  ldarg.3
0x20ef1  brtrue.s loc_20F00
0x20ef3  ldarg.s  4
0x20ef5  brfalse.s loc_20EFF
0x20ef7  ldarg.0
0x20ef8  ldarg.1
0x20ef9  ldarg.2
0x20efa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x20eff  ret
0x20f00  ldarg.s  5
0x20f02  brtrue.s loc_20F20
0x20f04  ldarg.3
0x20f05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20f0a  stloc.0
0x20f0b  ldloc.0
0x20f0c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall
0x20f11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20f16  beq.s    loc_20F20
0x20f18  ldarg.0
0x20f19  ldarg.3
0x20f1a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x20f1f  throw
0x20f20  ldarg.0
0x20f21  ldarg.1
0x20f22  ldarg.2
0x20f23  ldarg.3
0x20f24  ldc.i4.0
0x20f25  ldnull
0x20f26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x20f2b  ldarg.s  5
0x20f2d  brfalse.s loc_20F3F
0x20f2f  ldarg.0
0x20f30  ldstr    aPhonecall// "phonecall"
0x20f35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20f3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x20f3f  ldarg.0
0x20f40  ldstr    aActivityid_0// "activityid"
0x20f45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20f4a  ldarg.3
0x20f4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_activityid()
0x20f50  ldc.i4.0
0x20f51  ldc.i4.0
0x20f52  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x20f57  ldarg.0
0x20f58  ldstr    aActualduration// "actualdurationminutes"
0x20f5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20f62  ldarg.3
0x20f63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_actualdurationminutes()
0x20f68  ldc.i4.0
0x20f69  ldc.i4.0
0x20f6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x20f6f  ldarg.0
0x20f70  ldstr    aActualend// "actualend"
0x20f75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20f7a  ldarg.3
0x20f7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_actualend()
0x20f80  ldc.i4.0
0x20f81  ldc.i4.0
0x20f82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x20f87  ldarg.0
0x20f88  ldstr    aActualstart// "actualstart"
0x20f8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20f92  ldarg.3
0x20f93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_actualstart()
0x20f98  ldc.i4.0
0x20f99  ldc.i4.0
0x20f9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x20f9f  ldarg.0
0x20fa0  ldstr    aCategory// "category"
0x20fa5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20faa  ldarg.3
0x20fab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_category()
0x20fb0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20fb5  ldarg.0
0x20fb6  ldstr    aCreatedby// "createdby"
0x20fbb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20fc0  ldarg.3
0x20fc1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_createdby()
0x20fc6  ldc.i4.0
0x20fc7  ldc.i4.0
0x20fc8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20fcd  ldarg.0
0x20fce  ldstr    aCreatedon// "createdon"
0x20fd3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20fd8  ldarg.3
0x20fd9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_createdon()
0x20fde  ldc.i4.0
0x20fdf  ldc.i4.0
0x20fe0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x20fe5  ldarg.0
0x20fe6  ldstr    aDescription_0// "description"
0x20feb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20ff0  ldarg.3
0x20ff1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_description()
0x20ff6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20ffb  ldarg.0
0x20ffc  ldstr    aDirectioncode// "directioncode"
0x21001  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21006  ldarg.3
0x21007  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_directioncode()
0x2100c  ldc.i4.0
0x2100d  ldc.i4.0
0x2100e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x21013  ldarg.3
0x21014  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_from()
0x21019  stloc.1
0x2101a  ldloc.1
0x2101b  brfalse.s loc_21058
0x2101d  ldarg.0
0x2101e  ldstr    aFrom_0// "from"
0x21023  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21028  ldnull
0x21029  ldc.i4.0
0x2102a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x2102f  ldc.i4.0
0x21030  stloc.2
0x21031  br.s     loc_2104C
0x21033  ldarg.0
0x21034  ldstr    aActivityparty// "activityparty"
0x21039  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2103e  ldloc.1
0x2103f  ldloc.2
0x21040  ldelem.ref
0x21041  ldc.i4.0
0x21042  ldc.i4.0
0x21043  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x21048  ldloc.2
0x21049  ldc.i4.1
0x2104a  add
0x2104b  stloc.2
0x2104c  ldloc.2
0x2104d  ldloc.1
0x2104e  ldlen
0x2104f  conv.i4
0x21050  blt.s    loc_21033
0x21052  ldarg.0
0x21053  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x21058  ldarg.0
0x21059  ldstr    aImportsequence// "importsequencenumber"
0x2105e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21063  ldarg.3
0x21064  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_importsequencenumber()
0x21069  ldc.i4.0
0x2106a  ldc.i4.0
0x2106b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x21070  ldarg.0
0x21071  ldstr    aIsbilled// "isbilled"
0x21076  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2107b  ldarg.3
0x2107c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_isbilled()
0x21081  ldc.i4.0
0x21082  ldc.i4.0
0x21083  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x21088  ldarg.0
0x21089  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x2108e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21093  ldarg.3
0x21094  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_isworkflowcreated()
0x21099  ldc.i4.0
0x2109a  ldc.i4.0
0x2109b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x210a0  ldarg.0
0x210a1  ldstr    aModifiedby// "modifiedby"
0x210a6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x210ab  ldarg.3
0x210ac  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_modifiedby()
0x210b1  ldc.i4.0
0x210b2  ldc.i4.0
0x210b3  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x210b8  ldarg.0
0x210b9  ldstr    aModifiedon// "modifiedon"
0x210be  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x210c3  ldarg.3
0x210c4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_modifiedon()
0x210c9  ldc.i4.0
0x210ca  ldc.i4.0
0x210cb  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x210d0  ldarg.0
0x210d1  ldstr    aOverriddencrea// "overriddencreatedon"
0x210d6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x210db  ldarg.3
0x210dc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_overriddencreatedon()
0x210e1  ldc.i4.0
0x210e2  ldc.i4.0
0x210e3  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x210e8  ldarg.0
0x210e9  ldstr    aOwnerid// "ownerid"
0x210ee  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x210f3  ldarg.3
0x210f4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_ownerid()
0x210f9  ldc.i4.0
0x210fa  ldc.i4.0
0x210fb  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x21100  ldarg.0
0x21101  ldstr    aOwningbusiness// "owningbusinessunit"
0x21106  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2110b  ldarg.3
0x2110c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_owningbusinessunit()
0x21111  ldc.i4.0
0x21112  ldc.i4.0
0x21113  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x21118  ldarg.0
0x21119  ldstr    aPhonenumber// "phonenumber"
0x2111e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21123  ldarg.3
0x21124  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_phonenumber()
0x21129  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2112e  ldarg.0
0x2112f  ldstr    aPrioritycode// "prioritycode"
0x21134  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21139  ldarg.3
0x2113a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_prioritycode()
0x2113f  ldc.i4.0
0x21140  ldc.i4.0
0x21141  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x21146  ldarg.0
0x21147  ldstr    aRegardingobjec// "regardingobjectid"
0x2114c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21151  ldarg.3
0x21152  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_regardingobjectid()
0x21157  ldc.i4.0
0x21158  ldc.i4.0
0x21159  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2115e  ldarg.0
0x2115f  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x21164  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21169  ldarg.3
0x2116a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_scheduleddurationminutes()
0x2116f  ldc.i4.0
0x21170  ldc.i4.0
0x21171  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x21176  ldarg.0
0x21177  ldstr    aScheduledend// "scheduledend"
0x2117c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21181  ldarg.3
0x21182  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_scheduledend()
0x21187  ldc.i4.0
0x21188  ldc.i4.0
0x21189  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2118e  ldarg.0
0x2118f  ldstr    aScheduledstart// "scheduledstart"
0x21194  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21199  ldarg.3
0x2119a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_scheduledstart()
0x2119f  ldc.i4.0
0x211a0  ldc.i4.0
0x211a1  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x211a6  ldarg.0
0x211a7  ldstr    aServiceid// "serviceid"
0x211ac  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x211b1  ldarg.3
0x211b2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_serviceid()
0x211b7  ldc.i4.0
0x211b8  ldc.i4.0
0x211b9  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x211be  ldarg.0
0x211bf  ldstr    aStatecode// "statecode"
0x211c4  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x211c9  ldarg.3
0x211ca  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PhoneCallStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_statecode()
0x211cf  ldc.i4.0
0x211d0  ldc.i4.0
0x211d1  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write282_PhoneCallStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PhoneCallStateInfo o, bool isNullable, bool needType)
0x211d6  ldarg.0
0x211d7  ldstr    aStatuscode// "statuscode"
0x211dc  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x211e1  ldarg.3
0x211e2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_statuscode()
0x211e7  ldc.i4.0
0x211e8  ldc.i4.0
0x211e9  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x211ee  ldarg.0
0x211ef  ldstr    aSubcategory// "subcategory"
0x211f4  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x211f9  ldarg.3
0x211fa  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_subcategory()
0x211ff  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x21204  ldarg.0
0x21205  ldstr    aSubject// "subject"
0x2120a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2120f  ldarg.3
0x21210  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_subject()
0x21215  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2121a  ldarg.0
0x2121b  ldstr    aSubscriptionid// "subscriptionid"
0x21220  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21225  ldarg.3
0x21226  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_subscriptionid()
0x2122b  ldc.i4.0
0x2122c  ldc.i4.0
0x2122d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x21232  ldarg.0
0x21233  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x21238  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2123d  ldarg.3
0x2123e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::get_timezoneruleversionnumber()
0x21243  ldc.i4.0
0x21244  ldc.i4.0
0x21245  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2124a  ldarg.3
  ... truncated ...
```
