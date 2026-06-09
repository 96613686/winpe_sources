# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write211_service

- ea: `0x1cad0`
- end: `0x1cd01`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write211_service`
- size: `561`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35c60`
- `0x55010`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x16cb0`
- `0x1cad0`

## string_xrefs

- `0x1cb15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cb25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cb3d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cb55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cb6d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cb85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cb9b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cbb3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cbc9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cbe1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cbf9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cc11`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cc29`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cc41`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cc59`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cc6f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cc87`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cc9f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ccb7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cccf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cce7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1cb50`: `createdby`
- `0x1cb68`: `createdon`
- `0x1cc82`: `overriddencreatedon`
- `0x1cb10`: `service`
- `0x1ccb2`: `serviceid`

## pseudocode

```c

```

## disassembly

```asm
0x1cad0  ldarg.3
0x1cad1  brtrue.s loc_1CAE0
0x1cad3  ldarg.s  4
0x1cad5  brfalse.s loc_1CADF
0x1cad7  ldarg.0
0x1cad8  ldarg.1
0x1cad9  ldarg.2
0x1cada  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1cadf  ret
0x1cae0  ldarg.s  5
0x1cae2  brtrue.s loc_1CB00
0x1cae4  ldarg.3
0x1cae5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1caea  stloc.0
0x1caeb  ldloc.0
0x1caec  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service
0x1caf1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1caf6  beq.s    loc_1CB00
0x1caf8  ldarg.0
0x1caf9  ldarg.3
0x1cafa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1caff  throw
0x1cb00  ldarg.0
0x1cb01  ldarg.1
0x1cb02  ldarg.2
0x1cb03  ldarg.3
0x1cb04  ldc.i4.0
0x1cb05  ldnull
0x1cb06  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1cb0b  ldarg.s  5
0x1cb0d  brfalse.s loc_1CB1F
0x1cb0f  ldarg.0
0x1cb10  ldstr    aService// "service"
0x1cb15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cb1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1cb1f  ldarg.0
0x1cb20  ldstr    aAnchoroffset// "anchoroffset"
0x1cb25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cb2a  ldarg.3
0x1cb2b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_anchoroffset()
0x1cb30  ldc.i4.0
0x1cb31  ldc.i4.0
0x1cb32  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1cb37  ldarg.0
0x1cb38  ldstr    aCalendarid_0// "calendarid"
0x1cb3d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cb42  ldarg.3
0x1cb43  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_calendarid()
0x1cb48  ldc.i4.0
0x1cb49  ldc.i4.0
0x1cb4a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1cb4f  ldarg.0
0x1cb50  ldstr    aCreatedby// "createdby"
0x1cb55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cb5a  ldarg.3
0x1cb5b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_createdby()
0x1cb60  ldc.i4.0
0x1cb61  ldc.i4.0
0x1cb62  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1cb67  ldarg.0
0x1cb68  ldstr    aCreatedon// "createdon"
0x1cb6d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cb72  ldarg.3
0x1cb73  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_createdon()
0x1cb78  ldc.i4.0
0x1cb79  ldc.i4.0
0x1cb7a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1cb7f  ldarg.0
0x1cb80  ldstr    aDescription_0// "description"
0x1cb85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cb8a  ldarg.3
0x1cb8b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_description()
0x1cb90  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1cb95  ldarg.0
0x1cb96  ldstr    aDuration// "duration"
0x1cb9b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cba0  ldarg.3
0x1cba1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_duration()
0x1cba6  ldc.i4.0
0x1cba7  ldc.i4.0
0x1cba8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1cbad  ldarg.0
0x1cbae  ldstr    aGranularity// "granularity"
0x1cbb3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cbb8  ldarg.3
0x1cbb9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_granularity()
0x1cbbe  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1cbc3  ldarg.0
0x1cbc4  ldstr    aImportsequence// "importsequencenumber"
0x1cbc9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cbce  ldarg.3
0x1cbcf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_importsequencenumber()
0x1cbd4  ldc.i4.0
0x1cbd5  ldc.i4.0
0x1cbd6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1cbdb  ldarg.0
0x1cbdc  ldstr    aInitialstatusc// "initialstatuscode"
0x1cbe1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cbe6  ldarg.3
0x1cbe7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_initialstatuscode()
0x1cbec  ldc.i4.0
0x1cbed  ldc.i4.0
0x1cbee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x1cbf3  ldarg.0
0x1cbf4  ldstr    aIsschedulable// "isschedulable"
0x1cbf9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cbfe  ldarg.3
0x1cbff  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_isschedulable()
0x1cc04  ldc.i4.0
0x1cc05  ldc.i4.0
0x1cc06  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1cc0b  ldarg.0
0x1cc0c  ldstr    aIsvisible// "isvisible"
0x1cc11  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cc16  ldarg.3
0x1cc17  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_isvisible()
0x1cc1c  ldc.i4.0
0x1cc1d  ldc.i4.0
0x1cc1e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1cc23  ldarg.0
0x1cc24  ldstr    aModifiedby// "modifiedby"
0x1cc29  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cc2e  ldarg.3
0x1cc2f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_modifiedby()
0x1cc34  ldc.i4.0
0x1cc35  ldc.i4.0
0x1cc36  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1cc3b  ldarg.0
0x1cc3c  ldstr    aModifiedon// "modifiedon"
0x1cc41  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cc46  ldarg.3
0x1cc47  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_modifiedon()
0x1cc4c  ldc.i4.0
0x1cc4d  ldc.i4.0
0x1cc4e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1cc53  ldarg.0
0x1cc54  ldstr    aName// "name"
0x1cc59  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cc5e  ldarg.3
0x1cc5f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_name()
0x1cc64  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1cc69  ldarg.0
0x1cc6a  ldstr    aOrganizationid// "organizationid"
0x1cc6f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cc74  ldarg.3
0x1cc75  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_organizationid()
0x1cc7a  ldc.i4.0
0x1cc7b  ldc.i4.0
0x1cc7c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1cc81  ldarg.0
0x1cc82  ldstr    aOverriddencrea// "overriddencreatedon"
0x1cc87  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cc8c  ldarg.3
0x1cc8d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_overriddencreatedon()
0x1cc92  ldc.i4.0
0x1cc93  ldc.i4.0
0x1cc94  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1cc99  ldarg.0
0x1cc9a  ldstr    aResourcespecid_0// "resourcespecid"
0x1cc9f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1cca4  ldarg.3
0x1cca5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_resourcespecid()
0x1ccaa  ldc.i4.0
0x1ccab  ldc.i4.0
0x1ccac  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ccb1  ldarg.0
0x1ccb2  ldstr    aServiceid// "serviceid"
0x1ccb7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ccbc  ldarg.3
0x1ccbd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_serviceid()
0x1ccc2  ldc.i4.0
0x1ccc3  ldc.i4.0
0x1ccc4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1ccc9  ldarg.0
0x1ccca  ldstr    aShowresources// "showresources"
0x1cccf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ccd4  ldarg.3
0x1ccd5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_showresources()
0x1ccda  ldc.i4.0
0x1ccdb  ldc.i4.0
0x1ccdc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1cce1  ldarg.0
0x1cce2  ldstr    aStrategyid// "strategyid"
0x1cce7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ccec  ldarg.3
0x1cced  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.service::get_strategyid()
0x1ccf2  ldc.i4.0
0x1ccf3  ldc.i4.0
0x1ccf4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ccf9  ldarg.0
0x1ccfa  ldarg.3
0x1ccfb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1cd00  ret
```
