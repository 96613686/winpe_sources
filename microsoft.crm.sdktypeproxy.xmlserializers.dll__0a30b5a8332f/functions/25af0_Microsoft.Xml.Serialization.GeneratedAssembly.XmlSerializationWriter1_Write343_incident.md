# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write343_incident

- ea: `0x25af0`
- end: `0x25e87`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write343_incident`
- size: `919`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x370f0`
- `0x56580`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x170c0`
- `0x25af0`
- `0x25e90`

## string_xrefs

- `0x25b35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25b45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25b5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25b75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25b8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25ba5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25bbd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25bd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25bed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25c05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25c1d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25c35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25c4d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25c63`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25c7b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25c93`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25cab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25cc3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25cdb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25cf3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25d0b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25d23`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25d3b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25d53`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25d6b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25d83`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25d9b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25db1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25dc9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25de1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25df9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25e11`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25e29`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25e3f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25e57`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25e6d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25be8`: `createdby`
- `0x25c00`: `createdon`
- `0x25d1e`: `overriddencreatedon`
- `0x25b40`: `actualserviceunits`
- `0x25b58`: `billedserviceunits`
- `0x25bd0`: `contractservicelevelcode`

## pseudocode

```c

```

## disassembly

```asm
0x25af0  ldarg.3
0x25af1  brtrue.s loc_25B00
0x25af3  ldarg.s  4
0x25af5  brfalse.s loc_25AFF
0x25af7  ldarg.0
0x25af8  ldarg.1
0x25af9  ldarg.2
0x25afa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x25aff  ret
0x25b00  ldarg.s  5
0x25b02  brtrue.s loc_25B20
0x25b04  ldarg.3
0x25b05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x25b0a  stloc.0
0x25b0b  ldloc.0
0x25b0c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident
0x25b11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25b16  beq.s    loc_25B20
0x25b18  ldarg.0
0x25b19  ldarg.3
0x25b1a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x25b1f  throw
0x25b20  ldarg.0
0x25b21  ldarg.1
0x25b22  ldarg.2
0x25b23  ldarg.3
0x25b24  ldc.i4.0
0x25b25  ldnull
0x25b26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x25b2b  ldarg.s  5
0x25b2d  brfalse.s loc_25B3F
0x25b2f  ldarg.0
0x25b30  ldstr    aIncident// "incident"
0x25b35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25b3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x25b3f  ldarg.0
0x25b40  ldstr    aActualserviceu// "actualserviceunits"
0x25b45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25b4a  ldarg.3
0x25b4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_actualserviceunits()
0x25b50  ldc.i4.0
0x25b51  ldc.i4.0
0x25b52  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x25b57  ldarg.0
0x25b58  ldstr    aBilledserviceu// "billedserviceunits"
0x25b5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25b62  ldarg.3
0x25b63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_billedserviceunits()
0x25b68  ldc.i4.0
0x25b69  ldc.i4.0
0x25b6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x25b6f  ldarg.0
0x25b70  ldstr    aCaseorigincode// "caseorigincode"
0x25b75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25b7a  ldarg.3
0x25b7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_caseorigincode()
0x25b80  ldc.i4.0
0x25b81  ldc.i4.0
0x25b82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x25b87  ldarg.0
0x25b88  ldstr    aCasetypecode// "casetypecode"
0x25b8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25b92  ldarg.3
0x25b93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_casetypecode()
0x25b98  ldc.i4.0
0x25b99  ldc.i4.0
0x25b9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x25b9f  ldarg.0
0x25ba0  ldstr    aContractdetail_1// "contractdetailid"
0x25ba5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25baa  ldarg.3
0x25bab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_contractdetailid()
0x25bb0  ldc.i4.0
0x25bb1  ldc.i4.0
0x25bb2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25bb7  ldarg.0
0x25bb8  ldstr    aContractid// "contractid"
0x25bbd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25bc2  ldarg.3
0x25bc3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_contractid()
0x25bc8  ldc.i4.0
0x25bc9  ldc.i4.0
0x25bca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25bcf  ldarg.0
0x25bd0  ldstr    aContractservic// "contractservicelevelcode"
0x25bd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25bda  ldarg.3
0x25bdb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_contractservicelevelcode()
0x25be0  ldc.i4.0
0x25be1  ldc.i4.0
0x25be2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x25be7  ldarg.0
0x25be8  ldstr    aCreatedby// "createdby"
0x25bed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25bf2  ldarg.3
0x25bf3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_createdby()
0x25bf8  ldc.i4.0
0x25bf9  ldc.i4.0
0x25bfa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25bff  ldarg.0
0x25c00  ldstr    aCreatedon// "createdon"
0x25c05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25c0a  ldarg.3
0x25c0b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_createdon()
0x25c10  ldc.i4.0
0x25c11  ldc.i4.0
0x25c12  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x25c17  ldarg.0
0x25c18  ldstr    aCustomerid// "customerid"
0x25c1d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25c22  ldarg.3
0x25c23  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_customerid()
0x25c28  ldc.i4.0
0x25c29  ldc.i4.0
0x25c2a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write124_Customer(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer o, bool isNullable, bool needType)
0x25c2f  ldarg.0
0x25c30  ldstr    aCustomersatisf// "customersatisfactioncode"
0x25c35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25c3a  ldarg.3
0x25c3b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_customersatisfactioncode()
0x25c40  ldc.i4.0
0x25c41  ldc.i4.0
0x25c42  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x25c47  ldarg.0
0x25c48  ldstr    aDescription_0// "description"
0x25c4d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25c52  ldarg.3
0x25c53  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_description()
0x25c58  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x25c5d  ldarg.0
0x25c5e  ldstr    aFollowupby// "followupby"
0x25c63  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25c68  ldarg.3
0x25c69  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_followupby()
0x25c6e  ldc.i4.0
0x25c6f  ldc.i4.0
0x25c70  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x25c75  ldarg.0
0x25c76  ldstr    aImportsequence// "importsequencenumber"
0x25c7b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25c80  ldarg.3
0x25c81  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_importsequencenumber()
0x25c86  ldc.i4.0
0x25c87  ldc.i4.0
0x25c88  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x25c8d  ldarg.0
0x25c8e  ldstr    aIncidentid// "incidentid"
0x25c93  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25c98  ldarg.3
0x25c99  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_incidentid()
0x25c9e  ldc.i4.0
0x25c9f  ldc.i4.0
0x25ca0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x25ca5  ldarg.0
0x25ca6  ldstr    aIncidentstagec// "incidentstagecode"
0x25cab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25cb0  ldarg.3
0x25cb1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_incidentstagecode()
0x25cb6  ldc.i4.0
0x25cb7  ldc.i4.0
0x25cb8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x25cbd  ldarg.0
0x25cbe  ldstr    aIsdecrementing// "isdecrementing"
0x25cc3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25cc8  ldarg.3
0x25cc9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_isdecrementing()
0x25cce  ldc.i4.0
0x25ccf  ldc.i4.0
0x25cd0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x25cd5  ldarg.0
0x25cd6  ldstr    aKbarticleid// "kbarticleid"
0x25cdb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25ce0  ldarg.3
0x25ce1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_kbarticleid()
0x25ce6  ldc.i4.0
0x25ce7  ldc.i4.0
0x25ce8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25ced  ldarg.0
0x25cee  ldstr    aModifiedby// "modifiedby"
0x25cf3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25cf8  ldarg.3
0x25cf9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_modifiedby()
0x25cfe  ldc.i4.0
0x25cff  ldc.i4.0
0x25d00  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25d05  ldarg.0
0x25d06  ldstr    aModifiedon// "modifiedon"
0x25d0b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25d10  ldarg.3
0x25d11  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_modifiedon()
0x25d16  ldc.i4.0
0x25d17  ldc.i4.0
0x25d18  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x25d1d  ldarg.0
0x25d1e  ldstr    aOverriddencrea// "overriddencreatedon"
0x25d23  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25d28  ldarg.3
0x25d29  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_overriddencreatedon()
0x25d2e  ldc.i4.0
0x25d2f  ldc.i4.0
0x25d30  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x25d35  ldarg.0
0x25d36  ldstr    aOwnerid// "ownerid"
0x25d3b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25d40  ldarg.3
0x25d41  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_ownerid()
0x25d46  ldc.i4.0
0x25d47  ldc.i4.0
0x25d48  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x25d4d  ldarg.0
0x25d4e  ldstr    aOwningbusiness// "owningbusinessunit"
0x25d53  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25d58  ldarg.3
0x25d59  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_owningbusinessunit()
0x25d5e  ldc.i4.0
0x25d5f  ldc.i4.0
0x25d60  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25d65  ldarg.0
0x25d66  ldstr    aPrioritycode// "prioritycode"
0x25d6b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25d70  ldarg.3
0x25d71  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_prioritycode()
0x25d76  ldc.i4.0
0x25d77  ldc.i4.0
0x25d78  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x25d7d  ldarg.0
0x25d7e  ldstr    aProductid// "productid"
0x25d83  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25d88  ldarg.3
0x25d89  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_productid()
0x25d8e  ldc.i4.0
0x25d8f  ldc.i4.0
0x25d90  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25d95  ldarg.0
0x25d96  ldstr    aProductserialn// "productserialnumber"
0x25d9b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25da0  ldarg.3
0x25da1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_productserialnumber()
0x25da6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x25dab  ldarg.0
0x25dac  ldstr    aResponsiblecon// "responsiblecontactid"
0x25db1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25db6  ldarg.3
0x25db7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_responsiblecontactid()
0x25dbc  ldc.i4.0
0x25dbd  ldc.i4.0
0x25dbe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25dc3  ldarg.0
0x25dc4  ldstr    aSeveritycode// "severitycode"
0x25dc9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25dce  ldarg.3
0x25dcf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_severitycode()
0x25dd4  ldc.i4.0
0x25dd5  ldc.i4.0
0x25dd6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x25ddb  ldarg.0
0x25ddc  ldstr    aStatecode// "statecode"
0x25de1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25de6  ldarg.3
0x25de7  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.IncidentStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_statecode()
0x25dec  ldc.i4.0
0x25ded  ldc.i4.0
0x25dee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write342_IncidentStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.IncidentStateInfo o, bool isNullable, bool needType)
0x25df3  ldarg.0
0x25df4  ldstr    aStatuscode// "statuscode"
0x25df9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25dfe  ldarg.3
0x25dff  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_statuscode()
0x25e04  ldc.i4.0
0x25e05  ldc.i4.0
0x25e06  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x25e0b  ldarg.0
0x25e0c  ldstr    aSubjectid// "subjectid"
0x25e11  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25e16  ldarg.3
0x25e17  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_subjectid()
0x25e1c  ldc.i4.0
0x25e1d  ldc.i4.0
0x25e1e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25e23  ldarg.0
0x25e24  ldstr    aTicketnumber// "ticketnumber"
0x25e29  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25e2e  ldarg.3
0x25e2f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_ticketnumber()
0x25e34  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x25e39  ldarg.0
0x25e3a  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x25e3f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25e44  ldarg.3
0x25e45  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_timezoneruleversionnumber()
0x25e4a  ldc.i4.0
0x25e4b  ldc.i4.0
0x25e4c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x25e51  ldarg.0
0x25e52  ldstr    aTitle// "title"
0x25e57  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25e5c  ldarg.3
0x25e5d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.incident::get_title()
0x25e62  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x25e67  ldarg.0
  ... truncated ...
```
