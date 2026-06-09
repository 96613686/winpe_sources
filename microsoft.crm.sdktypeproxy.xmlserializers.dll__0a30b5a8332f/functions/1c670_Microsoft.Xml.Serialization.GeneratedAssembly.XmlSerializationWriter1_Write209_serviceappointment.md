# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write209_serviceappointment

- ea: `0x1c670`
- end: `0x1ca4c`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write209_serviceappointment`
- size: `988`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35bf0`
- `0x48190`
- `0x54fa0`

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
- `0x1c670`
- `0x1ca50`

## string_xrefs

- `0x1c6b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c6c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c6dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c6f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c70d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c725`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c73b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c753`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c775`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c78b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c7b0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c7c6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c7de`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c7f6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c80e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c826`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c83c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c854`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c86c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c884`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c89c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c8b4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c8cc`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c8ee`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c905`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c92e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c946`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c95e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c976`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c98e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c9a6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c9be`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c9d6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c9ec`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ca02`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ca1a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ca32`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c736`: `createdby`
- `0x1c74e`: `createdon`
- `0x1c867`: `overriddencreatedon`
- `0x1c6b0`: `serviceappointment`
- `0x1c941`: `scheduledend`
- `0x1c959`: `scheduledstart`
- `0x1c971`: `serviceid`
- `0x1c809`: `isworkflowcreated`
- `0x1c929`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x1c670  ldarg.3
0x1c671  brtrue.s loc_1C680
0x1c673  ldarg.s  4
0x1c675  brfalse.s loc_1C67F
0x1c677  ldarg.0
0x1c678  ldarg.1
0x1c679  ldarg.2
0x1c67a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1c67f  ret
0x1c680  ldarg.s  5
0x1c682  brtrue.s loc_1C6A0
0x1c684  ldarg.3
0x1c685  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c68a  stloc.0
0x1c68b  ldloc.0
0x1c68c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment
0x1c691  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c696  beq.s    loc_1C6A0
0x1c698  ldarg.0
0x1c699  ldarg.3
0x1c69a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1c69f  throw
0x1c6a0  ldarg.0
0x1c6a1  ldarg.1
0x1c6a2  ldarg.2
0x1c6a3  ldarg.3
0x1c6a4  ldc.i4.0
0x1c6a5  ldnull
0x1c6a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1c6ab  ldarg.s  5
0x1c6ad  brfalse.s loc_1C6BF
0x1c6af  ldarg.0
0x1c6b0  ldstr    aServiceappoint_0// "serviceappointment"
0x1c6b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c6ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1c6bf  ldarg.0
0x1c6c0  ldstr    aActivityid_0// "activityid"
0x1c6c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c6ca  ldarg.3
0x1c6cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_activityid()
0x1c6d0  ldc.i4.0
0x1c6d1  ldc.i4.0
0x1c6d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1c6d7  ldarg.0
0x1c6d8  ldstr    aActualduration// "actualdurationminutes"
0x1c6dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c6e2  ldarg.3
0x1c6e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_actualdurationminutes()
0x1c6e8  ldc.i4.0
0x1c6e9  ldc.i4.0
0x1c6ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1c6ef  ldarg.0
0x1c6f0  ldstr    aActualend// "actualend"
0x1c6f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c6fa  ldarg.3
0x1c6fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_actualend()
0x1c700  ldc.i4.0
0x1c701  ldc.i4.0
0x1c702  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1c707  ldarg.0
0x1c708  ldstr    aActualstart// "actualstart"
0x1c70d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c712  ldarg.3
0x1c713  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_actualstart()
0x1c718  ldc.i4.0
0x1c719  ldc.i4.0
0x1c71a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1c71f  ldarg.0
0x1c720  ldstr    aCategory// "category"
0x1c725  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c72a  ldarg.3
0x1c72b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_category()
0x1c730  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c735  ldarg.0
0x1c736  ldstr    aCreatedby// "createdby"
0x1c73b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c740  ldarg.3
0x1c741  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_createdby()
0x1c746  ldc.i4.0
0x1c747  ldc.i4.0
0x1c748  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1c74d  ldarg.0
0x1c74e  ldstr    aCreatedon// "createdon"
0x1c753  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c758  ldarg.3
0x1c759  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_createdon()
0x1c75e  ldc.i4.0
0x1c75f  ldc.i4.0
0x1c760  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1c765  ldarg.3
0x1c766  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_customers()
0x1c76b  stloc.1
0x1c76c  ldloc.1
0x1c76d  brfalse.s loc_1C7AA
0x1c76f  ldarg.0
0x1c770  ldstr    aCustomers// "customers"
0x1c775  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c77a  ldnull
0x1c77b  ldc.i4.0
0x1c77c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x1c781  ldc.i4.0
0x1c782  stloc.2
0x1c783  br.s     loc_1C79E
0x1c785  ldarg.0
0x1c786  ldstr    aActivityparty// "activityparty"
0x1c78b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c790  ldloc.1
0x1c791  ldloc.2
0x1c792  ldelem.ref
0x1c793  ldc.i4.0
0x1c794  ldc.i4.0
0x1c795  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x1c79a  ldloc.2
0x1c79b  ldc.i4.1
0x1c79c  add
0x1c79d  stloc.2
0x1c79e  ldloc.2
0x1c79f  ldloc.1
0x1c7a0  ldlen
0x1c7a1  conv.i4
0x1c7a2  blt.s    loc_1C785
0x1c7a4  ldarg.0
0x1c7a5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x1c7aa  ldarg.0
0x1c7ab  ldstr    aDescription_0// "description"
0x1c7b0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c7b5  ldarg.3
0x1c7b6  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_description()
0x1c7bb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c7c0  ldarg.0
0x1c7c1  ldstr    aImportsequence// "importsequencenumber"
0x1c7c6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c7cb  ldarg.3
0x1c7cc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_importsequencenumber()
0x1c7d1  ldc.i4.0
0x1c7d2  ldc.i4.0
0x1c7d3  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1c7d8  ldarg.0
0x1c7d9  ldstr    aIsalldayevent// "isalldayevent"
0x1c7de  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c7e3  ldarg.3
0x1c7e4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_isalldayevent()
0x1c7e9  ldc.i4.0
0x1c7ea  ldc.i4.0
0x1c7eb  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1c7f0  ldarg.0
0x1c7f1  ldstr    aIsbilled// "isbilled"
0x1c7f6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c7fb  ldarg.3
0x1c7fc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_isbilled()
0x1c801  ldc.i4.0
0x1c802  ldc.i4.0
0x1c803  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1c808  ldarg.0
0x1c809  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x1c80e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c813  ldarg.3
0x1c814  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_isworkflowcreated()
0x1c819  ldc.i4.0
0x1c81a  ldc.i4.0
0x1c81b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1c820  ldarg.0
0x1c821  ldstr    aLocation// "location"
0x1c826  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c82b  ldarg.3
0x1c82c  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_location()
0x1c831  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c836  ldarg.0
0x1c837  ldstr    aModifiedby// "modifiedby"
0x1c83c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c841  ldarg.3
0x1c842  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_modifiedby()
0x1c847  ldc.i4.0
0x1c848  ldc.i4.0
0x1c849  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1c84e  ldarg.0
0x1c84f  ldstr    aModifiedon// "modifiedon"
0x1c854  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c859  ldarg.3
0x1c85a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_modifiedon()
0x1c85f  ldc.i4.0
0x1c860  ldc.i4.0
0x1c861  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1c866  ldarg.0
0x1c867  ldstr    aOverriddencrea// "overriddencreatedon"
0x1c86c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c871  ldarg.3
0x1c872  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_overriddencreatedon()
0x1c877  ldc.i4.0
0x1c878  ldc.i4.0
0x1c879  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1c87e  ldarg.0
0x1c87f  ldstr    aOwnerid// "ownerid"
0x1c884  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c889  ldarg.3
0x1c88a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_ownerid()
0x1c88f  ldc.i4.0
0x1c890  ldc.i4.0
0x1c891  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x1c896  ldarg.0
0x1c897  ldstr    aOwningbusiness// "owningbusinessunit"
0x1c89c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c8a1  ldarg.3
0x1c8a2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_owningbusinessunit()
0x1c8a7  ldc.i4.0
0x1c8a8  ldc.i4.0
0x1c8a9  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1c8ae  ldarg.0
0x1c8af  ldstr    aPrioritycode// "prioritycode"
0x1c8b4  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c8b9  ldarg.3
0x1c8ba  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_prioritycode()
0x1c8bf  ldc.i4.0
0x1c8c0  ldc.i4.0
0x1c8c1  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1c8c6  ldarg.0
0x1c8c7  ldstr    aRegardingobjec// "regardingobjectid"
0x1c8cc  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c8d1  ldarg.3
0x1c8d2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_regardingobjectid()
0x1c8d7  ldc.i4.0
0x1c8d8  ldc.i4.0
0x1c8d9  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1c8de  ldarg.3
0x1c8df  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_resources()
0x1c8e4  stloc.3
0x1c8e5  ldloc.3
0x1c8e6  brfalse.s loc_1C928
0x1c8e8  ldarg.0
0x1c8e9  ldstr    aResources// "resources"
0x1c8ee  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c8f3  ldnull
0x1c8f4  ldc.i4.0
0x1c8f5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x1c8fa  ldc.i4.0
0x1c8fb  stloc.s  4
0x1c8fd  br.s     loc_1C91B
0x1c8ff  ldarg.0
0x1c900  ldstr    aActivityparty// "activityparty"
0x1c905  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c90a  ldloc.3
0x1c90b  ldloc.s  4
0x1c90d  ldelem.ref
0x1c90e  ldc.i4.0
0x1c90f  ldc.i4.0
0x1c910  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x1c915  ldloc.s  4
0x1c917  ldc.i4.1
0x1c918  add
0x1c919  stloc.s  4
0x1c91b  ldloc.s  4
0x1c91d  ldloc.3
0x1c91e  ldlen
0x1c91f  conv.i4
0x1c920  blt.s    loc_1C8FF
0x1c922  ldarg.0
0x1c923  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x1c928  ldarg.0
0x1c929  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x1c92e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c933  ldarg.3
0x1c934  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_scheduleddurationminutes()
0x1c939  ldc.i4.0
0x1c93a  ldc.i4.0
0x1c93b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1c940  ldarg.0
0x1c941  ldstr    aScheduledend// "scheduledend"
0x1c946  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c94b  ldarg.3
0x1c94c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_scheduledend()
0x1c951  ldc.i4.0
0x1c952  ldc.i4.0
0x1c953  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1c958  ldarg.0
0x1c959  ldstr    aScheduledstart// "scheduledstart"
0x1c95e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c963  ldarg.3
0x1c964  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_scheduledstart()
0x1c969  ldc.i4.0
0x1c96a  ldc.i4.0
0x1c96b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1c970  ldarg.0
0x1c971  ldstr    aServiceid// "serviceid"
0x1c976  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c97b  ldarg.3
0x1c97c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_serviceid()
0x1c981  ldc.i4.0
0x1c982  ldc.i4.0
0x1c983  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1c988  ldarg.0
0x1c989  ldstr    aSiteid_0// "siteid"
0x1c98e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c993  ldarg.3
0x1c994  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::get_siteid()
0x1c999  ldc.i4.0
0x1c99a  ldc.i4.0
0x1c99b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1c9a0  ldarg.0
0x1c9a1  ldstr    aStatecode// "statecode"
0x1c9a6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
  ... truncated ...
```
