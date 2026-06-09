# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write291_orderclose

- ea: `0x220f0`
- end: `0x223f5`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write291_orderclose`
- size: `773`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x369f0`
- `0x55e10`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x220f0`
- `0x22400`

## string_xrefs

- `0x22135`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22145`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2215d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22175`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2218d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x221a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x221bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x221d3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x221eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22201`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22219`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22231`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22249`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22261`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22279`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2228f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x222a7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x222bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x222d7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x222ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22307`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2231f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22337`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2234f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22367`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2237f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x22397`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x223ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x223c3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x223db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x221b6`: `createdby`
- `0x221ce`: `createdon`
- `0x2228a`: `overriddencreatedon`
- `0x2231a`: `scheduledend`
- `0x22332`: `scheduledstart`
- `0x2234a`: `serviceid`
- `0x2222c`: `isworkflowcreated`
- `0x22302`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x220f0  ldarg.3
0x220f1  brtrue.s loc_22100
0x220f3  ldarg.s  4
0x220f5  brfalse.s loc_220FF
0x220f7  ldarg.0
0x220f8  ldarg.1
0x220f9  ldarg.2
0x220fa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x220ff  ret
0x22100  ldarg.s  5
0x22102  brtrue.s loc_22120
0x22104  ldarg.3
0x22105  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2210a  stloc.0
0x2210b  ldloc.0
0x2210c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose
0x22111  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22116  beq.s    loc_22120
0x22118  ldarg.0
0x22119  ldarg.3
0x2211a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2211f  throw
0x22120  ldarg.0
0x22121  ldarg.1
0x22122  ldarg.2
0x22123  ldarg.3
0x22124  ldc.i4.0
0x22125  ldnull
0x22126  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2212b  ldarg.s  5
0x2212d  brfalse.s loc_2213F
0x2212f  ldarg.0
0x22130  ldstr    aOrderclose// "orderclose"
0x22135  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2213a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2213f  ldarg.0
0x22140  ldstr    aActivityid_0// "activityid"
0x22145  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2214a  ldarg.3
0x2214b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_activityid()
0x22150  ldc.i4.0
0x22151  ldc.i4.0
0x22152  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x22157  ldarg.0
0x22158  ldstr    aActualduration// "actualdurationminutes"
0x2215d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22162  ldarg.3
0x22163  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_actualdurationminutes()
0x22168  ldc.i4.0
0x22169  ldc.i4.0
0x2216a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2216f  ldarg.0
0x22170  ldstr    aActualend// "actualend"
0x22175  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2217a  ldarg.3
0x2217b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_actualend()
0x22180  ldc.i4.0
0x22181  ldc.i4.0
0x22182  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22187  ldarg.0
0x22188  ldstr    aActualstart// "actualstart"
0x2218d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22192  ldarg.3
0x22193  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_actualstart()
0x22198  ldc.i4.0
0x22199  ldc.i4.0
0x2219a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2219f  ldarg.0
0x221a0  ldstr    aCategory// "category"
0x221a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x221aa  ldarg.3
0x221ab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_category()
0x221b0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x221b5  ldarg.0
0x221b6  ldstr    aCreatedby// "createdby"
0x221bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x221c0  ldarg.3
0x221c1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_createdby()
0x221c6  ldc.i4.0
0x221c7  ldc.i4.0
0x221c8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x221cd  ldarg.0
0x221ce  ldstr    aCreatedon// "createdon"
0x221d3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x221d8  ldarg.3
0x221d9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_createdon()
0x221de  ldc.i4.0
0x221df  ldc.i4.0
0x221e0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x221e5  ldarg.0
0x221e6  ldstr    aDescription_0// "description"
0x221eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x221f0  ldarg.3
0x221f1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_description()
0x221f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x221fb  ldarg.0
0x221fc  ldstr    aImportsequence// "importsequencenumber"
0x22201  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22206  ldarg.3
0x22207  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_importsequencenumber()
0x2220c  ldc.i4.0
0x2220d  ldc.i4.0
0x2220e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x22213  ldarg.0
0x22214  ldstr    aIsbilled// "isbilled"
0x22219  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2221e  ldarg.3
0x2221f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_isbilled()
0x22224  ldc.i4.0
0x22225  ldc.i4.0
0x22226  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2222b  ldarg.0
0x2222c  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x22231  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22236  ldarg.3
0x22237  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_isworkflowcreated()
0x2223c  ldc.i4.0
0x2223d  ldc.i4.0
0x2223e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x22243  ldarg.0
0x22244  ldstr    aModifiedby// "modifiedby"
0x22249  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2224e  ldarg.3
0x2224f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_modifiedby()
0x22254  ldc.i4.0
0x22255  ldc.i4.0
0x22256  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2225b  ldarg.0
0x2225c  ldstr    aModifiedon// "modifiedon"
0x22261  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22266  ldarg.3
0x22267  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_modifiedon()
0x2226c  ldc.i4.0
0x2226d  ldc.i4.0
0x2226e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22273  ldarg.0
0x22274  ldstr    aOrdernumber// "ordernumber"
0x22279  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2227e  ldarg.3
0x2227f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_ordernumber()
0x22284  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x22289  ldarg.0
0x2228a  ldstr    aOverriddencrea// "overriddencreatedon"
0x2228f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22294  ldarg.3
0x22295  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_overriddencreatedon()
0x2229a  ldc.i4.0
0x2229b  ldc.i4.0
0x2229c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x222a1  ldarg.0
0x222a2  ldstr    aOwnerid// "ownerid"
0x222a7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x222ac  ldarg.3
0x222ad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_ownerid()
0x222b2  ldc.i4.0
0x222b3  ldc.i4.0
0x222b4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x222b9  ldarg.0
0x222ba  ldstr    aOwningbusiness// "owningbusinessunit"
0x222bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x222c4  ldarg.3
0x222c5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_owningbusinessunit()
0x222ca  ldc.i4.0
0x222cb  ldc.i4.0
0x222cc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x222d1  ldarg.0
0x222d2  ldstr    aRevision// "revision"
0x222d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x222dc  ldarg.3
0x222dd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_revision()
0x222e2  ldc.i4.0
0x222e3  ldc.i4.0
0x222e4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x222e9  ldarg.0
0x222ea  ldstr    aSalesorderid// "salesorderid"
0x222ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x222f4  ldarg.3
0x222f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_salesorderid()
0x222fa  ldc.i4.0
0x222fb  ldc.i4.0
0x222fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22301  ldarg.0
0x22302  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x22307  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2230c  ldarg.3
0x2230d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_scheduleddurationminutes()
0x22312  ldc.i4.0
0x22313  ldc.i4.0
0x22314  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x22319  ldarg.0
0x2231a  ldstr    aScheduledend// "scheduledend"
0x2231f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22324  ldarg.3
0x22325  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_scheduledend()
0x2232a  ldc.i4.0
0x2232b  ldc.i4.0
0x2232c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22331  ldarg.0
0x22332  ldstr    aScheduledstart// "scheduledstart"
0x22337  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2233c  ldarg.3
0x2233d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_scheduledstart()
0x22342  ldc.i4.0
0x22343  ldc.i4.0
0x22344  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x22349  ldarg.0
0x2234a  ldstr    aServiceid// "serviceid"
0x2234f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22354  ldarg.3
0x22355  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_serviceid()
0x2235a  ldc.i4.0
0x2235b  ldc.i4.0
0x2235c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x22361  ldarg.0
0x22362  ldstr    aStatecode// "statecode"
0x22367  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2236c  ldarg.3
0x2236d  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.OrderCloseStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_statecode()
0x22372  ldc.i4.0
0x22373  ldc.i4.0
0x22374  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write290_OrderCloseStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.OrderCloseStateInfo o, bool isNullable, bool needType)
0x22379  ldarg.0
0x2237a  ldstr    aStatuscode// "statuscode"
0x2237f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x22384  ldarg.3
0x22385  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_statuscode()
0x2238a  ldc.i4.0
0x2238b  ldc.i4.0
0x2238c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x22391  ldarg.0
0x22392  ldstr    aSubcategory// "subcategory"
0x22397  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2239c  ldarg.3
0x2239d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_subcategory()
0x223a2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x223a7  ldarg.0
0x223a8  ldstr    aSubject// "subject"
0x223ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x223b2  ldarg.3
0x223b3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_subject()
0x223b8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x223bd  ldarg.0
0x223be  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x223c3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x223c8  ldarg.3
0x223c9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_timezoneruleversionnumber()
0x223ce  ldc.i4.0
0x223cf  ldc.i4.0
0x223d0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x223d5  ldarg.0
0x223d6  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x223db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x223e0  ldarg.3
0x223e1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.orderclose::get_utcconversiontimezonecode()
0x223e6  ldc.i4.0
0x223e7  ldc.i4.0
0x223e8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x223ed  ldarg.0
0x223ee  ldarg.3
0x223ef  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x223f4  ret
```
