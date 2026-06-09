# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write247_relationshiprolemap

- ea: `0x1ee90`
- end: `0x1efbf`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write247_relationshiprolemap`
- size: `303`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36360`
- `0x55710`

## callees

- `0x5cf0`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x167c0`
- `0x1ee90`

## string_xrefs

- `0x1eed5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eee5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eefd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ef15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ef2d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ef45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ef5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ef75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ef8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1efa5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1eef8`: `createdby`
- `0x1ef10`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x1ee90  ldarg.3
0x1ee91  brtrue.s loc_1EEA0
0x1ee93  ldarg.s  4
0x1ee95  brfalse.s loc_1EE9F
0x1ee97  ldarg.0
0x1ee98  ldarg.1
0x1ee99  ldarg.2
0x1ee9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1ee9f  ret
0x1eea0  ldarg.s  5
0x1eea2  brtrue.s loc_1EEC0
0x1eea4  ldarg.3
0x1eea5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1eeaa  stloc.0
0x1eeab  ldloc.0
0x1eeac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprolemap
0x1eeb1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1eeb6  beq.s    loc_1EEC0
0x1eeb8  ldarg.0
0x1eeb9  ldarg.3
0x1eeba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1eebf  throw
0x1eec0  ldarg.0
0x1eec1  ldarg.1
0x1eec2  ldarg.2
0x1eec3  ldarg.3
0x1eec4  ldc.i4.0
0x1eec5  ldnull
0x1eec6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1eecb  ldarg.s  5
0x1eecd  brfalse.s loc_1EEDF
0x1eecf  ldarg.0
0x1eed0  ldstr    aRelationshipro_1// "relationshiprolemap"
0x1eed5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1eeda  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1eedf  ldarg.0
0x1eee0  ldstr    aAssociateobjec// "associateobjecttypecode"
0x1eee5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1eeea  ldarg.3
0x1eeeb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprolemap::get_associateobjecttypecode()
0x1eef0  ldc.i4.0
0x1eef1  ldc.i4.0
0x1eef2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write135_EntityNameReference(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference o, bool isNullable, bool needType)
0x1eef7  ldarg.0
0x1eef8  ldstr    aCreatedby// "createdby"
0x1eefd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ef02  ldarg.3
0x1ef03  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprolemap::get_createdby()
0x1ef08  ldc.i4.0
0x1ef09  ldc.i4.0
0x1ef0a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ef0f  ldarg.0
0x1ef10  ldstr    aCreatedon// "createdon"
0x1ef15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ef1a  ldarg.3
0x1ef1b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprolemap::get_createdon()
0x1ef20  ldc.i4.0
0x1ef21  ldc.i4.0
0x1ef22  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ef27  ldarg.0
0x1ef28  ldstr    aModifiedby// "modifiedby"
0x1ef2d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ef32  ldarg.3
0x1ef33  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprolemap::get_modifiedby()
0x1ef38  ldc.i4.0
0x1ef39  ldc.i4.0
0x1ef3a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ef3f  ldarg.0
0x1ef40  ldstr    aModifiedon// "modifiedon"
0x1ef45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ef4a  ldarg.3
0x1ef4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprolemap::get_modifiedon()
0x1ef50  ldc.i4.0
0x1ef51  ldc.i4.0
0x1ef52  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ef57  ldarg.0
0x1ef58  ldstr    aOrganizationid// "organizationid"
0x1ef5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ef62  ldarg.3
0x1ef63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprolemap::get_organizationid()
0x1ef68  ldc.i4.0
0x1ef69  ldc.i4.0
0x1ef6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1ef6f  ldarg.0
0x1ef70  ldstr    aPrimaryobjectt// "primaryobjecttypecode"
0x1ef75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ef7a  ldarg.3
0x1ef7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprolemap::get_primaryobjecttypecode()
0x1ef80  ldc.i4.0
0x1ef81  ldc.i4.0
0x1ef82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write135_EntityNameReference(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference o, bool isNullable, bool needType)
0x1ef87  ldarg.0
0x1ef88  ldstr    aRelationshipro_2// "relationshiproleid"
0x1ef8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ef92  ldarg.3
0x1ef93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprolemap::get_relationshiproleid()
0x1ef98  ldc.i4.0
0x1ef99  ldc.i4.0
0x1ef9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ef9f  ldarg.0
0x1efa0  ldstr    aRelationshipro_3// "relationshiprolemapid"
0x1efa5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1efaa  ldarg.3
0x1efab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprolemap::get_relationshiprolemapid()
0x1efb0  ldc.i4.0
0x1efb1  ldc.i4.0
0x1efb2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1efb7  ldarg.0
0x1efb8  ldarg.3
0x1efb9  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1efbe  ret
```
