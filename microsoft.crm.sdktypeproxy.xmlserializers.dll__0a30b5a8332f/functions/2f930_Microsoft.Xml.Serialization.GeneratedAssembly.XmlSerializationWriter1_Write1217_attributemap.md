# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1217_attributemap

- ea: `0x2f930`
- end: `0x2fa8b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1217_attributemap`
- size: `347`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x57380`

## callees

- `0x5cf0`
- `0x15020`
- `0x15180`
- `0x153c0`
- `0x2f930`

## string_xrefs

- `0x2f975`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f985`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f99d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f9b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f9cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f9e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f9fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fa15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fa2d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fa45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fa5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fa73`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f998`: `createdby`
- `0x2f9b0`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x2f930  ldarg.3
0x2f931  brtrue.s loc_2F940
0x2f933  ldarg.s  4
0x2f935  brfalse.s loc_2F93F
0x2f937  ldarg.0
0x2f938  ldarg.1
0x2f939  ldarg.2
0x2f93a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2f93f  ret
0x2f940  ldarg.s  5
0x2f942  brtrue.s loc_2F960
0x2f944  ldarg.3
0x2f945  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2f94a  stloc.0
0x2f94b  ldloc.0
0x2f94c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap
0x2f951  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f956  beq.s    loc_2F960
0x2f958  ldarg.0
0x2f959  ldarg.3
0x2f95a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2f95f  throw
0x2f960  ldarg.0
0x2f961  ldarg.1
0x2f962  ldarg.2
0x2f963  ldarg.3
0x2f964  ldc.i4.0
0x2f965  ldnull
0x2f966  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2f96b  ldarg.s  5
0x2f96d  brfalse.s loc_2F97F
0x2f96f  ldarg.0
0x2f970  ldstr    aAttributemap// "attributemap"
0x2f975  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f97a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2f97f  ldarg.0
0x2f980  ldstr    aAttributemapid// "attributemapid"
0x2f985  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f98a  ldarg.3
0x2f98b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap::get_attributemapid()
0x2f990  ldc.i4.0
0x2f991  ldc.i4.0
0x2f992  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2f997  ldarg.0
0x2f998  ldstr    aCreatedby// "createdby"
0x2f99d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f9a2  ldarg.3
0x2f9a3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap::get_createdby()
0x2f9a8  ldc.i4.0
0x2f9a9  ldc.i4.0
0x2f9aa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f9af  ldarg.0
0x2f9b0  ldstr    aCreatedon// "createdon"
0x2f9b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f9ba  ldarg.3
0x2f9bb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap::get_createdon()
0x2f9c0  ldc.i4.0
0x2f9c1  ldc.i4.0
0x2f9c2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f9c7  ldarg.0
0x2f9c8  ldstr    aEntitymapid// "entitymapid"
0x2f9cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f9d2  ldarg.3
0x2f9d3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap::get_entitymapid()
0x2f9d8  ldc.i4.0
0x2f9d9  ldc.i4.0
0x2f9da  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f9df  ldarg.0
0x2f9e0  ldstr    aIssystem// "issystem"
0x2f9e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f9ea  ldarg.3
0x2f9eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap::get_issystem()
0x2f9f0  ldc.i4.0
0x2f9f1  ldc.i4.0
0x2f9f2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2f9f7  ldarg.0
0x2f9f8  ldstr    aModifiedby// "modifiedby"
0x2f9fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fa02  ldarg.3
0x2fa03  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap::get_modifiedby()
0x2fa08  ldc.i4.0
0x2fa09  ldc.i4.0
0x2fa0a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2fa0f  ldarg.0
0x2fa10  ldstr    aModifiedon// "modifiedon"
0x2fa15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fa1a  ldarg.3
0x2fa1b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap::get_modifiedon()
0x2fa20  ldc.i4.0
0x2fa21  ldc.i4.0
0x2fa22  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2fa27  ldarg.0
0x2fa28  ldstr    aOrganizationid// "organizationid"
0x2fa2d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fa32  ldarg.3
0x2fa33  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap::get_organizationid()
0x2fa38  ldc.i4.0
0x2fa39  ldc.i4.0
0x2fa3a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2fa3f  ldarg.0
0x2fa40  ldstr    aParentattribut// "parentattributemapid"
0x2fa45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fa4a  ldarg.3
0x2fa4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap::get_parentattributemapid()
0x2fa50  ldc.i4.0
0x2fa51  ldc.i4.0
0x2fa52  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2fa57  ldarg.0
0x2fa58  ldstr    aSourceattribut// "sourceattributename"
0x2fa5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fa62  ldarg.3
0x2fa63  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap::get_sourceattributename()
0x2fa68  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2fa6d  ldarg.0
0x2fa6e  ldstr    aTargetattribut// "targetattributename"
0x2fa73  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fa78  ldarg.3
0x2fa79  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.attributemap::get_targetattributename()
0x2fa7e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2fa83  ldarg.0
0x2fa84  ldarg.3
0x2fa85  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2fa8a  ret
```
