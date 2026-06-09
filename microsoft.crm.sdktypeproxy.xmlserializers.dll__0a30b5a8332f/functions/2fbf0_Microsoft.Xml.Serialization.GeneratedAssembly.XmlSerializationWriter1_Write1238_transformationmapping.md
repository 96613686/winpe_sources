# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1238_transformationmapping

- ea: `0x2fbf0`
- end: `0x2fd61`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1238_transformationmapping`
- size: `369`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x57af0`

## callees

- `0x5cf0`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16cb0`
- `0x2fbf0`
- `0x2fd70`

## string_xrefs

- `0x2fc35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fc45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fc5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fc75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fc8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fca5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fcbd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fcd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fceb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fd03`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fd1b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fd31`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fd49`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fc40`: `createdby`
- `0x2fc58`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x2fbf0  ldarg.3
0x2fbf1  brtrue.s loc_2FC00
0x2fbf3  ldarg.s  4
0x2fbf5  brfalse.s loc_2FBFF
0x2fbf7  ldarg.0
0x2fbf8  ldarg.1
0x2fbf9  ldarg.2
0x2fbfa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2fbff  ret
0x2fc00  ldarg.s  5
0x2fc02  brtrue.s loc_2FC20
0x2fc04  ldarg.3
0x2fc05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2fc0a  stloc.0
0x2fc0b  ldloc.0
0x2fc0c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping
0x2fc11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fc16  beq.s    loc_2FC20
0x2fc18  ldarg.0
0x2fc19  ldarg.3
0x2fc1a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2fc1f  throw
0x2fc20  ldarg.0
0x2fc21  ldarg.1
0x2fc22  ldarg.2
0x2fc23  ldarg.3
0x2fc24  ldc.i4.0
0x2fc25  ldnull
0x2fc26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2fc2b  ldarg.s  5
0x2fc2d  brfalse.s loc_2FC3F
0x2fc2f  ldarg.0
0x2fc30  ldstr    aTransformation_0// "transformationmapping"
0x2fc35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fc3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2fc3f  ldarg.0
0x2fc40  ldstr    aCreatedby// "createdby"
0x2fc45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fc4a  ldarg.3
0x2fc4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_createdby()
0x2fc50  ldc.i4.0
0x2fc51  ldc.i4.0
0x2fc52  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2fc57  ldarg.0
0x2fc58  ldstr    aCreatedon// "createdon"
0x2fc5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fc62  ldarg.3
0x2fc63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_createdon()
0x2fc68  ldc.i4.0
0x2fc69  ldc.i4.0
0x2fc6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2fc6f  ldarg.0
0x2fc70  ldstr    aImportmapid// "importmapid"
0x2fc75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fc7a  ldarg.3
0x2fc7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_importmapid()
0x2fc80  ldc.i4.0
0x2fc81  ldc.i4.0
0x2fc82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2fc87  ldarg.0
0x2fc88  ldstr    aModifiedby// "modifiedby"
0x2fc8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fc92  ldarg.3
0x2fc93  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_modifiedby()
0x2fc98  ldc.i4.0
0x2fc99  ldc.i4.0
0x2fc9a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2fc9f  ldarg.0
0x2fca0  ldstr    aModifiedon// "modifiedon"
0x2fca5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fcaa  ldarg.3
0x2fcab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_modifiedon()
0x2fcb0  ldc.i4.0
0x2fcb1  ldc.i4.0
0x2fcb2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2fcb7  ldarg.0
0x2fcb8  ldstr    aProcesscode// "processcode"
0x2fcbd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fcc2  ldarg.3
0x2fcc3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_processcode()
0x2fcc8  ldc.i4.0
0x2fcc9  ldc.i4.0
0x2fcca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2fccf  ldarg.0
0x2fcd0  ldstr    aSourceentityna// "sourceentityname"
0x2fcd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fcda  ldarg.3
0x2fcdb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_sourceentityname()
0x2fce0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2fce5  ldarg.0
0x2fce6  ldstr    aStatecode// "statecode"
0x2fceb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fcf0  ldarg.3
0x2fcf1  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TransformationMappingStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_statecode()
0x2fcf6  ldc.i4.0
0x2fcf7  ldc.i4.0
0x2fcf8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1237_TransformationMappingStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TransformationMappingStateInfo o, bool isNullable, bool needType)
0x2fcfd  ldarg.0
0x2fcfe  ldstr    aStatuscode// "statuscode"
0x2fd03  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fd08  ldarg.3
0x2fd09  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_statuscode()
0x2fd0e  ldc.i4.0
0x2fd0f  ldc.i4.0
0x2fd10  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x2fd15  ldarg.0
0x2fd16  ldstr    aTargetentityna// "targetentityname"
0x2fd1b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fd20  ldarg.3
0x2fd21  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_targetentityname()
0x2fd26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2fd2b  ldarg.0
0x2fd2c  ldstr    aTransformation_3// "transformationmappingid"
0x2fd31  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fd36  ldarg.3
0x2fd37  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_transformationmappingid()
0x2fd3c  ldc.i4.0
0x2fd3d  ldc.i4.0
0x2fd3e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2fd43  ldarg.0
0x2fd44  ldstr    aTransformation_4// "transformationtypename"
0x2fd49  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fd4e  ldarg.3
0x2fd4f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationmapping::get_transformationtypename()
0x2fd54  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2fd59  ldarg.0
0x2fd5a  ldarg.3
0x2fd5b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2fd60  ret
```
