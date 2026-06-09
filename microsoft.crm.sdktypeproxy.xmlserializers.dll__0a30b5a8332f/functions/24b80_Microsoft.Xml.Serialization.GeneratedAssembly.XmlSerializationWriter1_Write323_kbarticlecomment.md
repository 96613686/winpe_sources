# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write323_kbarticlecomment

- ea: `0x24b80`
- end: `0x24cab`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write323_kbarticlecomment`
- size: `299`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36e50`
- `0x562e0`

## callees

- `0x5cf0`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x24b80`

## string_xrefs

- `0x24bc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24bd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24beb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24c03`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24c1b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24c33`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24c4b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24c63`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24c7b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24c93`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x24be6`: `createdby`
- `0x24bfe`: `createdon`
- `0x24bc0`: `kbarticlecomment`
- `0x24bd0`: `commenttext`
- `0x24c16`: `kbarticlecommentid`

## pseudocode

```c

```

## disassembly

```asm
0x24b80  ldarg.3
0x24b81  brtrue.s loc_24B90
0x24b83  ldarg.s  4
0x24b85  brfalse.s loc_24B8F
0x24b87  ldarg.0
0x24b88  ldarg.1
0x24b89  ldarg.2
0x24b8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x24b8f  ret
0x24b90  ldarg.s  5
0x24b92  brtrue.s loc_24BB0
0x24b94  ldarg.3
0x24b95  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x24b9a  stloc.0
0x24b9b  ldloc.0
0x24b9c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticlecomment
0x24ba1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24ba6  beq.s    loc_24BB0
0x24ba8  ldarg.0
0x24ba9  ldarg.3
0x24baa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x24baf  throw
0x24bb0  ldarg.0
0x24bb1  ldarg.1
0x24bb2  ldarg.2
0x24bb3  ldarg.3
0x24bb4  ldc.i4.0
0x24bb5  ldnull
0x24bb6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x24bbb  ldarg.s  5
0x24bbd  brfalse.s loc_24BCF
0x24bbf  ldarg.0
0x24bc0  ldstr    aKbarticlecomme// "kbarticlecomment"
0x24bc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24bca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x24bcf  ldarg.0
0x24bd0  ldstr    aCommenttext// "commenttext"
0x24bd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24bda  ldarg.3
0x24bdb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticlecomment::get_commenttext()
0x24be0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24be5  ldarg.0
0x24be6  ldstr    aCreatedby// "createdby"
0x24beb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24bf0  ldarg.3
0x24bf1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticlecomment::get_createdby()
0x24bf6  ldc.i4.0
0x24bf7  ldc.i4.0
0x24bf8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24bfd  ldarg.0
0x24bfe  ldstr    aCreatedon// "createdon"
0x24c03  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24c08  ldarg.3
0x24c09  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticlecomment::get_createdon()
0x24c0e  ldc.i4.0
0x24c0f  ldc.i4.0
0x24c10  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x24c15  ldarg.0
0x24c16  ldstr    aKbarticlecomme_0// "kbarticlecommentid"
0x24c1b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24c20  ldarg.3
0x24c21  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticlecomment::get_kbarticlecommentid()
0x24c26  ldc.i4.0
0x24c27  ldc.i4.0
0x24c28  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x24c2d  ldarg.0
0x24c2e  ldstr    aKbarticleid// "kbarticleid"
0x24c33  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24c38  ldarg.3
0x24c39  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticlecomment::get_kbarticleid()
0x24c3e  ldc.i4.0
0x24c3f  ldc.i4.0
0x24c40  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24c45  ldarg.0
0x24c46  ldstr    aModifiedby// "modifiedby"
0x24c4b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24c50  ldarg.3
0x24c51  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticlecomment::get_modifiedby()
0x24c56  ldc.i4.0
0x24c57  ldc.i4.0
0x24c58  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x24c5d  ldarg.0
0x24c5e  ldstr    aModifiedon// "modifiedon"
0x24c63  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24c68  ldarg.3
0x24c69  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticlecomment::get_modifiedon()
0x24c6e  ldc.i4.0
0x24c6f  ldc.i4.0
0x24c70  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x24c75  ldarg.0
0x24c76  ldstr    aOrganizationid// "organizationid"
0x24c7b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24c80  ldarg.3
0x24c81  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticlecomment::get_organizationid()
0x24c86  ldc.i4.0
0x24c87  ldc.i4.0
0x24c88  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x24c8d  ldarg.0
0x24c8e  ldstr    aTitle// "title"
0x24c93  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x24c98  ldarg.3
0x24c99  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.kbarticlecomment::get_title()
0x24c9e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x24ca3  ldarg.0
0x24ca4  ldarg.3
0x24ca5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x24caa  ret
```
