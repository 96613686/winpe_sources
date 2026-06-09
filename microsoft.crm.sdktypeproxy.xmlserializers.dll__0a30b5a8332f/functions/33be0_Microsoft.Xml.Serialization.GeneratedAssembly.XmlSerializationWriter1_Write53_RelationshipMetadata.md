# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write53_RelationshipMetadata

- ea: `0x33be0`
- end: `0x33d0b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write53_RelationshipMetadata`
- size: `299`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1940`
- `0x30290`
- `0x68a90`
- `0x69930`

## callees

- `0x1890`
- `0x308d0`
- `0x30e30`
- `0x30ec0`
- `0x30f10`
- `0x311d0`
- `0x33be0`

## string_xrefs

- `0x33c63`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33c73`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33c8b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33ca1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33cb9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33cd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33ced`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33ce8`: `SecurityType`

## pseudocode

```c

```

## disassembly

```asm
0x33be0  ldarg.3
0x33be1  brtrue.s loc_33BF0
0x33be3  ldarg.s  4
0x33be5  brfalse.s loc_33BEF
0x33be7  ldarg.0
0x33be8  ldarg.1
0x33be9  ldarg.2
0x33bea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x33bef  ret
0x33bf0  ldarg.s  5
0x33bf2  brtrue.s loc_33C4E
0x33bf4  ldarg.3
0x33bf5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x33bfa  stloc.0
0x33bfb  ldloc.0
0x33bfc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata
0x33c01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33c06  beq.s    loc_33C4E
0x33c08  ldloc.0
0x33c09  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata
0x33c0e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33c13  bne.un.s loc_33C27
0x33c15  ldarg.0
0x33c16  ldarg.1
0x33c17  ldarg.2
0x33c18  ldarg.3
0x33c19  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata
0x33c1e  ldarg.s  4
0x33c20  ldc.i4.1
0x33c21  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write56_OneToManyMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata o, bool isNullable, bool needType)
0x33c26  ret
0x33c27  ldloc.0
0x33c28  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata
0x33c2d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33c32  bne.un.s loc_33C46
0x33c34  ldarg.0
0x33c35  ldarg.1
0x33c36  ldarg.2
0x33c37  ldarg.3
0x33c38  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata
0x33c3d  ldarg.s  4
0x33c3f  ldc.i4.1
0x33c40  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write52_ManyToManyMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata o, bool isNullable, bool needType)
0x33c45  ret
0x33c46  ldarg.0
0x33c47  ldarg.3
0x33c48  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x33c4d  throw
0x33c4e  ldarg.0
0x33c4f  ldarg.1
0x33c50  ldarg.2
0x33c51  ldarg.3
0x33c52  ldc.i4.0
0x33c53  ldnull
0x33c54  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x33c59  ldarg.s  5
0x33c5b  brfalse.s loc_33C6D
0x33c5d  ldarg.0
0x33c5e  ldstr    aRelationshipme// "RelationshipMetadata"
0x33c63  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33c68  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x33c6d  ldarg.0
0x33c6e  ldstr    aMetadataid// "MetadataId"
0x33c73  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33c78  ldarg.3
0x33c79  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x33c7e  ldc.i4.0
0x33c7f  ldc.i4.0
0x33c80  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x33c85  ldarg.0
0x33c86  ldstr    aSchemaname// "SchemaName"
0x33c8b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33c90  ldarg.3
0x33c91  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_SchemaName()
0x33c96  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33c9b  ldarg.0
0x33c9c  ldstr    aIscustomrelati// "IsCustomRelationship"
0x33ca1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33ca6  ldarg.3
0x33ca7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_IsCustomRelationship()
0x33cac  ldc.i4.0
0x33cad  ldc.i4.0
0x33cae  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33cb3  ldarg.0
0x33cb4  ldstr    aRelationshipty// "RelationshipType"
0x33cb9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33cbe  ldarg.0
0x33cbf  ldarg.3
0x33cc0  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityRelationshipType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_RelationshipType()
0x33cc5  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write46_EntityRelationshipType(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityRelationshipType v)
0x33cca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33ccf  ldarg.0
0x33cd0  ldstr    aIsvalidforadva// "IsValidForAdvancedFind"
0x33cd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33cda  ldarg.3
0x33cdb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_IsValidForAdvancedFind()
0x33ce0  ldc.i4.0
0x33ce1  ldc.i4.0
0x33ce2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33ce7  ldarg.0
0x33ce8  ldstr    aSecuritytype// "SecurityType"
0x33ced  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33cf2  ldarg.0
0x33cf3  ldarg.3
0x33cf4  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityTypes [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_SecurityType()
0x33cf9  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write47_SecurityTypes(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityTypes v)
0x33cfe  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33d03  ldarg.0
0x33d04  ldarg.3
0x33d05  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x33d0a  ret
```
