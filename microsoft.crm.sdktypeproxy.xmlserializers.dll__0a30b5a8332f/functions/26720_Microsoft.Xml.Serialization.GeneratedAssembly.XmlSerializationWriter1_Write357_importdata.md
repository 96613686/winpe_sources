# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write357_importdata

- ea: `0x26720`
- end: `0x268c5`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write357_importdata`
- size: `421`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x372b0`
- `0x56740`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x26720`
- `0x268d0`

## string_xrefs

- `0x26765`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26775`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2678d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x267a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x267bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x267d3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x267eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26803`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2681b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26833`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2684b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26863`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2687b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26893`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x268ab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26770`: `createdby`
- `0x26788`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x26720  ldarg.3
0x26721  brtrue.s loc_26730
0x26723  ldarg.s  4
0x26725  brfalse.s loc_2672F
0x26727  ldarg.0
0x26728  ldarg.1
0x26729  ldarg.2
0x2672a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2672f  ret
0x26730  ldarg.s  5
0x26732  brtrue.s loc_26750
0x26734  ldarg.3
0x26735  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2673a  stloc.0
0x2673b  ldloc.0
0x2673c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata
0x26741  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x26746  beq.s    loc_26750
0x26748  ldarg.0
0x26749  ldarg.3
0x2674a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2674f  throw
0x26750  ldarg.0
0x26751  ldarg.1
0x26752  ldarg.2
0x26753  ldarg.3
0x26754  ldc.i4.0
0x26755  ldnull
0x26756  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2675b  ldarg.s  5
0x2675d  brfalse.s loc_2676F
0x2675f  ldarg.0
0x26760  ldstr    aImportdata// "importdata"
0x26765  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2676a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2676f  ldarg.0
0x26770  ldstr    aCreatedby// "createdby"
0x26775  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2677a  ldarg.3
0x2677b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_createdby()
0x26780  ldc.i4.0
0x26781  ldc.i4.0
0x26782  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x26787  ldarg.0
0x26788  ldstr    aCreatedon// "createdon"
0x2678d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26792  ldarg.3
0x26793  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_createdon()
0x26798  ldc.i4.0
0x26799  ldc.i4.0
0x2679a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2679f  ldarg.0
0x267a0  ldstr    aData_0// "data"
0x267a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x267aa  ldarg.3
0x267ab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_data()
0x267b0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x267b5  ldarg.0
0x267b6  ldstr    aHaserror// "haserror"
0x267bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x267c0  ldarg.3
0x267c1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_haserror()
0x267c6  ldc.i4.0
0x267c7  ldc.i4.0
0x267c8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x267cd  ldarg.0
0x267ce  ldstr    aImportdataid// "importdataid"
0x267d3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x267d8  ldarg.3
0x267d9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_importdataid()
0x267de  ldc.i4.0
0x267df  ldc.i4.0
0x267e0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x267e5  ldarg.0
0x267e6  ldstr    aImportfileid// "importfileid"
0x267eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x267f0  ldarg.3
0x267f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_importfileid()
0x267f6  ldc.i4.0
0x267f7  ldc.i4.0
0x267f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x267fd  ldarg.0
0x267fe  ldstr    aLinenumber// "linenumber"
0x26803  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26808  ldarg.3
0x26809  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_linenumber()
0x2680e  ldc.i4.0
0x2680f  ldc.i4.0
0x26810  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x26815  ldarg.0
0x26816  ldstr    aModifiedby// "modifiedby"
0x2681b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26820  ldarg.3
0x26821  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_modifiedby()
0x26826  ldc.i4.0
0x26827  ldc.i4.0
0x26828  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2682d  ldarg.0
0x2682e  ldstr    aModifiedon// "modifiedon"
0x26833  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26838  ldarg.3
0x26839  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_modifiedon()
0x2683e  ldc.i4.0
0x2683f  ldc.i4.0
0x26840  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x26845  ldarg.0
0x26846  ldstr    aOwnerid// "ownerid"
0x2684b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26850  ldarg.3
0x26851  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_ownerid()
0x26856  ldc.i4.0
0x26857  ldc.i4.0
0x26858  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2685d  ldarg.0
0x2685e  ldstr    aOwningbusiness// "owningbusinessunit"
0x26863  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26868  ldarg.3
0x26869  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_owningbusinessunit()
0x2686e  ldc.i4.0
0x2686f  ldc.i4.0
0x26870  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x26875  ldarg.0
0x26876  ldstr    aRecordid// "recordid"
0x2687b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26880  ldarg.3
0x26881  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_recordid()
0x26886  ldc.i4.0
0x26887  ldc.i4.0
0x26888  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x2688d  ldarg.0
0x2688e  ldstr    aStatecode// "statecode"
0x26893  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26898  ldarg.3
0x26899  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportDataStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_statecode()
0x2689e  ldc.i4.0
0x2689f  ldc.i4.0
0x268a0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write356_ImportDataStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportDataStateInfo o, bool isNullable, bool needType)
0x268a5  ldarg.0
0x268a6  ldstr    aStatuscode// "statuscode"
0x268ab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x268b0  ldarg.3
0x268b1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importdata::get_statuscode()
0x268b6  ldc.i4.0
0x268b7  ldc.i4.0
0x268b8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x268bd  ldarg.0
0x268be  ldarg.3
0x268bf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x268c4  ret
```
