# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write472_uomschedule

- ea: `0x2efb0`
- end: `0x2f109`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write472_uomschedule`
- size: `345`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x384a0`
- `0x579a0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x2efb0`

## string_xrefs

- `0x2eff5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f005`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f01b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f033`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f04b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f061`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f079`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f091`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f0a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f0bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f0d7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f0ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f016`: `createdby`
- `0x2f02e`: `createdon`
- `0x2f0d2`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x2efb0  ldarg.3
0x2efb1  brtrue.s loc_2EFC0
0x2efb3  ldarg.s  4
0x2efb5  brfalse.s loc_2EFBF
0x2efb7  ldarg.0
0x2efb8  ldarg.1
0x2efb9  ldarg.2
0x2efba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2efbf  ret
0x2efc0  ldarg.s  5
0x2efc2  brtrue.s loc_2EFE0
0x2efc4  ldarg.3
0x2efc5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2efca  stloc.0
0x2efcb  ldloc.0
0x2efcc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule
0x2efd1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2efd6  beq.s    loc_2EFE0
0x2efd8  ldarg.0
0x2efd9  ldarg.3
0x2efda  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2efdf  throw
0x2efe0  ldarg.0
0x2efe1  ldarg.1
0x2efe2  ldarg.2
0x2efe3  ldarg.3
0x2efe4  ldc.i4.0
0x2efe5  ldnull
0x2efe6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2efeb  ldarg.s  5
0x2efed  brfalse.s loc_2EFFF
0x2efef  ldarg.0
0x2eff0  ldstr    aUomschedule// "uomschedule"
0x2eff5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2effa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2efff  ldarg.0
0x2f000  ldstr    aBaseuomname// "baseuomname"
0x2f005  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f00a  ldarg.3
0x2f00b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule::get_baseuomname()
0x2f010  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f015  ldarg.0
0x2f016  ldstr    aCreatedby// "createdby"
0x2f01b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f020  ldarg.3
0x2f021  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule::get_createdby()
0x2f026  ldc.i4.0
0x2f027  ldc.i4.0
0x2f028  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f02d  ldarg.0
0x2f02e  ldstr    aCreatedon// "createdon"
0x2f033  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f038  ldarg.3
0x2f039  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule::get_createdon()
0x2f03e  ldc.i4.0
0x2f03f  ldc.i4.0
0x2f040  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f045  ldarg.0
0x2f046  ldstr    aDescription_0// "description"
0x2f04b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f050  ldarg.3
0x2f051  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule::get_description()
0x2f056  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f05b  ldarg.0
0x2f05c  ldstr    aImportsequence// "importsequencenumber"
0x2f061  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f066  ldarg.3
0x2f067  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule::get_importsequencenumber()
0x2f06c  ldc.i4.0
0x2f06d  ldc.i4.0
0x2f06e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2f073  ldarg.0
0x2f074  ldstr    aModifiedby// "modifiedby"
0x2f079  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f07e  ldarg.3
0x2f07f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule::get_modifiedby()
0x2f084  ldc.i4.0
0x2f085  ldc.i4.0
0x2f086  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f08b  ldarg.0
0x2f08c  ldstr    aModifiedon// "modifiedon"
0x2f091  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f096  ldarg.3
0x2f097  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule::get_modifiedon()
0x2f09c  ldc.i4.0
0x2f09d  ldc.i4.0
0x2f09e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f0a3  ldarg.0
0x2f0a4  ldstr    aName// "name"
0x2f0a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f0ae  ldarg.3
0x2f0af  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule::get_name()
0x2f0b4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f0b9  ldarg.0
0x2f0ba  ldstr    aOrganizationid// "organizationid"
0x2f0bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f0c4  ldarg.3
0x2f0c5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule::get_organizationid()
0x2f0ca  ldc.i4.0
0x2f0cb  ldc.i4.0
0x2f0cc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f0d1  ldarg.0
0x2f0d2  ldstr    aOverriddencrea// "overriddencreatedon"
0x2f0d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f0dc  ldarg.3
0x2f0dd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule::get_overriddencreatedon()
0x2f0e2  ldc.i4.0
0x2f0e3  ldc.i4.0
0x2f0e4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f0e9  ldarg.0
0x2f0ea  ldstr    aUomscheduleid// "uomscheduleid"
0x2f0ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f0f4  ldarg.3
0x2f0f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uomschedule::get_uomscheduleid()
0x2f0fa  ldc.i4.0
0x2f0fb  ldc.i4.0
0x2f0fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2f101  ldarg.0
0x2f102  ldarg.3
0x2f103  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2f108  ret
```
