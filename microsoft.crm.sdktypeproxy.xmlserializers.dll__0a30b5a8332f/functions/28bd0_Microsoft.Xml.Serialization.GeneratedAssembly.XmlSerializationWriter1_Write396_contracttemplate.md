# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write396_contracttemplate

- ea: `0x28bd0`
- end: `0x28d9f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write396_contracttemplate`
- size: `463`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37940`
- `0x56d60`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x28bd0`

## string_xrefs

- `0x28c15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28c25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28c3b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28c53`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28c6b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28c83`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28c9b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28cb3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28ccb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28ce1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28cf7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28d0f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28d27`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28d3f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28d55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28d6d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28d85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28c96`: `createdby`
- `0x28cae`: `createdon`
- `0x28d68`: `overriddencreatedon`
- `0x28c10`: `contracttemplate`
- `0x28c66`: `contractservicelevelcode`
- `0x28c7e`: `contracttemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x28bd0  ldarg.3
0x28bd1  brtrue.s loc_28BE0
0x28bd3  ldarg.s  4
0x28bd5  brfalse.s loc_28BDF
0x28bd7  ldarg.0
0x28bd8  ldarg.1
0x28bd9  ldarg.2
0x28bda  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x28bdf  ret
0x28be0  ldarg.s  5
0x28be2  brtrue.s loc_28C00
0x28be4  ldarg.3
0x28be5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x28bea  stloc.0
0x28beb  ldloc.0
0x28bec  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate
0x28bf1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x28bf6  beq.s    loc_28C00
0x28bf8  ldarg.0
0x28bf9  ldarg.3
0x28bfa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x28bff  throw
0x28c00  ldarg.0
0x28c01  ldarg.1
0x28c02  ldarg.2
0x28c03  ldarg.3
0x28c04  ldc.i4.0
0x28c05  ldnull
0x28c06  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x28c0b  ldarg.s  5
0x28c0d  brfalse.s loc_28C1F
0x28c0f  ldarg.0
0x28c10  ldstr    aContracttempla// "contracttemplate"
0x28c15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28c1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x28c1f  ldarg.0
0x28c20  ldstr    aAbbreviation// "abbreviation"
0x28c25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28c2a  ldarg.3
0x28c2b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_abbreviation()
0x28c30  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28c35  ldarg.0
0x28c36  ldstr    aAllotmenttypec// "allotmenttypecode"
0x28c3b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28c40  ldarg.3
0x28c41  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_allotmenttypecode()
0x28c46  ldc.i4.0
0x28c47  ldc.i4.0
0x28c48  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x28c4d  ldarg.0
0x28c4e  ldstr    aBillingfrequen// "billingfrequencycode"
0x28c53  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28c58  ldarg.3
0x28c59  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_billingfrequencycode()
0x28c5e  ldc.i4.0
0x28c5f  ldc.i4.0
0x28c60  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x28c65  ldarg.0
0x28c66  ldstr    aContractservic// "contractservicelevelcode"
0x28c6b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28c70  ldarg.3
0x28c71  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_contractservicelevelcode()
0x28c76  ldc.i4.0
0x28c77  ldc.i4.0
0x28c78  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x28c7d  ldarg.0
0x28c7e  ldstr    aContracttempla_0// "contracttemplateid"
0x28c83  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28c88  ldarg.3
0x28c89  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_contracttemplateid()
0x28c8e  ldc.i4.0
0x28c8f  ldc.i4.0
0x28c90  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x28c95  ldarg.0
0x28c96  ldstr    aCreatedby// "createdby"
0x28c9b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28ca0  ldarg.3
0x28ca1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_createdby()
0x28ca6  ldc.i4.0
0x28ca7  ldc.i4.0
0x28ca8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28cad  ldarg.0
0x28cae  ldstr    aCreatedon// "createdon"
0x28cb3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28cb8  ldarg.3
0x28cb9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_createdon()
0x28cbe  ldc.i4.0
0x28cbf  ldc.i4.0
0x28cc0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28cc5  ldarg.0
0x28cc6  ldstr    aDescription_0// "description"
0x28ccb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28cd0  ldarg.3
0x28cd1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_description()
0x28cd6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28cdb  ldarg.0
0x28cdc  ldstr    aEffectivitycal// "effectivitycalendar"
0x28ce1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28ce6  ldarg.3
0x28ce7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_effectivitycalendar()
0x28cec  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28cf1  ldarg.0
0x28cf2  ldstr    aImportsequence// "importsequencenumber"
0x28cf7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28cfc  ldarg.3
0x28cfd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_importsequencenumber()
0x28d02  ldc.i4.0
0x28d03  ldc.i4.0
0x28d04  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x28d09  ldarg.0
0x28d0a  ldstr    aModifiedby// "modifiedby"
0x28d0f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28d14  ldarg.3
0x28d15  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_modifiedby()
0x28d1a  ldc.i4.0
0x28d1b  ldc.i4.0
0x28d1c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28d21  ldarg.0
0x28d22  ldstr    aModifiedon// "modifiedon"
0x28d27  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28d2c  ldarg.3
0x28d2d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_modifiedon()
0x28d32  ldc.i4.0
0x28d33  ldc.i4.0
0x28d34  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28d39  ldarg.0
0x28d3a  ldstr    aName// "name"
0x28d3f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28d44  ldarg.3
0x28d45  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_name()
0x28d4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28d4f  ldarg.0
0x28d50  ldstr    aOrganizationid// "organizationid"
0x28d55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28d5a  ldarg.3
0x28d5b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_organizationid()
0x28d60  ldc.i4.0
0x28d61  ldc.i4.0
0x28d62  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28d67  ldarg.0
0x28d68  ldstr    aOverriddencrea// "overriddencreatedon"
0x28d6d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28d72  ldarg.3
0x28d73  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_overriddencreatedon()
0x28d78  ldc.i4.0
0x28d79  ldc.i4.0
0x28d7a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28d7f  ldarg.0
0x28d80  ldstr    aUsediscountasp// "usediscountaspercentage"
0x28d85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28d8a  ldarg.3
0x28d8b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contracttemplate::get_usediscountaspercentage()
0x28d90  ldc.i4.0
0x28d91  ldc.i4.0
0x28d92  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x28d97  ldarg.0
0x28d98  ldarg.3
0x28d99  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x28d9e  ret
```
