# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write380_duplicaterule

- ea: `0x27c30`
- end: `0x27e5b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write380_duplicaterule`
- size: `555`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37630`
- `0x56ac0`
- `0x58850`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x27c30`
- `0x27e60`

## string_xrefs

- `0x27c75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27c85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27c9b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27cb1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27cc9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27ce1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27cf9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27d0f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27d27`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27d3f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27d55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27d6b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27d83`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27d9b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27db3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27dc9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27de1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27df9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27e11`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27e29`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27e41`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27cc4`: `createdby`
- `0x27cdc`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x27c30  ldarg.3
0x27c31  brtrue.s loc_27C40
0x27c33  ldarg.s  4
0x27c35  brfalse.s loc_27C3F
0x27c37  ldarg.0
0x27c38  ldarg.1
0x27c39  ldarg.2
0x27c3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x27c3f  ret
0x27c40  ldarg.s  5
0x27c42  brtrue.s loc_27C60
0x27c44  ldarg.3
0x27c45  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x27c4a  stloc.0
0x27c4b  ldloc.0
0x27c4c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule
0x27c51  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27c56  beq.s    loc_27C60
0x27c58  ldarg.0
0x27c59  ldarg.3
0x27c5a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x27c5f  throw
0x27c60  ldarg.0
0x27c61  ldarg.1
0x27c62  ldarg.2
0x27c63  ldarg.3
0x27c64  ldc.i4.0
0x27c65  ldnull
0x27c66  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x27c6b  ldarg.s  5
0x27c6d  brfalse.s loc_27C7F
0x27c6f  ldarg.0
0x27c70  ldstr    aDuplicaterule// "duplicaterule"
0x27c75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27c7a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x27c7f  ldarg.0
0x27c80  ldstr    aBaseentitymatc// "baseentitymatchcodetable"
0x27c85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27c8a  ldarg.3
0x27c8b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_baseentitymatchcodetable()
0x27c90  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27c95  ldarg.0
0x27c96  ldstr    aBaseentityname// "baseentityname"
0x27c9b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27ca0  ldarg.3
0x27ca1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_baseentityname()
0x27ca6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27cab  ldarg.0
0x27cac  ldstr    aBaseentitytype// "baseentitytypecode"
0x27cb1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27cb6  ldarg.3
0x27cb7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_baseentitytypecode()
0x27cbc  ldc.i4.0
0x27cbd  ldc.i4.0
0x27cbe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x27cc3  ldarg.0
0x27cc4  ldstr    aCreatedby// "createdby"
0x27cc9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27cce  ldarg.3
0x27ccf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_createdby()
0x27cd4  ldc.i4.0
0x27cd5  ldc.i4.0
0x27cd6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x27cdb  ldarg.0
0x27cdc  ldstr    aCreatedon// "createdon"
0x27ce1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27ce6  ldarg.3
0x27ce7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_createdon()
0x27cec  ldc.i4.0
0x27ced  ldc.i4.0
0x27cee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x27cf3  ldarg.0
0x27cf4  ldstr    aDescription_0// "description"
0x27cf9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27cfe  ldarg.3
0x27cff  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_description()
0x27d04  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27d09  ldarg.0
0x27d0a  ldstr    aDuplicaterulei// "duplicateruleid"
0x27d0f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27d14  ldarg.3
0x27d15  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_duplicateruleid()
0x27d1a  ldc.i4.0
0x27d1b  ldc.i4.0
0x27d1c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x27d21  ldarg.0
0x27d22  ldstr    aIscasesensitiv// "iscasesensitive"
0x27d27  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27d2c  ldarg.3
0x27d2d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_iscasesensitive()
0x27d32  ldc.i4.0
0x27d33  ldc.i4.0
0x27d34  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x27d39  ldarg.0
0x27d3a  ldstr    aMatchingentity// "matchingentitymatchcodetable"
0x27d3f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27d44  ldarg.3
0x27d45  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_matchingentitymatchcodetable()
0x27d4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27d4f  ldarg.0
0x27d50  ldstr    aMatchingentity_0// "matchingentityname"
0x27d55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27d5a  ldarg.3
0x27d5b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_matchingentityname()
0x27d60  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27d65  ldarg.0
0x27d66  ldstr    aMatchingentity_1// "matchingentitytypecode"
0x27d6b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27d70  ldarg.3
0x27d71  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_matchingentitytypecode()
0x27d76  ldc.i4.0
0x27d77  ldc.i4.0
0x27d78  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x27d7d  ldarg.0
0x27d7e  ldstr    aModifiedby// "modifiedby"
0x27d83  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27d88  ldarg.3
0x27d89  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_modifiedby()
0x27d8e  ldc.i4.0
0x27d8f  ldc.i4.0
0x27d90  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x27d95  ldarg.0
0x27d96  ldstr    aModifiedon// "modifiedon"
0x27d9b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27da0  ldarg.3
0x27da1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_modifiedon()
0x27da6  ldc.i4.0
0x27da7  ldc.i4.0
0x27da8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x27dad  ldarg.0
0x27dae  ldstr    aName// "name"
0x27db3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27db8  ldarg.3
0x27db9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_name()
0x27dbe  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27dc3  ldarg.0
0x27dc4  ldstr    aOwnerid// "ownerid"
0x27dc9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27dce  ldarg.3
0x27dcf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_ownerid()
0x27dd4  ldc.i4.0
0x27dd5  ldc.i4.0
0x27dd6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x27ddb  ldarg.0
0x27ddc  ldstr    aOwningbusiness// "owningbusinessunit"
0x27de1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27de6  ldarg.3
0x27de7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_owningbusinessunit()
0x27dec  ldc.i4.0
0x27ded  ldc.i4.0
0x27dee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x27df3  ldarg.0
0x27df4  ldstr    aStatecode// "statecode"
0x27df9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27dfe  ldarg.3
0x27dff  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DuplicateRuleStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_statecode()
0x27e04  ldc.i4.0
0x27e05  ldc.i4.0
0x27e06  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write379_DuplicateRuleStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DuplicateRuleStateInfo o, bool isNullable, bool needType)
0x27e0b  ldarg.0
0x27e0c  ldstr    aStatuscode// "statuscode"
0x27e11  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27e16  ldarg.3
0x27e17  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_statuscode()
0x27e1c  ldc.i4.0
0x27e1d  ldc.i4.0
0x27e1e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x27e23  ldarg.0
0x27e24  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x27e29  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27e2e  ldarg.3
0x27e2f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_timezoneruleversionnumber()
0x27e34  ldc.i4.0
0x27e35  ldc.i4.0
0x27e36  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x27e3b  ldarg.0
0x27e3c  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x27e41  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27e46  ldarg.3
0x27e47  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterule::get_utcconversiontimezonecode()
0x27e4c  ldc.i4.0
0x27e4d  ldc.i4.0
0x27e4e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x27e53  ldarg.0
0x27e54  ldarg.3
0x27e55  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x27e5a  ret
```
