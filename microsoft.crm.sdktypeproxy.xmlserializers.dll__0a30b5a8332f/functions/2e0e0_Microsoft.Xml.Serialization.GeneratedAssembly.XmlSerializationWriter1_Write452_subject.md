# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write452_subject

- ea: `0x2e0e0`
- end: `0x2e253`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write452_subject`
- size: `371`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x38120`
- `0x54ec0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x2e0e0`

## string_xrefs

- `0x2e125`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e135`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e14d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e165`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e17b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e193`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e1ab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e1c3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e1db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e1f3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e20b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e223`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e23b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e130`: `createdby`
- `0x2e148`: `createdon`
- `0x2e1ee`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x2e0e0  ldarg.3
0x2e0e1  brtrue.s loc_2E0F0
0x2e0e3  ldarg.s  4
0x2e0e5  brfalse.s loc_2E0EF
0x2e0e7  ldarg.0
0x2e0e8  ldarg.1
0x2e0e9  ldarg.2
0x2e0ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2e0ef  ret
0x2e0f0  ldarg.s  5
0x2e0f2  brtrue.s loc_2E110
0x2e0f4  ldarg.3
0x2e0f5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2e0fa  stloc.0
0x2e0fb  ldloc.0
0x2e0fc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject
0x2e101  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e106  beq.s    loc_2E110
0x2e108  ldarg.0
0x2e109  ldarg.3
0x2e10a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2e10f  throw
0x2e110  ldarg.0
0x2e111  ldarg.1
0x2e112  ldarg.2
0x2e113  ldarg.3
0x2e114  ldc.i4.0
0x2e115  ldnull
0x2e116  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2e11b  ldarg.s  5
0x2e11d  brfalse.s loc_2E12F
0x2e11f  ldarg.0
0x2e120  ldstr    aSubject// "subject"
0x2e125  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e12a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2e12f  ldarg.0
0x2e130  ldstr    aCreatedby// "createdby"
0x2e135  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e13a  ldarg.3
0x2e13b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_createdby()
0x2e140  ldc.i4.0
0x2e141  ldc.i4.0
0x2e142  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e147  ldarg.0
0x2e148  ldstr    aCreatedon// "createdon"
0x2e14d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e152  ldarg.3
0x2e153  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_createdon()
0x2e158  ldc.i4.0
0x2e159  ldc.i4.0
0x2e15a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e15f  ldarg.0
0x2e160  ldstr    aDescription_0// "description"
0x2e165  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e16a  ldarg.3
0x2e16b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_description()
0x2e170  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e175  ldarg.0
0x2e176  ldstr    aFeaturemask// "featuremask"
0x2e17b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e180  ldarg.3
0x2e181  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_featuremask()
0x2e186  ldc.i4.0
0x2e187  ldc.i4.0
0x2e188  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2e18d  ldarg.0
0x2e18e  ldstr    aImportsequence// "importsequencenumber"
0x2e193  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e198  ldarg.3
0x2e199  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_importsequencenumber()
0x2e19e  ldc.i4.0
0x2e19f  ldc.i4.0
0x2e1a0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2e1a5  ldarg.0
0x2e1a6  ldstr    aModifiedby// "modifiedby"
0x2e1ab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e1b0  ldarg.3
0x2e1b1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_modifiedby()
0x2e1b6  ldc.i4.0
0x2e1b7  ldc.i4.0
0x2e1b8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e1bd  ldarg.0
0x2e1be  ldstr    aModifiedon// "modifiedon"
0x2e1c3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e1c8  ldarg.3
0x2e1c9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_modifiedon()
0x2e1ce  ldc.i4.0
0x2e1cf  ldc.i4.0
0x2e1d0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e1d5  ldarg.0
0x2e1d6  ldstr    aOrganizationid// "organizationid"
0x2e1db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e1e0  ldarg.3
0x2e1e1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_organizationid()
0x2e1e6  ldc.i4.0
0x2e1e7  ldc.i4.0
0x2e1e8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e1ed  ldarg.0
0x2e1ee  ldstr    aOverriddencrea// "overriddencreatedon"
0x2e1f3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e1f8  ldarg.3
0x2e1f9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_overriddencreatedon()
0x2e1fe  ldc.i4.0
0x2e1ff  ldc.i4.0
0x2e200  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e205  ldarg.0
0x2e206  ldstr    aParentsubject// "parentsubject"
0x2e20b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e210  ldarg.3
0x2e211  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_parentsubject()
0x2e216  ldc.i4.0
0x2e217  ldc.i4.0
0x2e218  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e21d  ldarg.0
0x2e21e  ldstr    aSubjectid// "subjectid"
0x2e223  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e228  ldarg.3
0x2e229  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_subjectid()
0x2e22e  ldc.i4.0
0x2e22f  ldc.i4.0
0x2e230  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2e235  ldarg.0
0x2e236  ldstr    aTitle// "title"
0x2e23b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e240  ldarg.3
0x2e241  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.subject::get_title()
0x2e246  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e24b  ldarg.0
0x2e24c  ldarg.3
0x2e24d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2e252  ret
```
