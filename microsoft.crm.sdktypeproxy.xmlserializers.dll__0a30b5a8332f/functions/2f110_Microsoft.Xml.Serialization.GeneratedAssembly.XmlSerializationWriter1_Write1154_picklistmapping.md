# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1154_picklistmapping

- ea: `0x2f110`
- end: `0x2f26d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1154_picklistmapping`
- size: `349`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x55c50`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16cb0`
- `0x2f110`
- `0x2f270`

## string_xrefs

- `0x2f155`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f165`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f17d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f195`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f1ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f1c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f1dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f1f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f20d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f223`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f23b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f253`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f178`: `createdby`
- `0x2f190`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x2f110  ldarg.3
0x2f111  brtrue.s loc_2F120
0x2f113  ldarg.s  4
0x2f115  brfalse.s loc_2F11F
0x2f117  ldarg.0
0x2f118  ldarg.1
0x2f119  ldarg.2
0x2f11a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2f11f  ret
0x2f120  ldarg.s  5
0x2f122  brtrue.s loc_2F140
0x2f124  ldarg.3
0x2f125  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2f12a  stloc.0
0x2f12b  ldloc.0
0x2f12c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping
0x2f131  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f136  beq.s    loc_2F140
0x2f138  ldarg.0
0x2f139  ldarg.3
0x2f13a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2f13f  throw
0x2f140  ldarg.0
0x2f141  ldarg.1
0x2f142  ldarg.2
0x2f143  ldarg.3
0x2f144  ldc.i4.0
0x2f145  ldnull
0x2f146  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2f14b  ldarg.s  5
0x2f14d  brfalse.s loc_2F15F
0x2f14f  ldarg.0
0x2f150  ldstr    aPicklistmappin_0// "picklistmapping"
0x2f155  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f15a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2f15f  ldarg.0
0x2f160  ldstr    aColumnmappingi// "columnmappingid"
0x2f165  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f16a  ldarg.3
0x2f16b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping::get_columnmappingid()
0x2f170  ldc.i4.0
0x2f171  ldc.i4.0
0x2f172  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f177  ldarg.0
0x2f178  ldstr    aCreatedby// "createdby"
0x2f17d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f182  ldarg.3
0x2f183  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping::get_createdby()
0x2f188  ldc.i4.0
0x2f189  ldc.i4.0
0x2f18a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f18f  ldarg.0
0x2f190  ldstr    aCreatedon// "createdon"
0x2f195  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f19a  ldarg.3
0x2f19b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping::get_createdon()
0x2f1a0  ldc.i4.0
0x2f1a1  ldc.i4.0
0x2f1a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f1a7  ldarg.0
0x2f1a8  ldstr    aModifiedby// "modifiedby"
0x2f1ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f1b2  ldarg.3
0x2f1b3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping::get_modifiedby()
0x2f1b8  ldc.i4.0
0x2f1b9  ldc.i4.0
0x2f1ba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f1bf  ldarg.0
0x2f1c0  ldstr    aModifiedon// "modifiedon"
0x2f1c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f1ca  ldarg.3
0x2f1cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping::get_modifiedon()
0x2f1d0  ldc.i4.0
0x2f1d1  ldc.i4.0
0x2f1d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f1d7  ldarg.0
0x2f1d8  ldstr    aPicklistmappin_1// "picklistmappingid"
0x2f1dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f1e2  ldarg.3
0x2f1e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping::get_picklistmappingid()
0x2f1e8  ldc.i4.0
0x2f1e9  ldc.i4.0
0x2f1ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2f1ef  ldarg.0
0x2f1f0  ldstr    aProcesscode// "processcode"
0x2f1f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f1fa  ldarg.3
0x2f1fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping::get_processcode()
0x2f200  ldc.i4.0
0x2f201  ldc.i4.0
0x2f202  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2f207  ldarg.0
0x2f208  ldstr    aSourcevalue// "sourcevalue"
0x2f20d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f212  ldarg.3
0x2f213  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping::get_sourcevalue()
0x2f218  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f21d  ldarg.0
0x2f21e  ldstr    aStatecode// "statecode"
0x2f223  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f228  ldarg.3
0x2f229  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PickListMappingStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping::get_statecode()
0x2f22e  ldc.i4.0
0x2f22f  ldc.i4.0
0x2f230  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1153_PickListMappingStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PickListMappingStateInfo o, bool isNullable, bool needType)
0x2f235  ldarg.0
0x2f236  ldstr    aStatuscode// "statuscode"
0x2f23b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f240  ldarg.3
0x2f241  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping::get_statuscode()
0x2f246  ldc.i4.0
0x2f247  ldc.i4.0
0x2f248  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x2f24d  ldarg.0
0x2f24e  ldstr    aTargetvalue// "targetvalue"
0x2f253  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f258  ldarg.3
0x2f259  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.picklistmapping::get_targetvalue()
0x2f25e  ldc.i4.0
0x2f25f  ldc.i4.0
0x2f260  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2f265  ldarg.0
0x2f266  ldarg.3
0x2f267  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2f26c  ret
```
