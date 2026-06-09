# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write217_sdkmessageprocessingstepimage

- ea: `0x1d050`
- end: `0x1d1ef`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write217_sdkmessageprocessingstepimage`
- size: `415`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35db0`
- `0x55160`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x1d050`

## string_xrefs

- `0x1d095`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d0a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d0bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d0d3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d0eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d103`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d119`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d131`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d147`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d15f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d177`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d18f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d1a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d1bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d1d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d0b6`: `createdby`
- `0x1d0ce`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x1d050  ldarg.3
0x1d051  brtrue.s loc_1D060
0x1d053  ldarg.s  4
0x1d055  brfalse.s loc_1D05F
0x1d057  ldarg.0
0x1d058  ldarg.1
0x1d059  ldarg.2
0x1d05a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1d05f  ret
0x1d060  ldarg.s  5
0x1d062  brtrue.s loc_1D080
0x1d064  ldarg.3
0x1d065  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1d06a  stloc.0
0x1d06b  ldloc.0
0x1d06c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage
0x1d071  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d076  beq.s    loc_1D080
0x1d078  ldarg.0
0x1d079  ldarg.3
0x1d07a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1d07f  throw
0x1d080  ldarg.0
0x1d081  ldarg.1
0x1d082  ldarg.2
0x1d083  ldarg.3
0x1d084  ldc.i4.0
0x1d085  ldnull
0x1d086  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1d08b  ldarg.s  5
0x1d08d  brfalse.s loc_1D09F
0x1d08f  ldarg.0
0x1d090  ldstr    aSdkmessageproc_3// "sdkmessageprocessingstepimage"
0x1d095  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d09a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1d09f  ldarg.0
0x1d0a0  ldstr    aAttributes_0// "attributes"
0x1d0a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d0aa  ldarg.3
0x1d0ab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_attributes()
0x1d0b0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d0b5  ldarg.0
0x1d0b6  ldstr    aCreatedby// "createdby"
0x1d0bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d0c0  ldarg.3
0x1d0c1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_createdby()
0x1d0c6  ldc.i4.0
0x1d0c7  ldc.i4.0
0x1d0c8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d0cd  ldarg.0
0x1d0ce  ldstr    aCreatedon// "createdon"
0x1d0d3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d0d8  ldarg.3
0x1d0d9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_createdon()
0x1d0de  ldc.i4.0
0x1d0df  ldc.i4.0
0x1d0e0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1d0e5  ldarg.0
0x1d0e6  ldstr    aCustomizationl// "customizationlevel"
0x1d0eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d0f0  ldarg.3
0x1d0f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_customizationlevel()
0x1d0f6  ldc.i4.0
0x1d0f7  ldc.i4.0
0x1d0f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1d0fd  ldarg.0
0x1d0fe  ldstr    aEntityalias_0// "entityalias"
0x1d103  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d108  ldarg.3
0x1d109  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_entityalias()
0x1d10e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d113  ldarg.0
0x1d114  ldstr    aImagetype_0// "imagetype"
0x1d119  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d11e  ldarg.3
0x1d11f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_imagetype()
0x1d124  ldc.i4.0
0x1d125  ldc.i4.0
0x1d126  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1d12b  ldarg.0
0x1d12c  ldstr    aMessagepropert_0// "messagepropertyname"
0x1d131  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d136  ldarg.3
0x1d137  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_messagepropertyname()
0x1d13c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d141  ldarg.0
0x1d142  ldstr    aModifiedby// "modifiedby"
0x1d147  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d14c  ldarg.3
0x1d14d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_modifiedby()
0x1d152  ldc.i4.0
0x1d153  ldc.i4.0
0x1d154  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d159  ldarg.0
0x1d15a  ldstr    aModifiedon// "modifiedon"
0x1d15f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d164  ldarg.3
0x1d165  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_modifiedon()
0x1d16a  ldc.i4.0
0x1d16b  ldc.i4.0
0x1d16c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1d171  ldarg.0
0x1d172  ldstr    aOrganizationid// "organizationid"
0x1d177  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d17c  ldarg.3
0x1d17d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_organizationid()
0x1d182  ldc.i4.0
0x1d183  ldc.i4.0
0x1d184  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d189  ldarg.0
0x1d18a  ldstr    aRelatedattribu// "relatedattributename"
0x1d18f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d194  ldarg.3
0x1d195  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_relatedattributename()
0x1d19a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d19f  ldarg.0
0x1d1a0  ldstr    aSdkmessageproc_7// "sdkmessageprocessingstepid"
0x1d1a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d1aa  ldarg.3
0x1d1ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_sdkmessageprocessingstepid()
0x1d1b0  ldc.i4.0
0x1d1b1  ldc.i4.0
0x1d1b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d1b7  ldarg.0
0x1d1b8  ldstr    aSdkmessageproc_8// "sdkmessageprocessingstepimageid"
0x1d1bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d1c2  ldarg.3
0x1d1c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_sdkmessageprocessingstepimageid()
0x1d1c8  ldc.i4.0
0x1d1c9  ldc.i4.0
0x1d1ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1d1cf  ldarg.0
0x1d1d0  ldstr    aSdkmessageproc_9// "sdkmessageprocessingstepimageidunique"
0x1d1d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d1da  ldarg.3
0x1d1db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstepimage::get_sdkmessageprocessingstepimageidunique()
0x1d1e0  ldc.i4.0
0x1d1e1  ldc.i4.0
0x1d1e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1d1e7  ldarg.0
0x1d1e8  ldarg.3
0x1d1e9  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1d1ee  ret
```
