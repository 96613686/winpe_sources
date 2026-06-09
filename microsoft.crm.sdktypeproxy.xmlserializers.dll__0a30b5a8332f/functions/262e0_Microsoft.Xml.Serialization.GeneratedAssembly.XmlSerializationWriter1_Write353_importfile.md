# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write353_importfile

- ea: `0x262e0`
- end: `0x2669b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write353_importfile`
- size: `955`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37240`
- `0x566d0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x262e0`
- `0x266a0`

## string_xrefs

- `0x26325`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26335`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2634b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26363`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26379`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26391`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x263a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x263c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x263d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x263f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26409`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2641f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26437`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2644f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26467`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2647f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26497`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x264af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x264c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x264dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x264f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2650b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26523`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26539`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26551`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26569`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26581`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26599`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x265af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x265c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x265db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x265f3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2660b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26623`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26639`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26651`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26669`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26681`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26374`: `createdby`
- `0x2638c`: `createdon`
- `0x26346`: `completedon`

## pseudocode

```c

```

## disassembly

```asm
0x262e0  ldarg.3
0x262e1  brtrue.s loc_262F0
0x262e3  ldarg.s  4
0x262e5  brfalse.s loc_262EF
0x262e7  ldarg.0
0x262e8  ldarg.1
0x262e9  ldarg.2
0x262ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x262ef  ret
0x262f0  ldarg.s  5
0x262f2  brtrue.s loc_26310
0x262f4  ldarg.3
0x262f5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x262fa  stloc.0
0x262fb  ldloc.0
0x262fc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile
0x26301  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x26306  beq.s    loc_26310
0x26308  ldarg.0
0x26309  ldarg.3
0x2630a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2630f  throw
0x26310  ldarg.0
0x26311  ldarg.1
0x26312  ldarg.2
0x26313  ldarg.3
0x26314  ldc.i4.0
0x26315  ldnull
0x26316  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2631b  ldarg.s  5
0x2631d  brfalse.s loc_2632F
0x2631f  ldarg.0
0x26320  ldstr    aImportfile// "importfile"
0x26325  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2632a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2632f  ldarg.0
0x26330  ldstr    aAdditionalhead// "additionalheaderrow"
0x26335  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2633a  ldarg.3
0x2633b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_additionalheaderrow()
0x26340  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x26345  ldarg.0
0x26346  ldstr    aCompletedon// "completedon"
0x2634b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26350  ldarg.3
0x26351  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_completedon()
0x26356  ldc.i4.0
0x26357  ldc.i4.0
0x26358  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2635d  ldarg.0
0x2635e  ldstr    aContent// "content"
0x26363  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26368  ldarg.3
0x26369  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_content()
0x2636e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x26373  ldarg.0
0x26374  ldstr    aCreatedby// "createdby"
0x26379  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2637e  ldarg.3
0x2637f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_createdby()
0x26384  ldc.i4.0
0x26385  ldc.i4.0
0x26386  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2638b  ldarg.0
0x2638c  ldstr    aCreatedon// "createdon"
0x26391  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26396  ldarg.3
0x26397  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_createdon()
0x2639c  ldc.i4.0
0x2639d  ldc.i4.0
0x2639e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x263a3  ldarg.0
0x263a4  ldstr    aDatadelimiterc// "datadelimitercode"
0x263a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x263ae  ldarg.3
0x263af  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_datadelimitercode()
0x263b4  ldc.i4.0
0x263b5  ldc.i4.0
0x263b6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x263bb  ldarg.0
0x263bc  ldstr    aEnableduplicat// "enableduplicatedetection"
0x263c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x263c6  ldarg.3
0x263c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_enableduplicatedetection()
0x263cc  ldc.i4.0
0x263cd  ldc.i4.0
0x263ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x263d3  ldarg.0
0x263d4  ldstr    aFailurecount// "failurecount"
0x263d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x263de  ldarg.3
0x263df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_failurecount()
0x263e4  ldc.i4.0
0x263e5  ldc.i4.0
0x263e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x263eb  ldarg.0
0x263ec  ldstr    aFielddelimiter// "fielddelimitercode"
0x263f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x263f6  ldarg.3
0x263f7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_fielddelimitercode()
0x263fc  ldc.i4.0
0x263fd  ldc.i4.0
0x263fe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x26403  ldarg.0
0x26404  ldstr    aHeaderrow// "headerrow"
0x26409  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2640e  ldarg.3
0x2640f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_headerrow()
0x26414  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x26419  ldarg.0
0x2641a  ldstr    aImportfileid// "importfileid"
0x2641f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26424  ldarg.3
0x26425  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_importfileid()
0x2642a  ldc.i4.0
0x2642b  ldc.i4.0
0x2642c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x26431  ldarg.0
0x26432  ldstr    aImportid// "importid"
0x26437  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2643c  ldarg.3
0x2643d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_importid()
0x26442  ldc.i4.0
0x26443  ldc.i4.0
0x26444  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x26449  ldarg.0
0x2644a  ldstr    aImportmapid// "importmapid"
0x2644f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26454  ldarg.3
0x26455  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_importmapid()
0x2645a  ldc.i4.0
0x2645b  ldc.i4.0
0x2645c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x26461  ldarg.0
0x26462  ldstr    aIsfirstrowhead// "isfirstrowheader"
0x26467  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2646c  ldarg.3
0x2646d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_isfirstrowheader()
0x26472  ldc.i4.0
0x26473  ldc.i4.0
0x26474  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x26479  ldarg.0
0x2647a  ldstr    aModifiedby// "modifiedby"
0x2647f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26484  ldarg.3
0x26485  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_modifiedby()
0x2648a  ldc.i4.0
0x2648b  ldc.i4.0
0x2648c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x26491  ldarg.0
0x26492  ldstr    aModifiedon// "modifiedon"
0x26497  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2649c  ldarg.3
0x2649d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_modifiedon()
0x264a2  ldc.i4.0
0x264a3  ldc.i4.0
0x264a4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x264a9  ldarg.0
0x264aa  ldstr    aName// "name"
0x264af  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x264b4  ldarg.3
0x264b5  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_name()
0x264ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x264bf  ldarg.0
0x264c0  ldstr    aOwnerid// "ownerid"
0x264c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x264ca  ldarg.3
0x264cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_ownerid()
0x264d0  ldc.i4.0
0x264d1  ldc.i4.0
0x264d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x264d7  ldarg.0
0x264d8  ldstr    aOwningbusiness// "owningbusinessunit"
0x264dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x264e2  ldarg.3
0x264e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_owningbusinessunit()
0x264e8  ldc.i4.0
0x264e9  ldc.i4.0
0x264ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x264ef  ldarg.0
0x264f0  ldstr    aParsedtablecol// "parsedtablecolumnprefix"
0x264f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x264fa  ldarg.3
0x264fb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_parsedtablecolumnprefix()
0x26500  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x26505  ldarg.0
0x26506  ldstr    aParsedtablecol_0// "parsedtablecolumnsnumber"
0x2650b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26510  ldarg.3
0x26511  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_parsedtablecolumnsnumber()
0x26516  ldc.i4.0
0x26517  ldc.i4.0
0x26518  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2651d  ldarg.0
0x2651e  ldstr    aParsedtablenam// "parsedtablename"
0x26523  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26528  ldarg.3
0x26529  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_parsedtablename()
0x2652e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x26533  ldarg.0
0x26534  ldstr    aProcesscode// "processcode"
0x26539  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2653e  ldarg.3
0x2653f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_processcode()
0x26544  ldc.i4.0
0x26545  ldc.i4.0
0x26546  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2654b  ldarg.0
0x2654c  ldstr    aProcessingstat// "processingstatus"
0x26551  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26556  ldarg.3
0x26557  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_processingstatus()
0x2655c  ldc.i4.0
0x2655d  ldc.i4.0
0x2655e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x26563  ldarg.0
0x26564  ldstr    aProgresscounte// "progresscounter"
0x26569  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2656e  ldarg.3
0x2656f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_progresscounter()
0x26574  ldc.i4.0
0x26575  ldc.i4.0
0x26576  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2657b  ldarg.0
0x2657c  ldstr    aRecordsownerid// "recordsownerid"
0x26581  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26586  ldarg.3
0x26587  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_recordsownerid()
0x2658c  ldc.i4.0
0x2658d  ldc.i4.0
0x2658e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x26593  ldarg.0
0x26594  ldstr    aSize// "size"
0x26599  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2659e  ldarg.3
0x2659f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_size()
0x265a4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x265a9  ldarg.0
0x265aa  ldstr    aSource// "source"
0x265af  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x265b4  ldarg.3
0x265b5  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_source()
0x265ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x265bf  ldarg.0
0x265c0  ldstr    aSourceentityna// "sourceentityname"
0x265c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x265ca  ldarg.3
0x265cb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_sourceentityname()
0x265d0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x265d5  ldarg.0
0x265d6  ldstr    aStatecode// "statecode"
0x265db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x265e0  ldarg.3
0x265e1  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportFileStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_statecode()
0x265e6  ldc.i4.0
0x265e7  ldc.i4.0
0x265e8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write352_ImportFileStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportFileStateInfo o, bool isNullable, bool needType)
0x265ed  ldarg.0
0x265ee  ldstr    aStatuscode// "statuscode"
0x265f3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x265f8  ldarg.3
0x265f9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_statuscode()
0x265fe  ldc.i4.0
0x265ff  ldc.i4.0
0x26600  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x26605  ldarg.0
0x26606  ldstr    aSuccesscount// "successcount"
0x2660b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26610  ldarg.3
0x26611  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_successcount()
0x26616  ldc.i4.0
0x26617  ldc.i4.0
0x26618  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2661d  ldarg.0
0x2661e  ldstr    aTargetentityna// "targetentityname"
0x26623  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26628  ldarg.3
0x26629  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_targetentityname()
0x2662e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x26633  ldarg.0
0x26634  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x26639  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2663e  ldarg.3
0x2663f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_timezoneruleversionnumber()
0x26644  ldc.i4.0
0x26645  ldc.i4.0
0x26646  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2664b  ldarg.0
0x2664c  ldstr    aTotalcount// "totalcount"
0x26651  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26656  ldarg.3
0x26657  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_totalcount()
0x2665c  ldc.i4.0
0x2665d  ldc.i4.0
0x2665e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x26663  ldarg.0
0x26664  ldstr    aUsesystemmap// "usesystemmap"
0x26669  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2666e  ldarg.3
0x2666f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importfile::get_usesystemmap()
  ... truncated ...
```
