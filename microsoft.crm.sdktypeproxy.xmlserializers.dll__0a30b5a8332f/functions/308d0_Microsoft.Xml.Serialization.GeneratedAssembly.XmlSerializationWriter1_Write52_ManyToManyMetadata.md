# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write52_ManyToManyMetadata

- ea: `0x308d0`
- end: `0x30aeb`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write52_ManyToManyMetadata`
- size: `539`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1940`
- `0x6ac0`
- `0x30290`
- `0x304e0`
- `0x33be0`
- `0x68950`

## callees

- `0x1420`
- `0x1890`
- `0x308d0`
- `0x30af0`
- `0x30bf0`
- `0x30d40`
- `0x30e30`
- `0x30ec0`
- `0x30f10`

## string_xrefs

- `0x30915`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30925`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3093d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30953`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3096b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30987`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3099f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x309bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x309d1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x309e7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x309fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30a13`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30a29`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30a41`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30a59`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30a71`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30a89`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30aa1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30ab9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30ad1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3099a`: `SecurityType`

## pseudocode

```c

```

## disassembly

```asm
0x308d0  ldarg.3
0x308d1  brtrue.s loc_308E0
0x308d3  ldarg.s  4
0x308d5  brfalse.s loc_308DF
0x308d7  ldarg.0
0x308d8  ldarg.1
0x308d9  ldarg.2
0x308da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x308df  ret
0x308e0  ldarg.s  5
0x308e2  brtrue.s loc_30900
0x308e4  ldarg.3
0x308e5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x308ea  stloc.0
0x308eb  ldloc.0
0x308ec  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata
0x308f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x308f6  beq.s    loc_30900
0x308f8  ldarg.0
0x308f9  ldarg.3
0x308fa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x308ff  throw
0x30900  ldarg.0
0x30901  ldarg.1
0x30902  ldarg.2
0x30903  ldarg.3
0x30904  ldc.i4.0
0x30905  ldnull
0x30906  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3090b  ldarg.s  5
0x3090d  brfalse.s loc_3091F
0x3090f  ldarg.0
0x30910  ldstr    aManytomanymeta// "ManyToManyMetadata"
0x30915  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3091a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3091f  ldarg.0
0x30920  ldstr    aMetadataid// "MetadataId"
0x30925  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3092a  ldarg.3
0x3092b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x30930  ldc.i4.0
0x30931  ldc.i4.0
0x30932  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x30937  ldarg.0
0x30938  ldstr    aSchemaname// "SchemaName"
0x3093d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30942  ldarg.3
0x30943  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_SchemaName()
0x30948  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3094d  ldarg.0
0x3094e  ldstr    aIscustomrelati// "IsCustomRelationship"
0x30953  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30958  ldarg.3
0x30959  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_IsCustomRelationship()
0x3095e  ldc.i4.0
0x3095f  ldc.i4.0
0x30960  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x30965  ldarg.0
0x30966  ldstr    aRelationshipty// "RelationshipType"
0x3096b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30970  ldarg.0
0x30971  ldarg.3
0x30972  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityRelationshipType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_RelationshipType()
0x30977  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write46_EntityRelationshipType(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityRelationshipType v)
0x3097c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x30981  ldarg.0
0x30982  ldstr    aIsvalidforadva// "IsValidForAdvancedFind"
0x30987  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3098c  ldarg.3
0x3098d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_IsValidForAdvancedFind()
0x30992  ldc.i4.0
0x30993  ldc.i4.0
0x30994  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x30999  ldarg.0
0x3099a  ldstr    aSecuritytype// "SecurityType"
0x3099f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x309a4  ldarg.0
0x309a5  ldarg.3
0x309a6  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityTypes [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_SecurityType()
0x309ab  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write47_SecurityTypes(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityTypes v)
0x309b0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x309b5  ldarg.0
0x309b6  ldstr    aEntity1logical// "Entity1LogicalName"
0x309bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x309c0  ldarg.3
0x309c1  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity1LogicalName()
0x309c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x309cb  ldarg.0
0x309cc  ldstr    aEntity2logical// "Entity2LogicalName"
0x309d1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x309d6  ldarg.3
0x309d7  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity2LogicalName()
0x309dc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x309e1  ldarg.0
0x309e2  ldstr    aIntersectentit// "IntersectEntityName"
0x309e7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x309ec  ldarg.3
0x309ed  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_IntersectEntityName()
0x309f2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x309f7  ldarg.0
0x309f8  ldstr    aEntity1interse// "Entity1IntersectAttribute"
0x309fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30a02  ldarg.3
0x30a03  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity1IntersectAttribute()
0x30a08  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x30a0d  ldarg.0
0x30a0e  ldstr    aEntity2interse// "Entity2IntersectAttribute"
0x30a13  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30a18  ldarg.3
0x30a19  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity2IntersectAttribute()
0x30a1e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x30a23  ldarg.0
0x30a24  ldstr    aEntity1associa// "Entity1AssociatedMenuBehavior"
0x30a29  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30a2e  ldarg.3
0x30a2f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuBehavior [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity1AssociatedMenuBehavior()
0x30a34  ldc.i4.0
0x30a35  ldc.i4.0
0x30a36  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write49_CrmAssociatedMenuBehavior(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuBehavior o, bool isNullable, bool needType)
0x30a3b  ldarg.0
0x30a3c  ldstr    aEntity1associa_0// "Entity1AssociatedMenuLabel"
0x30a41  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30a46  ldarg.3
0x30a47  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity1AssociatedMenuLabel()
0x30a4c  ldc.i4.0
0x30a4d  ldc.i4.0
0x30a4e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x30a53  ldarg.0
0x30a54  ldstr    aEntity2associa// "Entity2AssociatedMenuBehavior"
0x30a59  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30a5e  ldarg.3
0x30a5f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuBehavior [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity2AssociatedMenuBehavior()
0x30a64  ldc.i4.0
0x30a65  ldc.i4.0
0x30a66  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write49_CrmAssociatedMenuBehavior(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuBehavior o, bool isNullable, bool needType)
0x30a6b  ldarg.0
0x30a6c  ldstr    aEntity2associa_0// "Entity2AssociatedMenuLabel"
0x30a71  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30a76  ldarg.3
0x30a77  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity2AssociatedMenuLabel()
0x30a7c  ldc.i4.0
0x30a7d  ldc.i4.0
0x30a7e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x30a83  ldarg.0
0x30a84  ldstr    aEntity1associa_1// "Entity1AssociatedMenuGroup"
0x30a89  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30a8e  ldarg.3
0x30a8f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuGroup [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity1AssociatedMenuGroup()
0x30a94  ldc.i4.0
0x30a95  ldc.i4.0
0x30a96  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write51_CrmAssociatedMenuGroup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuGroup o, bool isNullable, bool needType)
0x30a9b  ldarg.0
0x30a9c  ldstr    aEntity2associa_1// "Entity2AssociatedMenuGroup"
0x30aa1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30aa6  ldarg.3
0x30aa7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuGroup [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity2AssociatedMenuGroup()
0x30aac  ldc.i4.0
0x30aad  ldc.i4.0
0x30aae  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write51_CrmAssociatedMenuGroup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuGroup o, bool isNullable, bool needType)
0x30ab3  ldarg.0
0x30ab4  ldstr    aEntity1associa_2// "Entity1AssociatedMenuOrder"
0x30ab9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30abe  ldarg.3
0x30abf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity1AssociatedMenuOrder()
0x30ac4  ldc.i4.0
0x30ac5  ldc.i4.0
0x30ac6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x30acb  ldarg.0
0x30acc  ldstr    aEntity2associa_2// "Entity2AssociatedMenuOrder"
0x30ad1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30ad6  ldarg.3
0x30ad7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.ManyToManyMetadata::get_Entity2AssociatedMenuOrder()
0x30adc  ldc.i4.0
0x30add  ldc.i4.0
0x30ade  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x30ae3  ldarg.0
0x30ae4  ldarg.3
0x30ae5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x30aea  ret
```
