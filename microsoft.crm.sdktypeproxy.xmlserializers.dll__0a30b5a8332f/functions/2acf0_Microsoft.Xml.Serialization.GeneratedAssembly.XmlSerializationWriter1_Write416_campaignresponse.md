# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write416_campaignresponse

- ea: `0x2acf0`
- end: `0x2b1f8`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write416_campaignresponse`
- size: `1288`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37be0`
- `0x57070`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x19770`
- `0x2acf0`
- `0x2b200`

## string_xrefs

- `0x2ad35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ad45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ad5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ad75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ad8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ada5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2adbb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2add3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ade9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ae01`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ae23`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ae39`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ae5e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ae74`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ae8a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2aea0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2aec0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2aed7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2af00`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2af18`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2af30`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2af48`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2af5e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2af76`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2af8e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2afa6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2afbe`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2afd6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2affa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b011`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b03c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b054`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b06a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b082`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b09a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b0b2`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b0ca`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b0e2`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b0fa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b112`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b12a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b142`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b158`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b16e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b184`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b19c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b1b4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b1ca`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2b1e0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ade4`: `createdby`
- `0x2adfc`: `createdon`
- `0x2afa1`: `overriddencreatedon`
- `0x2b0c5`: `scheduledend`
- `0x2b0dd`: `scheduledstart`
- `0x2b0f5`: `serviceid`
- `0x2af2b`: `isworkflowcreated`
- `0x2b0ad`: `scheduleddurationminutes`
- `0x2adce`: `companyname`
- `0x2b1af`: `yomicompanyname`

## pseudocode

```c

```

## disassembly

```asm
0x2acf0  ldarg.3
0x2acf1  brtrue.s loc_2AD00
0x2acf3  ldarg.s  4
0x2acf5  brfalse.s loc_2ACFF
0x2acf7  ldarg.0
0x2acf8  ldarg.1
0x2acf9  ldarg.2
0x2acfa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2acff  ret
0x2ad00  ldarg.s  5
0x2ad02  brtrue.s loc_2AD20
0x2ad04  ldarg.3
0x2ad05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2ad0a  stloc.0
0x2ad0b  ldloc.0
0x2ad0c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse
0x2ad11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ad16  beq.s    loc_2AD20
0x2ad18  ldarg.0
0x2ad19  ldarg.3
0x2ad1a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2ad1f  throw
0x2ad20  ldarg.0
0x2ad21  ldarg.1
0x2ad22  ldarg.2
0x2ad23  ldarg.3
0x2ad24  ldc.i4.0
0x2ad25  ldnull
0x2ad26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2ad2b  ldarg.s  5
0x2ad2d  brfalse.s loc_2AD3F
0x2ad2f  ldarg.0
0x2ad30  ldstr    aCampaignrespon_0// "campaignresponse"
0x2ad35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ad3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2ad3f  ldarg.0
0x2ad40  ldstr    aActivityid_0// "activityid"
0x2ad45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ad4a  ldarg.3
0x2ad4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_activityid()
0x2ad50  ldc.i4.0
0x2ad51  ldc.i4.0
0x2ad52  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2ad57  ldarg.0
0x2ad58  ldstr    aActualduration// "actualdurationminutes"
0x2ad5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ad62  ldarg.3
0x2ad63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_actualdurationminutes()
0x2ad68  ldc.i4.0
0x2ad69  ldc.i4.0
0x2ad6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2ad6f  ldarg.0
0x2ad70  ldstr    aActualend// "actualend"
0x2ad75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ad7a  ldarg.3
0x2ad7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_actualend()
0x2ad80  ldc.i4.0
0x2ad81  ldc.i4.0
0x2ad82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2ad87  ldarg.0
0x2ad88  ldstr    aActualstart// "actualstart"
0x2ad8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ad92  ldarg.3
0x2ad93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_actualstart()
0x2ad98  ldc.i4.0
0x2ad99  ldc.i4.0
0x2ad9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2ad9f  ldarg.0
0x2ada0  ldstr    aCategory// "category"
0x2ada5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2adaa  ldarg.3
0x2adab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_category()
0x2adb0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2adb5  ldarg.0
0x2adb6  ldstr    aChanneltypecod// "channeltypecode"
0x2adbb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2adc0  ldarg.3
0x2adc1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_channeltypecode()
0x2adc6  ldc.i4.0
0x2adc7  ldc.i4.0
0x2adc8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2adcd  ldarg.0
0x2adce  ldstr    aCompanyname// "companyname"
0x2add3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2add8  ldarg.3
0x2add9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_companyname()
0x2adde  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ade3  ldarg.0
0x2ade4  ldstr    aCreatedby// "createdby"
0x2ade9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2adee  ldarg.3
0x2adef  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_createdby()
0x2adf4  ldc.i4.0
0x2adf5  ldc.i4.0
0x2adf6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2adfb  ldarg.0
0x2adfc  ldstr    aCreatedon// "createdon"
0x2ae01  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ae06  ldarg.3
0x2ae07  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_createdon()
0x2ae0c  ldc.i4.0
0x2ae0d  ldc.i4.0
0x2ae0e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2ae13  ldarg.3
0x2ae14  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_customer()
0x2ae19  stloc.1
0x2ae1a  ldloc.1
0x2ae1b  brfalse.s loc_2AE58
0x2ae1d  ldarg.0
0x2ae1e  ldstr    aCustomer_0// "customer"
0x2ae23  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ae28  ldnull
0x2ae29  ldc.i4.0
0x2ae2a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x2ae2f  ldc.i4.0
0x2ae30  stloc.2
0x2ae31  br.s     loc_2AE4C
0x2ae33  ldarg.0
0x2ae34  ldstr    aActivityparty// "activityparty"
0x2ae39  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ae3e  ldloc.1
0x2ae3f  ldloc.2
0x2ae40  ldelem.ref
0x2ae41  ldc.i4.0
0x2ae42  ldc.i4.0
0x2ae43  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x2ae48  ldloc.2
0x2ae49  ldc.i4.1
0x2ae4a  add
0x2ae4b  stloc.2
0x2ae4c  ldloc.2
0x2ae4d  ldloc.1
0x2ae4e  ldlen
0x2ae4f  conv.i4
0x2ae50  blt.s    loc_2AE33
0x2ae52  ldarg.0
0x2ae53  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x2ae58  ldarg.0
0x2ae59  ldstr    aDescription_0// "description"
0x2ae5e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ae63  ldarg.3
0x2ae64  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_description()
0x2ae69  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ae6e  ldarg.0
0x2ae6f  ldstr    aEmailaddress// "emailaddress"
0x2ae74  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ae79  ldarg.3
0x2ae7a  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_emailaddress()
0x2ae7f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ae84  ldarg.0
0x2ae85  ldstr    aFax// "fax"
0x2ae8a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ae8f  ldarg.3
0x2ae90  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_fax()
0x2ae95  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ae9a  ldarg.0
0x2ae9b  ldstr    aFirstname// "firstname"
0x2aea0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2aea5  ldarg.3
0x2aea6  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_firstname()
0x2aeab  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2aeb0  ldarg.3
0x2aeb1  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_from()
0x2aeb6  stloc.3
0x2aeb7  ldloc.3
0x2aeb8  brfalse.s loc_2AEFA
0x2aeba  ldarg.0
0x2aebb  ldstr    aFrom_0// "from"
0x2aec0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2aec5  ldnull
0x2aec6  ldc.i4.0
0x2aec7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x2aecc  ldc.i4.0
0x2aecd  stloc.s  4
0x2aecf  br.s     loc_2AEED
0x2aed1  ldarg.0
0x2aed2  ldstr    aActivityparty// "activityparty"
0x2aed7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2aedc  ldloc.3
0x2aedd  ldloc.s  4
0x2aedf  ldelem.ref
0x2aee0  ldc.i4.0
0x2aee1  ldc.i4.0
0x2aee2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x2aee7  ldloc.s  4
0x2aee9  ldc.i4.1
0x2aeea  add
0x2aeeb  stloc.s  4
0x2aeed  ldloc.s  4
0x2aeef  ldloc.3
0x2aef0  ldlen
0x2aef1  conv.i4
0x2aef2  blt.s    loc_2AED1
0x2aef4  ldarg.0
0x2aef5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x2aefa  ldarg.0
0x2aefb  ldstr    aImportsequence// "importsequencenumber"
0x2af00  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2af05  ldarg.3
0x2af06  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_importsequencenumber()
0x2af0b  ldc.i4.0
0x2af0c  ldc.i4.0
0x2af0d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2af12  ldarg.0
0x2af13  ldstr    aIsbilled// "isbilled"
0x2af18  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2af1d  ldarg.3
0x2af1e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_isbilled()
0x2af23  ldc.i4.0
0x2af24  ldc.i4.0
0x2af25  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2af2a  ldarg.0
0x2af2b  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x2af30  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2af35  ldarg.3
0x2af36  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_isworkflowcreated()
0x2af3b  ldc.i4.0
0x2af3c  ldc.i4.0
0x2af3d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2af42  ldarg.0
0x2af43  ldstr    aLastname// "lastname"
0x2af48  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2af4d  ldarg.3
0x2af4e  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_lastname()
0x2af53  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2af58  ldarg.0
0x2af59  ldstr    aModifiedby// "modifiedby"
0x2af5e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2af63  ldarg.3
0x2af64  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_modifiedby()
0x2af69  ldc.i4.0
0x2af6a  ldc.i4.0
0x2af6b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2af70  ldarg.0
0x2af71  ldstr    aModifiedon// "modifiedon"
0x2af76  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2af7b  ldarg.3
0x2af7c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_modifiedon()
0x2af81  ldc.i4.0
0x2af82  ldc.i4.0
0x2af83  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2af88  ldarg.0
0x2af89  ldstr    aOriginatingact// "originatingactivityid"
0x2af8e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2af93  ldarg.3
0x2af94  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_originatingactivityid()
0x2af99  ldc.i4.0
0x2af9a  ldc.i4.0
0x2af9b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2afa0  ldarg.0
0x2afa1  ldstr    aOverriddencrea// "overriddencreatedon"
0x2afa6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2afab  ldarg.3
0x2afac  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_overriddencreatedon()
0x2afb1  ldc.i4.0
0x2afb2  ldc.i4.0
0x2afb3  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2afb8  ldarg.0
0x2afb9  ldstr    aOwnerid// "ownerid"
0x2afbe  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2afc3  ldarg.3
0x2afc4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_ownerid()
0x2afc9  ldc.i4.0
0x2afca  ldc.i4.0
0x2afcb  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2afd0  ldarg.0
0x2afd1  ldstr    aOwningbusiness// "owningbusinessunit"
0x2afd6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2afdb  ldarg.3
0x2afdc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_owningbusinessunit()
0x2afe1  ldc.i4.0
0x2afe2  ldc.i4.0
0x2afe3  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2afe8  ldarg.3
0x2afe9  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::get_partner()
0x2afee  stloc.s  5
0x2aff0  ldloc.s  5
0x2aff2  brfalse.s loc_2B036
0x2aff4  ldarg.0
0x2aff5  ldstr    aPartner// "partner"
0x2affa  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2afff  ldnull
0x2b000  ldc.i4.0
0x2b001  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x2b006  ldc.i4.0
0x2b007  stloc.s  6
0x2b009  br.s     loc_2B028
0x2b00b  ldarg.0
0x2b00c  ldstr    aActivityparty// "activityparty"
0x2b011  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2b016  ldloc.s  5
0x2b018  ldloc.s  6
0x2b01a  ldelem.ref
0x2b01b  ldc.i4.0
0x2b01c  ldc.i4.0
0x2b01d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x2b022  ldloc.s  6
0x2b024  ldc.i4.1
0x2b025  add
0x2b026  stloc.s  6
  ... truncated ...
```
