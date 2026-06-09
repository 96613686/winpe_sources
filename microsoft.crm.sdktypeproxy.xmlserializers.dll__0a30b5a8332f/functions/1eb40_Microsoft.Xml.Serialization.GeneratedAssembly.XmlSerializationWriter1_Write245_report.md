# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write245_report

- ea: `0x1eb40`
- end: `0x1ee81`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write245_report`
- size: `833`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x362f0`
- `0x556a0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x16a10`
- `0x1eb40`

## string_xrefs

- `0x1eb85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eb95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ebab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ebc1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ebd7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ebef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ec07`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ec1d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ec33`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ec49`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ec5f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ec77`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ec8f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eca7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ecbf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ecd7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eced`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ed05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ed1d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ed33`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ed4b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ed63`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ed7b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ed91`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eda9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1edc1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1edd7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1edef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ee07`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ee1f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ee37`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ee4f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ee67`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ebd2`: `createdby`
- `0x1ebea`: `createdon`
- `0x1ec02`: `customreportxml`
- `0x1eca2`: `isscheduledreport`
- `0x1edbc`: `schedulexml`

## pseudocode

```c

```

## disassembly

```asm
0x1eb40  ldarg.3
0x1eb41  brtrue.s loc_1EB50
0x1eb43  ldarg.s  4
0x1eb45  brfalse.s loc_1EB4F
0x1eb47  ldarg.0
0x1eb48  ldarg.1
0x1eb49  ldarg.2
0x1eb4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1eb4f  ret
0x1eb50  ldarg.s  5
0x1eb52  brtrue.s loc_1EB70
0x1eb54  ldarg.3
0x1eb55  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1eb5a  stloc.0
0x1eb5b  ldloc.0
0x1eb5c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report
0x1eb61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1eb66  beq.s    loc_1EB70
0x1eb68  ldarg.0
0x1eb69  ldarg.3
0x1eb6a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1eb6f  throw
0x1eb70  ldarg.0
0x1eb71  ldarg.1
0x1eb72  ldarg.2
0x1eb73  ldarg.3
0x1eb74  ldc.i4.0
0x1eb75  ldnull
0x1eb76  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1eb7b  ldarg.s  5
0x1eb7d  brfalse.s loc_1EB8F
0x1eb7f  ldarg.0
0x1eb80  ldstr    aReport// "report"
0x1eb85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1eb8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1eb8f  ldarg.0
0x1eb90  ldstr    aBodybinary// "bodybinary"
0x1eb95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1eb9a  ldarg.3
0x1eb9b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_bodybinary()
0x1eba0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1eba5  ldarg.0
0x1eba6  ldstr    aBodytext// "bodytext"
0x1ebab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ebb0  ldarg.3
0x1ebb1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_bodytext()
0x1ebb6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ebbb  ldarg.0
0x1ebbc  ldstr    aBodyurl// "bodyurl"
0x1ebc1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ebc6  ldarg.3
0x1ebc7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_bodyurl()
0x1ebcc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ebd1  ldarg.0
0x1ebd2  ldstr    aCreatedby// "createdby"
0x1ebd7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ebdc  ldarg.3
0x1ebdd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_createdby()
0x1ebe2  ldc.i4.0
0x1ebe3  ldc.i4.0
0x1ebe4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ebe9  ldarg.0
0x1ebea  ldstr    aCreatedon// "createdon"
0x1ebef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ebf4  ldarg.3
0x1ebf5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_createdon()
0x1ebfa  ldc.i4.0
0x1ebfb  ldc.i4.0
0x1ebfc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ec01  ldarg.0
0x1ec02  ldstr    aCustomreportxm// "customreportxml"
0x1ec07  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ec0c  ldarg.3
0x1ec0d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_customreportxml()
0x1ec12  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ec17  ldarg.0
0x1ec18  ldstr    aDefaultfilter// "defaultfilter"
0x1ec1d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ec22  ldarg.3
0x1ec23  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_defaultfilter()
0x1ec28  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ec2d  ldarg.0
0x1ec2e  ldstr    aDescription_0// "description"
0x1ec33  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ec38  ldarg.3
0x1ec39  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_description()
0x1ec3e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ec43  ldarg.0
0x1ec44  ldstr    aFilename// "filename"
0x1ec49  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ec4e  ldarg.3
0x1ec4f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_filename()
0x1ec54  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ec59  ldarg.0
0x1ec5a  ldstr    aFilesize// "filesize"
0x1ec5f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ec64  ldarg.3
0x1ec65  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_filesize()
0x1ec6a  ldc.i4.0
0x1ec6b  ldc.i4.0
0x1ec6c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ec71  ldarg.0
0x1ec72  ldstr    aIscustomreport// "iscustomreport"
0x1ec77  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ec7c  ldarg.3
0x1ec7d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_iscustomreport()
0x1ec82  ldc.i4.0
0x1ec83  ldc.i4.0
0x1ec84  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1ec89  ldarg.0
0x1ec8a  ldstr    aIspersonal// "ispersonal"
0x1ec8f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ec94  ldarg.3
0x1ec95  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_ispersonal()
0x1ec9a  ldc.i4.0
0x1ec9b  ldc.i4.0
0x1ec9c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1eca1  ldarg.0
0x1eca2  ldstr    aIsscheduledrep// "isscheduledreport"
0x1eca7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ecac  ldarg.3
0x1ecad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_isscheduledreport()
0x1ecb2  ldc.i4.0
0x1ecb3  ldc.i4.0
0x1ecb4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1ecb9  ldarg.0
0x1ecba  ldstr    aLanguagecode_0// "languagecode"
0x1ecbf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ecc4  ldarg.3
0x1ecc5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_languagecode()
0x1ecca  ldc.i4.0
0x1eccb  ldc.i4.0
0x1eccc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ecd1  ldarg.0
0x1ecd2  ldstr    aMimetype// "mimetype"
0x1ecd7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ecdc  ldarg.3
0x1ecdd  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_mimetype()
0x1ece2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ece7  ldarg.0
0x1ece8  ldstr    aModifiedby// "modifiedby"
0x1eced  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ecf2  ldarg.3
0x1ecf3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_modifiedby()
0x1ecf8  ldc.i4.0
0x1ecf9  ldc.i4.0
0x1ecfa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ecff  ldarg.0
0x1ed00  ldstr    aModifiedon// "modifiedon"
0x1ed05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ed0a  ldarg.3
0x1ed0b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_modifiedon()
0x1ed10  ldc.i4.0
0x1ed11  ldc.i4.0
0x1ed12  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ed17  ldarg.0
0x1ed18  ldstr    aName// "name"
0x1ed1d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ed22  ldarg.3
0x1ed23  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_name()
0x1ed28  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ed2d  ldarg.0
0x1ed2e  ldstr    aOwnerid// "ownerid"
0x1ed33  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ed38  ldarg.3
0x1ed39  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_ownerid()
0x1ed3e  ldc.i4.0
0x1ed3f  ldc.i4.0
0x1ed40  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x1ed45  ldarg.0
0x1ed46  ldstr    aOwningbusiness// "owningbusinessunit"
0x1ed4b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ed50  ldarg.3
0x1ed51  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_owningbusinessunit()
0x1ed56  ldc.i4.0
0x1ed57  ldc.i4.0
0x1ed58  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ed5d  ldarg.0
0x1ed5e  ldstr    aParentreportid// "parentreportid"
0x1ed63  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ed68  ldarg.3
0x1ed69  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_parentreportid()
0x1ed6e  ldc.i4.0
0x1ed6f  ldc.i4.0
0x1ed70  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ed75  ldarg.0
0x1ed76  ldstr    aQueryinfo// "queryinfo"
0x1ed7b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ed80  ldarg.3
0x1ed81  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_queryinfo()
0x1ed86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ed8b  ldarg.0
0x1ed8c  ldstr    aReportid// "reportid"
0x1ed91  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ed96  ldarg.3
0x1ed97  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_reportid()
0x1ed9c  ldc.i4.0
0x1ed9d  ldc.i4.0
0x1ed9e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1eda3  ldarg.0
0x1eda4  ldstr    aReporttypecode// "reporttypecode"
0x1eda9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1edae  ldarg.3
0x1edaf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_reporttypecode()
0x1edb4  ldc.i4.0
0x1edb5  ldc.i4.0
0x1edb6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1edbb  ldarg.0
0x1edbc  ldstr    aSchedulexml// "schedulexml"
0x1edc1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1edc6  ldarg.3
0x1edc7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_schedulexml()
0x1edcc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1edd1  ldarg.0
0x1edd2  ldstr    aSignaturedate// "signaturedate"
0x1edd7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1eddc  ldarg.3
0x1eddd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_signaturedate()
0x1ede2  ldc.i4.0
0x1ede3  ldc.i4.0
0x1ede4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ede9  ldarg.0
0x1edea  ldstr    aSignatureid// "signatureid"
0x1edef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1edf4  ldarg.3
0x1edf5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_signatureid()
0x1edfa  ldc.i4.0
0x1edfb  ldc.i4.0
0x1edfc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1ee01  ldarg.0
0x1ee02  ldstr    aSignaturelcid// "signaturelcid"
0x1ee07  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ee0c  ldarg.3
0x1ee0d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_signaturelcid()
0x1ee12  ldc.i4.0
0x1ee13  ldc.i4.0
0x1ee14  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ee19  ldarg.0
0x1ee1a  ldstr    aSignaturemajor// "signaturemajorversion"
0x1ee1f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ee24  ldarg.3
0x1ee25  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_signaturemajorversion()
0x1ee2a  ldc.i4.0
0x1ee2b  ldc.i4.0
0x1ee2c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ee31  ldarg.0
0x1ee32  ldstr    aSignatureminor// "signatureminorversion"
0x1ee37  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ee3c  ldarg.3
0x1ee3d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_signatureminorversion()
0x1ee42  ldc.i4.0
0x1ee43  ldc.i4.0
0x1ee44  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ee49  ldarg.0
0x1ee4a  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x1ee4f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ee54  ldarg.3
0x1ee55  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_timezoneruleversionnumber()
0x1ee5a  ldc.i4.0
0x1ee5b  ldc.i4.0
0x1ee5c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ee61  ldarg.0
0x1ee62  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x1ee67  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ee6c  ldarg.3
0x1ee6d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.report::get_utcconversiontimezonecode()
0x1ee72  ldc.i4.0
0x1ee73  ldc.i4.0
0x1ee74  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ee79  ldarg.0
0x1ee7a  ldarg.3
0x1ee7b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1ee80  ret
```
