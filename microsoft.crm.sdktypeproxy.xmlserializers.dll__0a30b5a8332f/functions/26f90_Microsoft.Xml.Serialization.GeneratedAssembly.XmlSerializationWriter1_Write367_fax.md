# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write367_fax

- ea: `0x26f90`
- end: `0x273ae`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write367_fax`
- size: `1054`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37400`
- `0x56890`

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
- `0x26f90`
- `0x273b0`

## string_xrefs

- `0x26fd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26fe5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26ffd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27015`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2702d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27045`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2705b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27071`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27087`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2709f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x270b7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x270cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x270e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27105`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2711b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27140`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27158`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27170`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27188`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x271a0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x271b8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x271d0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x271e8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27200`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27218`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27230`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27248`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27260`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27278`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27290`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x272a8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x272c0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x272d8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x272ee`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27304`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2731c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2733e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27355`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2737e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27394`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27082`: `createdby`
- `0x2709a`: `createdon`
- `0x271cb`: `overriddencreatedon`
- `0x2725b`: `scheduledend`
- `0x27273`: `scheduledstart`
- `0x2728b`: `serviceid`
- `0x2716b`: `isworkflowcreated`
- `0x27243`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x26f90  ldarg.3
0x26f91  brtrue.s loc_26FA0
0x26f93  ldarg.s  4
0x26f95  brfalse.s loc_26F9F
0x26f97  ldarg.0
0x26f98  ldarg.1
0x26f99  ldarg.2
0x26f9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x26f9f  ret
0x26fa0  ldarg.s  5
0x26fa2  brtrue.s loc_26FC0
0x26fa4  ldarg.3
0x26fa5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x26faa  stloc.0
0x26fab  ldloc.0
0x26fac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax
0x26fb1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x26fb6  beq.s    loc_26FC0
0x26fb8  ldarg.0
0x26fb9  ldarg.3
0x26fba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x26fbf  throw
0x26fc0  ldarg.0
0x26fc1  ldarg.1
0x26fc2  ldarg.2
0x26fc3  ldarg.3
0x26fc4  ldc.i4.0
0x26fc5  ldnull
0x26fc6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x26fcb  ldarg.s  5
0x26fcd  brfalse.s loc_26FDF
0x26fcf  ldarg.0
0x26fd0  ldstr    aFax// "fax"
0x26fd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26fda  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x26fdf  ldarg.0
0x26fe0  ldstr    aActivityid_0// "activityid"
0x26fe5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26fea  ldarg.3
0x26feb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_activityid()
0x26ff0  ldc.i4.0
0x26ff1  ldc.i4.0
0x26ff2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x26ff7  ldarg.0
0x26ff8  ldstr    aActualduration// "actualdurationminutes"
0x26ffd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27002  ldarg.3
0x27003  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_actualdurationminutes()
0x27008  ldc.i4.0
0x27009  ldc.i4.0
0x2700a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2700f  ldarg.0
0x27010  ldstr    aActualend// "actualend"
0x27015  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2701a  ldarg.3
0x2701b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_actualend()
0x27020  ldc.i4.0
0x27021  ldc.i4.0
0x27022  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x27027  ldarg.0
0x27028  ldstr    aActualstart// "actualstart"
0x2702d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27032  ldarg.3
0x27033  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_actualstart()
0x27038  ldc.i4.0
0x27039  ldc.i4.0
0x2703a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2703f  ldarg.0
0x27040  ldstr    aBillingcode// "billingcode"
0x27045  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2704a  ldarg.3
0x2704b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_billingcode()
0x27050  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27055  ldarg.0
0x27056  ldstr    aCategory// "category"
0x2705b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27060  ldarg.3
0x27061  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_category()
0x27066  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2706b  ldarg.0
0x2706c  ldstr    aCoverpagename// "coverpagename"
0x27071  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27076  ldarg.3
0x27077  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_coverpagename()
0x2707c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27081  ldarg.0
0x27082  ldstr    aCreatedby// "createdby"
0x27087  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2708c  ldarg.3
0x2708d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_createdby()
0x27092  ldc.i4.0
0x27093  ldc.i4.0
0x27094  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x27099  ldarg.0
0x2709a  ldstr    aCreatedon// "createdon"
0x2709f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x270a4  ldarg.3
0x270a5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_createdon()
0x270aa  ldc.i4.0
0x270ab  ldc.i4.0
0x270ac  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x270b1  ldarg.0
0x270b2  ldstr    aDescription_0// "description"
0x270b7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x270bc  ldarg.3
0x270bd  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_description()
0x270c2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x270c7  ldarg.0
0x270c8  ldstr    aDirectioncode// "directioncode"
0x270cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x270d2  ldarg.3
0x270d3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_directioncode()
0x270d8  ldc.i4.0
0x270d9  ldc.i4.0
0x270da  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x270df  ldarg.0
0x270e0  ldstr    aFaxnumber// "faxnumber"
0x270e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x270ea  ldarg.3
0x270eb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_faxnumber()
0x270f0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x270f5  ldarg.3
0x270f6  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_from()
0x270fb  stloc.1
0x270fc  ldloc.1
0x270fd  brfalse.s loc_2713A
0x270ff  ldarg.0
0x27100  ldstr    aFrom_0// "from"
0x27105  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2710a  ldnull
0x2710b  ldc.i4.0
0x2710c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x27111  ldc.i4.0
0x27112  stloc.2
0x27113  br.s     loc_2712E
0x27115  ldarg.0
0x27116  ldstr    aActivityparty// "activityparty"
0x2711b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27120  ldloc.1
0x27121  ldloc.2
0x27122  ldelem.ref
0x27123  ldc.i4.0
0x27124  ldc.i4.0
0x27125  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x2712a  ldloc.2
0x2712b  ldc.i4.1
0x2712c  add
0x2712d  stloc.2
0x2712e  ldloc.2
0x2712f  ldloc.1
0x27130  ldlen
0x27131  conv.i4
0x27132  blt.s    loc_27115
0x27134  ldarg.0
0x27135  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x2713a  ldarg.0
0x2713b  ldstr    aImportsequence// "importsequencenumber"
0x27140  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27145  ldarg.3
0x27146  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_importsequencenumber()
0x2714b  ldc.i4.0
0x2714c  ldc.i4.0
0x2714d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x27152  ldarg.0
0x27153  ldstr    aIsbilled// "isbilled"
0x27158  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2715d  ldarg.3
0x2715e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_isbilled()
0x27163  ldc.i4.0
0x27164  ldc.i4.0
0x27165  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2716a  ldarg.0
0x2716b  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x27170  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27175  ldarg.3
0x27176  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_isworkflowcreated()
0x2717b  ldc.i4.0
0x2717c  ldc.i4.0
0x2717d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x27182  ldarg.0
0x27183  ldstr    aModifiedby// "modifiedby"
0x27188  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2718d  ldarg.3
0x2718e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_modifiedby()
0x27193  ldc.i4.0
0x27194  ldc.i4.0
0x27195  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2719a  ldarg.0
0x2719b  ldstr    aModifiedon// "modifiedon"
0x271a0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x271a5  ldarg.3
0x271a6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_modifiedon()
0x271ab  ldc.i4.0
0x271ac  ldc.i4.0
0x271ad  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x271b2  ldarg.0
0x271b3  ldstr    aNumberofpages// "numberofpages"
0x271b8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x271bd  ldarg.3
0x271be  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_numberofpages()
0x271c3  ldc.i4.0
0x271c4  ldc.i4.0
0x271c5  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x271ca  ldarg.0
0x271cb  ldstr    aOverriddencrea// "overriddencreatedon"
0x271d0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x271d5  ldarg.3
0x271d6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_overriddencreatedon()
0x271db  ldc.i4.0
0x271dc  ldc.i4.0
0x271dd  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x271e2  ldarg.0
0x271e3  ldstr    aOwnerid// "ownerid"
0x271e8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x271ed  ldarg.3
0x271ee  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_ownerid()
0x271f3  ldc.i4.0
0x271f4  ldc.i4.0
0x271f5  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x271fa  ldarg.0
0x271fb  ldstr    aOwningbusiness// "owningbusinessunit"
0x27200  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27205  ldarg.3
0x27206  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_owningbusinessunit()
0x2720b  ldc.i4.0
0x2720c  ldc.i4.0
0x2720d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x27212  ldarg.0
0x27213  ldstr    aPrioritycode// "prioritycode"
0x27218  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2721d  ldarg.3
0x2721e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_prioritycode()
0x27223  ldc.i4.0
0x27224  ldc.i4.0
0x27225  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2722a  ldarg.0
0x2722b  ldstr    aRegardingobjec// "regardingobjectid"
0x27230  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27235  ldarg.3
0x27236  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_regardingobjectid()
0x2723b  ldc.i4.0
0x2723c  ldc.i4.0
0x2723d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x27242  ldarg.0
0x27243  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x27248  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2724d  ldarg.3
0x2724e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_scheduleddurationminutes()
0x27253  ldc.i4.0
0x27254  ldc.i4.0
0x27255  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2725a  ldarg.0
0x2725b  ldstr    aScheduledend// "scheduledend"
0x27260  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27265  ldarg.3
0x27266  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_scheduledend()
0x2726b  ldc.i4.0
0x2726c  ldc.i4.0
0x2726d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x27272  ldarg.0
0x27273  ldstr    aScheduledstart// "scheduledstart"
0x27278  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2727d  ldarg.3
0x2727e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_scheduledstart()
0x27283  ldc.i4.0
0x27284  ldc.i4.0
0x27285  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2728a  ldarg.0
0x2728b  ldstr    aServiceid// "serviceid"
0x27290  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27295  ldarg.3
0x27296  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_serviceid()
0x2729b  ldc.i4.0
0x2729c  ldc.i4.0
0x2729d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x272a2  ldarg.0
0x272a3  ldstr    aStatecode// "statecode"
0x272a8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x272ad  ldarg.3
0x272ae  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.FaxStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_statecode()
0x272b3  ldc.i4.0
0x272b4  ldc.i4.0
0x272b5  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write366_FaxStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.FaxStateInfo o, bool isNullable, bool needType)
0x272ba  ldarg.0
0x272bb  ldstr    aStatuscode// "statuscode"
0x272c0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x272c5  ldarg.3
0x272c6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_statuscode()
0x272cb  ldc.i4.0
0x272cc  ldc.i4.0
0x272cd  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x272d2  ldarg.0
0x272d3  ldstr    aSubcategory// "subcategory"
0x272d8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x272dd  ldarg.3
0x272de  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::get_subcategory()
0x272e3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x272e8  ldarg.0
0x272e9  ldstr    aSubject// "subject"
0x272ee  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
  ... truncated ...
```
