# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write251_relationshiprole

- ea: `0x1efc0`
- end: `0x1f11b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write251_relationshiprole`
- size: `347`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x363d0`
- `0x55780`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x16cb0`
- `0x1efc0`
- `0x1f120`

## string_xrefs

- `0x1f005`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f015`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f02d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f045`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f05b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f073`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f08b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f0a3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f0b9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f0d1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f0e9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f101`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1f010`: `createdby`
- `0x1f028`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x1efc0  ldarg.3
0x1efc1  brtrue.s loc_1EFD0
0x1efc3  ldarg.s  4
0x1efc5  brfalse.s loc_1EFCF
0x1efc7  ldarg.0
0x1efc8  ldarg.1
0x1efc9  ldarg.2
0x1efca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1efcf  ret
0x1efd0  ldarg.s  5
0x1efd2  brtrue.s loc_1EFF0
0x1efd4  ldarg.3
0x1efd5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1efda  stloc.0
0x1efdb  ldloc.0
0x1efdc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole
0x1efe1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1efe6  beq.s    loc_1EFF0
0x1efe8  ldarg.0
0x1efe9  ldarg.3
0x1efea  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1efef  throw
0x1eff0  ldarg.0
0x1eff1  ldarg.1
0x1eff2  ldarg.2
0x1eff3  ldarg.3
0x1eff4  ldc.i4.0
0x1eff5  ldnull
0x1eff6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1effb  ldarg.s  5
0x1effd  brfalse.s loc_1F00F
0x1efff  ldarg.0
0x1f000  ldstr    aRelationshipro_0// "relationshiprole"
0x1f005  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f00a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1f00f  ldarg.0
0x1f010  ldstr    aCreatedby// "createdby"
0x1f015  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f01a  ldarg.3
0x1f01b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole::get_createdby()
0x1f020  ldc.i4.0
0x1f021  ldc.i4.0
0x1f022  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1f027  ldarg.0
0x1f028  ldstr    aCreatedon// "createdon"
0x1f02d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f032  ldarg.3
0x1f033  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole::get_createdon()
0x1f038  ldc.i4.0
0x1f039  ldc.i4.0
0x1f03a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1f03f  ldarg.0
0x1f040  ldstr    aDescription_0// "description"
0x1f045  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f04a  ldarg.3
0x1f04b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole::get_description()
0x1f050  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1f055  ldarg.0
0x1f056  ldstr    aImportsequence// "importsequencenumber"
0x1f05b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f060  ldarg.3
0x1f061  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole::get_importsequencenumber()
0x1f066  ldc.i4.0
0x1f067  ldc.i4.0
0x1f068  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1f06d  ldarg.0
0x1f06e  ldstr    aModifiedby// "modifiedby"
0x1f073  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f078  ldarg.3
0x1f079  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole::get_modifiedby()
0x1f07e  ldc.i4.0
0x1f07f  ldc.i4.0
0x1f080  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1f085  ldarg.0
0x1f086  ldstr    aModifiedon// "modifiedon"
0x1f08b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f090  ldarg.3
0x1f091  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole::get_modifiedon()
0x1f096  ldc.i4.0
0x1f097  ldc.i4.0
0x1f098  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1f09d  ldarg.0
0x1f09e  ldstr    aName// "name"
0x1f0a3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f0a8  ldarg.3
0x1f0a9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole::get_name()
0x1f0ae  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1f0b3  ldarg.0
0x1f0b4  ldstr    aOrganizationid// "organizationid"
0x1f0b9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f0be  ldarg.3
0x1f0bf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole::get_organizationid()
0x1f0c4  ldc.i4.0
0x1f0c5  ldc.i4.0
0x1f0c6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1f0cb  ldarg.0
0x1f0cc  ldstr    aRelationshipro_2// "relationshiproleid"
0x1f0d1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f0d6  ldarg.3
0x1f0d7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole::get_relationshiproleid()
0x1f0dc  ldc.i4.0
0x1f0dd  ldc.i4.0
0x1f0de  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1f0e3  ldarg.0
0x1f0e4  ldstr    aStatecode// "statecode"
0x1f0e9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f0ee  ldarg.3
0x1f0ef  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RelationshipRoleStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole::get_statecode()
0x1f0f4  ldc.i4.0
0x1f0f5  ldc.i4.0
0x1f0f6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write250_RelationshipRoleStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RelationshipRoleStateInfo o, bool isNullable, bool needType)
0x1f0fb  ldarg.0
0x1f0fc  ldstr    aStatuscode// "statuscode"
0x1f101  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1f106  ldarg.3
0x1f107  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.relationshiprole::get_statuscode()
0x1f10c  ldc.i4.0
0x1f10d  ldc.i4.0
0x1f10e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x1f113  ldarg.0
0x1f114  ldarg.3
0x1f115  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1f11a  ret
```
