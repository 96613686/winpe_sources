# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1159_ownermapping

- ea: `0x2f2f0`
- end: `0x2f48f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1159_ownermapping`
- size: `415`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x55d30`

## callees

- `0x5cf0`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16cb0`
- `0x2f2f0`
- `0x2f490`

## string_xrefs

- `0x2f335`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f345`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f35d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f375`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f38d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f3a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f3bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f3d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f3ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f403`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f419`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f431`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f449`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f45f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f477`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f340`: `createdby`
- `0x2f358`: `createdon`
- `0x2f3fe`: `sourceuservalueforsourcecrmuserlink`
- `0x2f472`: `targetuservalueforsourcecrmuserlink`

## pseudocode

```c

```

## disassembly

```asm
0x2f2f0  ldarg.3
0x2f2f1  brtrue.s loc_2F300
0x2f2f3  ldarg.s  4
0x2f2f5  brfalse.s loc_2F2FF
0x2f2f7  ldarg.0
0x2f2f8  ldarg.1
0x2f2f9  ldarg.2
0x2f2fa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2f2ff  ret
0x2f300  ldarg.s  5
0x2f302  brtrue.s loc_2F320
0x2f304  ldarg.3
0x2f305  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2f30a  stloc.0
0x2f30b  ldloc.0
0x2f30c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping
0x2f311  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f316  beq.s    loc_2F320
0x2f318  ldarg.0
0x2f319  ldarg.3
0x2f31a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2f31f  throw
0x2f320  ldarg.0
0x2f321  ldarg.1
0x2f322  ldarg.2
0x2f323  ldarg.3
0x2f324  ldc.i4.0
0x2f325  ldnull
0x2f326  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2f32b  ldarg.s  5
0x2f32d  brfalse.s loc_2F33F
0x2f32f  ldarg.0
0x2f330  ldstr    aOwnermapping// "ownermapping"
0x2f335  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f33a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2f33f  ldarg.0
0x2f340  ldstr    aCreatedby// "createdby"
0x2f345  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f34a  ldarg.3
0x2f34b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_createdby()
0x2f350  ldc.i4.0
0x2f351  ldc.i4.0
0x2f352  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f357  ldarg.0
0x2f358  ldstr    aCreatedon// "createdon"
0x2f35d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f362  ldarg.3
0x2f363  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_createdon()
0x2f368  ldc.i4.0
0x2f369  ldc.i4.0
0x2f36a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f36f  ldarg.0
0x2f370  ldstr    aImportmapid// "importmapid"
0x2f375  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f37a  ldarg.3
0x2f37b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_importmapid()
0x2f380  ldc.i4.0
0x2f381  ldc.i4.0
0x2f382  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f387  ldarg.0
0x2f388  ldstr    aModifiedby// "modifiedby"
0x2f38d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f392  ldarg.3
0x2f393  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_modifiedby()
0x2f398  ldc.i4.0
0x2f399  ldc.i4.0
0x2f39a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f39f  ldarg.0
0x2f3a0  ldstr    aModifiedon// "modifiedon"
0x2f3a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f3aa  ldarg.3
0x2f3ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_modifiedon()
0x2f3b0  ldc.i4.0
0x2f3b1  ldc.i4.0
0x2f3b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f3b7  ldarg.0
0x2f3b8  ldstr    aOwnermappingid// "ownermappingid"
0x2f3bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f3c2  ldarg.3
0x2f3c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_ownermappingid()
0x2f3c8  ldc.i4.0
0x2f3c9  ldc.i4.0
0x2f3ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2f3cf  ldarg.0
0x2f3d0  ldstr    aProcesscode// "processcode"
0x2f3d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f3da  ldarg.3
0x2f3db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_processcode()
0x2f3e0  ldc.i4.0
0x2f3e1  ldc.i4.0
0x2f3e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2f3e7  ldarg.0
0x2f3e8  ldstr    aSourcesystemus// "sourcesystemusername"
0x2f3ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f3f2  ldarg.3
0x2f3f3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_sourcesystemusername()
0x2f3f8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f3fd  ldarg.0
0x2f3fe  ldstr    aSourceuservalu// "sourceuservalueforsourcecrmuserlink"
0x2f403  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f408  ldarg.3
0x2f409  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_sourceuservalueforsourcecrmuserlink()
0x2f40e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f413  ldarg.0
0x2f414  ldstr    aStatecode// "statecode"
0x2f419  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f41e  ldarg.3
0x2f41f  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.OwnerMappingStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_statecode()
0x2f424  ldc.i4.0
0x2f425  ldc.i4.0
0x2f426  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1158_OwnerMappingStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.OwnerMappingStateInfo o, bool isNullable, bool needType)
0x2f42b  ldarg.0
0x2f42c  ldstr    aStatuscode// "statuscode"
0x2f431  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f436  ldarg.3
0x2f437  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_statuscode()
0x2f43c  ldc.i4.0
0x2f43d  ldc.i4.0
0x2f43e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x2f443  ldarg.0
0x2f444  ldstr    aTargetsystemus// "targetsystemuserdomainname"
0x2f449  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f44e  ldarg.3
0x2f44f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_targetsystemuserdomainname()
0x2f454  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f459  ldarg.0
0x2f45a  ldstr    aTargetsystemus_0// "targetsystemuserid"
0x2f45f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f464  ldarg.3
0x2f465  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_targetsystemuserid()
0x2f46a  ldc.i4.0
0x2f46b  ldc.i4.0
0x2f46c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f471  ldarg.0
0x2f472  ldstr    aTargetuservalu// "targetuservalueforsourcecrmuserlink"
0x2f477  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f47c  ldarg.3
0x2f47d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ownermapping::get_targetuservalueforsourcecrmuserlink()
0x2f482  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f487  ldarg.0
0x2f488  ldarg.3
0x2f489  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2f48e  ret
```
