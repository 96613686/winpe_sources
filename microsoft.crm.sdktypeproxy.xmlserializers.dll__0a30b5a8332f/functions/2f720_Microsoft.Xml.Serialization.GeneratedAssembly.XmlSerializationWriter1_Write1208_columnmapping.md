# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1208_columnmapping

- ea: `0x2f720`
- end: `0x2f8a7`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1208_columnmapping`
- size: `391`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x57000`

## callees

- `0x5cf0`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16cb0`
- `0x2f720`
- `0x2f8b0`

## string_xrefs

- `0x2f765`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f775`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f78d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f7a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f7bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f7d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f7ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f805`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f81d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f833`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f849`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f861`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f879`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f88f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f788`: `createdby`
- `0x2f7a0`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x2f720  ldarg.3
0x2f721  brtrue.s loc_2F730
0x2f723  ldarg.s  4
0x2f725  brfalse.s loc_2F72F
0x2f727  ldarg.0
0x2f728  ldarg.1
0x2f729  ldarg.2
0x2f72a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2f72f  ret
0x2f730  ldarg.s  5
0x2f732  brtrue.s loc_2F750
0x2f734  ldarg.3
0x2f735  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2f73a  stloc.0
0x2f73b  ldloc.0
0x2f73c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping
0x2f741  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f746  beq.s    loc_2F750
0x2f748  ldarg.0
0x2f749  ldarg.3
0x2f74a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2f74f  throw
0x2f750  ldarg.0
0x2f751  ldarg.1
0x2f752  ldarg.2
0x2f753  ldarg.3
0x2f754  ldc.i4.0
0x2f755  ldnull
0x2f756  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2f75b  ldarg.s  5
0x2f75d  brfalse.s loc_2F76F
0x2f75f  ldarg.0
0x2f760  ldstr    aColumnmapping// "columnmapping"
0x2f765  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f76a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2f76f  ldarg.0
0x2f770  ldstr    aColumnmappingi// "columnmappingid"
0x2f775  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f77a  ldarg.3
0x2f77b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_columnmappingid()
0x2f780  ldc.i4.0
0x2f781  ldc.i4.0
0x2f782  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2f787  ldarg.0
0x2f788  ldstr    aCreatedby// "createdby"
0x2f78d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f792  ldarg.3
0x2f793  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_createdby()
0x2f798  ldc.i4.0
0x2f799  ldc.i4.0
0x2f79a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f79f  ldarg.0
0x2f7a0  ldstr    aCreatedon// "createdon"
0x2f7a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f7aa  ldarg.3
0x2f7ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_createdon()
0x2f7b0  ldc.i4.0
0x2f7b1  ldc.i4.0
0x2f7b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f7b7  ldarg.0
0x2f7b8  ldstr    aImportmapid// "importmapid"
0x2f7bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f7c2  ldarg.3
0x2f7c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_importmapid()
0x2f7c8  ldc.i4.0
0x2f7c9  ldc.i4.0
0x2f7ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f7cf  ldarg.0
0x2f7d0  ldstr    aModifiedby// "modifiedby"
0x2f7d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f7da  ldarg.3
0x2f7db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_modifiedby()
0x2f7e0  ldc.i4.0
0x2f7e1  ldc.i4.0
0x2f7e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f7e7  ldarg.0
0x2f7e8  ldstr    aModifiedon// "modifiedon"
0x2f7ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f7f2  ldarg.3
0x2f7f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_modifiedon()
0x2f7f8  ldc.i4.0
0x2f7f9  ldc.i4.0
0x2f7fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f7ff  ldarg.0
0x2f800  ldstr    aProcesscode// "processcode"
0x2f805  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f80a  ldarg.3
0x2f80b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_processcode()
0x2f810  ldc.i4.0
0x2f811  ldc.i4.0
0x2f812  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2f817  ldarg.0
0x2f818  ldstr    aSourceattribut// "sourceattributename"
0x2f81d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f822  ldarg.3
0x2f823  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_sourceattributename()
0x2f828  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f82d  ldarg.0
0x2f82e  ldstr    aSourceentityna// "sourceentityname"
0x2f833  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f838  ldarg.3
0x2f839  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_sourceentityname()
0x2f83e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f843  ldarg.0
0x2f844  ldstr    aStatecode// "statecode"
0x2f849  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f84e  ldarg.3
0x2f84f  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ColumnMappingStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_statecode()
0x2f854  ldc.i4.0
0x2f855  ldc.i4.0
0x2f856  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1207_ColumnMappingStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ColumnMappingStateInfo o, bool isNullable, bool needType)
0x2f85b  ldarg.0
0x2f85c  ldstr    aStatuscode// "statuscode"
0x2f861  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f866  ldarg.3
0x2f867  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_statuscode()
0x2f86c  ldc.i4.0
0x2f86d  ldc.i4.0
0x2f86e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x2f873  ldarg.0
0x2f874  ldstr    aTargetattribut// "targetattributename"
0x2f879  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f87e  ldarg.3
0x2f87f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_targetattributename()
0x2f884  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f889  ldarg.0
0x2f88a  ldstr    aTargetentityna// "targetentityname"
0x2f88f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f894  ldarg.3
0x2f895  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.columnmapping::get_targetentityname()
0x2f89a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f89f  ldarg.0
0x2f8a0  ldarg.3
0x2f8a1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2f8a6  ret
```
