# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write56_OneToManyMetadata

- ea: `0x311d0`
- end: `0x31405`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write56_OneToManyMetadata`
- size: `565`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1940`
- `0x6ac0`
- `0x30290`
- `0x304e0`
- `0x33be0`
- `0x688c0`

## callees

- `0x1420`
- `0x1890`
- `0x30af0`
- `0x30bf0`
- `0x30d40`
- `0x30e30`
- `0x30ec0`
- `0x30f10`
- `0x311d0`
- `0x31410`

## string_xrefs

- `0x31215`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31225`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3123d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31253`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3126b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31287`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3129f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x312bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x312d3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x312eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31303`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3131b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31333`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3134b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31361`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31377`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3138d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x313a3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x313bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x313d3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x313eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3129a`: `SecurityType`
- `0x312ce`: `CascadeDelete`

## pseudocode

```c

```

## disassembly

```asm
0x311d0  ldarg.3
0x311d1  brtrue.s loc_311E0
0x311d3  ldarg.s  4
0x311d5  brfalse.s loc_311DF
0x311d7  ldarg.0
0x311d8  ldarg.1
0x311d9  ldarg.2
0x311da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x311df  ret
0x311e0  ldarg.s  5
0x311e2  brtrue.s loc_31200
0x311e4  ldarg.3
0x311e5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x311ea  stloc.0
0x311eb  ldloc.0
0x311ec  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata
0x311f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x311f6  beq.s    loc_31200
0x311f8  ldarg.0
0x311f9  ldarg.3
0x311fa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x311ff  throw
0x31200  ldarg.0
0x31201  ldarg.1
0x31202  ldarg.2
0x31203  ldarg.3
0x31204  ldc.i4.0
0x31205  ldnull
0x31206  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3120b  ldarg.s  5
0x3120d  brfalse.s loc_3121F
0x3120f  ldarg.0
0x31210  ldstr    aOnetomanymetad// "OneToManyMetadata"
0x31215  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3121a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3121f  ldarg.0
0x31220  ldstr    aMetadataid// "MetadataId"
0x31225  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3122a  ldarg.3
0x3122b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x31230  ldc.i4.0
0x31231  ldc.i4.0
0x31232  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x31237  ldarg.0
0x31238  ldstr    aSchemaname// "SchemaName"
0x3123d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31242  ldarg.3
0x31243  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_SchemaName()
0x31248  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3124d  ldarg.0
0x3124e  ldstr    aIscustomrelati// "IsCustomRelationship"
0x31253  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31258  ldarg.3
0x31259  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_IsCustomRelationship()
0x3125e  ldc.i4.0
0x3125f  ldc.i4.0
0x31260  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x31265  ldarg.0
0x31266  ldstr    aRelationshipty// "RelationshipType"
0x3126b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31270  ldarg.0
0x31271  ldarg.3
0x31272  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityRelationshipType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_RelationshipType()
0x31277  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write46_EntityRelationshipType(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityRelationshipType v)
0x3127c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31281  ldarg.0
0x31282  ldstr    aIsvalidforadva// "IsValidForAdvancedFind"
0x31287  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3128c  ldarg.3
0x3128d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_IsValidForAdvancedFind()
0x31292  ldc.i4.0
0x31293  ldc.i4.0
0x31294  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x31299  ldarg.0
0x3129a  ldstr    aSecuritytype// "SecurityType"
0x3129f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x312a4  ldarg.0
0x312a5  ldarg.3
0x312a6  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityTypes [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.RelationshipMetadata::get_SecurityType()
0x312ab  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write47_SecurityTypes(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityTypes v)
0x312b0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x312b5  ldarg.0
0x312b6  ldstr    aCascadeassign// "CascadeAssign"
0x312bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x312c0  ldarg.3
0x312c1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_CascadeAssign()
0x312c6  ldc.i4.0
0x312c7  ldc.i4.0
0x312c8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write55_CrmCascadeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType o, bool isNullable, bool needType)
0x312cd  ldarg.0
0x312ce  ldstr    aCascadedelete// "CascadeDelete"
0x312d3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x312d8  ldarg.3
0x312d9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_CascadeDelete()
0x312de  ldc.i4.0
0x312df  ldc.i4.0
0x312e0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write55_CrmCascadeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType o, bool isNullable, bool needType)
0x312e5  ldarg.0
0x312e6  ldstr    aCascademerge// "CascadeMerge"
0x312eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x312f0  ldarg.3
0x312f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_CascadeMerge()
0x312f6  ldc.i4.0
0x312f7  ldc.i4.0
0x312f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write55_CrmCascadeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType o, bool isNullable, bool needType)
0x312fd  ldarg.0
0x312fe  ldstr    aCascadereparen// "CascadeReparent"
0x31303  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31308  ldarg.3
0x31309  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_CascadeReparent()
0x3130e  ldc.i4.0
0x3130f  ldc.i4.0
0x31310  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write55_CrmCascadeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType o, bool isNullable, bool needType)
0x31315  ldarg.0
0x31316  ldstr    aCascadeshare// "CascadeShare"
0x3131b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31320  ldarg.3
0x31321  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_CascadeShare()
0x31326  ldc.i4.0
0x31327  ldc.i4.0
0x31328  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write55_CrmCascadeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType o, bool isNullable, bool needType)
0x3132d  ldarg.0
0x3132e  ldstr    aCascadeunshare// "CascadeUnshare"
0x31333  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31338  ldarg.3
0x31339  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_CascadeUnshare()
0x3133e  ldc.i4.0
0x3133f  ldc.i4.0
0x31340  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write55_CrmCascadeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmCascadeType o, bool isNullable, bool needType)
0x31345  ldarg.0
0x31346  ldstr    aReferencedattr// "ReferencedAttribute"
0x3134b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31350  ldarg.3
0x31351  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_ReferencedAttribute()
0x31356  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3135b  ldarg.0
0x3135c  ldstr    aReferencedenti// "ReferencedEntity"
0x31361  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31366  ldarg.3
0x31367  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_ReferencedEntity()
0x3136c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31371  ldarg.0
0x31372  ldstr    aReferencingatt// "ReferencingAttribute"
0x31377  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3137c  ldarg.3
0x3137d  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_ReferencingAttribute()
0x31382  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31387  ldarg.0
0x31388  ldstr    aReferencingent// "ReferencingEntity"
0x3138d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31392  ldarg.3
0x31393  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_ReferencingEntity()
0x31398  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3139d  ldarg.0
0x3139e  ldstr    aAssociatedmenu// "AssociatedMenuBehavior"
0x313a3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x313a8  ldarg.3
0x313a9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuBehavior [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_AssociatedMenuBehavior()
0x313ae  ldc.i4.0
0x313af  ldc.i4.0
0x313b0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write49_CrmAssociatedMenuBehavior(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuBehavior o, bool isNullable, bool needType)
0x313b5  ldarg.0
0x313b6  ldstr    aAssociatedmenu_0// "AssociatedMenuGroup"
0x313bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x313c0  ldarg.3
0x313c1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuGroup [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_AssociatedMenuGroup()
0x313c6  ldc.i4.0
0x313c7  ldc.i4.0
0x313c8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write51_CrmAssociatedMenuGroup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAssociatedMenuGroup o, bool isNullable, bool needType)
0x313cd  ldarg.0
0x313ce  ldstr    aAssociatedmenu_1// "AssociatedMenuOrder"
0x313d3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x313d8  ldarg.3
0x313d9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_AssociatedMenuOrder()
0x313de  ldc.i4.0
0x313df  ldc.i4.0
0x313e0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x313e5  ldarg.0
0x313e6  ldstr    aAssociatedmenu_2// "AssociatedMenuLabel"
0x313eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x313f0  ldarg.3
0x313f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata::get_AssociatedMenuLabel()
0x313f6  ldc.i4.0
0x313f7  ldc.i4.0
0x313f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x313fd  ldarg.0
0x313fe  ldarg.3
0x313ff  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x31404  ret
```
