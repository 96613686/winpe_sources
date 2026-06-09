# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write60_EntityMetadata

- ea: `0x304e0`
- end: `0x308ce`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write60_EntityMetadata`
- size: `1006`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1100`
- `0x1940`
- `0x30290`
- `0x68510`
- `0x69630`

## callees

- `0x1420`
- `0x1890`
- `0x304e0`
- `0x308d0`
- `0x30bf0`
- `0x30f10`
- `0x30f80`
- `0x311d0`
- `0x31530`
- `0x33a90`

## string_xrefs

- `0x30525`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30535`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3054d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30563`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30579`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30591`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x305a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x305c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x305d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x305f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30609`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30621`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30639`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30651`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30669`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30681`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30699`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x306b1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x306c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x306df`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x306f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3070b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3072d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30743`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30772`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30789`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x307be`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x307d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3080c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30823`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3085a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30871`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3089c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x308b4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3081e`: `Privilege`
- `0x30807`: `Privileges`

## pseudocode

```c

```

## disassembly

```asm
0x304e0  ldarg.3
0x304e1  brtrue.s loc_304F0
0x304e3  ldarg.s  4
0x304e5  brfalse.s loc_304EF
0x304e7  ldarg.0
0x304e8  ldarg.1
0x304e9  ldarg.2
0x304ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x304ef  ret
0x304f0  ldarg.s  5
0x304f2  brtrue.s loc_30510
0x304f4  ldarg.3
0x304f5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x304fa  stloc.0
0x304fb  ldloc.0
0x304fc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata
0x30501  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x30506  beq.s    loc_30510
0x30508  ldarg.0
0x30509  ldarg.3
0x3050a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3050f  throw
0x30510  ldarg.0
0x30511  ldarg.1
0x30512  ldarg.2
0x30513  ldarg.3
0x30514  ldc.i4.0
0x30515  ldnull
0x30516  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3051b  ldarg.s  5
0x3051d  brfalse.s loc_3052F
0x3051f  ldarg.0
0x30520  ldstr    aEntitymetadata// "EntityMetadata"
0x30525  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3052a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3052f  ldarg.0
0x30530  ldstr    aMetadataid// "MetadataId"
0x30535  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3053a  ldarg.3
0x3053b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x30540  ldc.i4.0
0x30541  ldc.i4.0
0x30542  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x30547  ldarg.0
0x30548  ldstr    aSchemaname// "SchemaName"
0x3054d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30552  ldarg.3
0x30553  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_SchemaName()
0x30558  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3055d  ldarg.0
0x3055e  ldstr    aLogicalname// "LogicalName"
0x30563  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30568  ldarg.3
0x30569  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_LogicalName()
0x3056e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x30573  ldarg.0
0x30574  ldstr    aObjecttypecode// "ObjectTypeCode"
0x30579  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3057e  ldarg.3
0x3057f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_ObjectTypeCode()
0x30584  ldc.i4.0
0x30585  ldc.i4.0
0x30586  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x3058b  ldarg.0
0x3058c  ldstr    aDisplayname// "DisplayName"
0x30591  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30596  ldarg.3
0x30597  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_DisplayName()
0x3059c  ldc.i4.0
0x3059d  ldc.i4.0
0x3059e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x305a3  ldarg.0
0x305a4  ldstr    aDisplaycollect// "DisplayCollectionName"
0x305a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x305ae  ldarg.3
0x305af  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_DisplayCollectionName()
0x305b4  ldc.i4.0
0x305b5  ldc.i4.0
0x305b6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x305bb  ldarg.0
0x305bc  ldstr    aDescription// "Description"
0x305c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x305c6  ldarg.3
0x305c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_Description()
0x305cc  ldc.i4.0
0x305cd  ldc.i4.0
0x305ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x305d3  ldarg.0
0x305d4  ldstr    aIscustomentity// "IsCustomEntity"
0x305d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x305de  ldarg.3
0x305df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_IsCustomEntity()
0x305e4  ldc.i4.0
0x305e5  ldc.i4.0
0x305e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x305eb  ldarg.0
0x305ec  ldstr    aIscustomizable_0// "IsCustomizable"
0x305f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x305f6  ldarg.3
0x305f7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_IsCustomizable()
0x305fc  ldc.i4.0
0x305fd  ldc.i4.0
0x305fe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x30603  ldarg.0
0x30604  ldstr    aIsavailableoff// "IsAvailableOffline"
0x30609  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3060e  ldarg.3
0x3060f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_IsAvailableOffline()
0x30614  ldc.i4.0
0x30615  ldc.i4.0
0x30616  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x3061b  ldarg.0
0x3061c  ldstr    aIsintersect// "IsIntersect"
0x30621  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30626  ldarg.3
0x30627  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_IsIntersect()
0x3062c  ldc.i4.0
0x3062d  ldc.i4.0
0x3062e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x30633  ldarg.0
0x30634  ldstr    aCantriggerwork// "CanTriggerWorkflow"
0x30639  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3063e  ldarg.3
0x3063f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_CanTriggerWorkflow()
0x30644  ldc.i4.0
0x30645  ldc.i4.0
0x30646  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x3064b  ldarg.0
0x3064c  ldstr    aWorkflowsuppor// "WorkflowSupport"
0x30651  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30656  ldarg.3
0x30657  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_WorkflowSupport()
0x3065c  ldc.i4.0
0x3065d  ldc.i4.0
0x3065e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x30663  ldarg.0
0x30664  ldstr    aDuplicatedetec// "DuplicateDetection"
0x30669  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3066e  ldarg.3
0x3066f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_DuplicateDetection()
0x30674  ldc.i4.0
0x30675  ldc.i4.0
0x30676  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x3067b  ldarg.0
0x3067c  ldstr    aIsmailmergeena// "IsMailMergeEnabled"
0x30681  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30686  ldarg.3
0x30687  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_IsMailMergeEnabled()
0x3068c  ldc.i4.0
0x3068d  ldc.i4.0
0x3068e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x30693  ldarg.0
0x30694  ldstr    aIsimportable// "IsImportable"
0x30699  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3069e  ldarg.3
0x3069f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_IsImportable()
0x306a4  ldc.i4.0
0x306a5  ldc.i4.0
0x306a6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x306ab  ldarg.0
0x306ac  ldstr    aIschildentity// "IsChildEntity"
0x306b1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x306b6  ldarg.3
0x306b7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_IsChildEntity()
0x306bc  ldc.i4.0
0x306bd  ldc.i4.0
0x306be  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x306c3  ldarg.0
0x306c4  ldstr    aReportviewname// "ReportViewName"
0x306c9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x306ce  ldarg.3
0x306cf  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_ReportViewName()
0x306d4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x306d9  ldarg.0
0x306da  ldstr    aPrimaryfield// "PrimaryField"
0x306df  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x306e4  ldarg.3
0x306e5  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_PrimaryField()
0x306ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x306ef  ldarg.0
0x306f0  ldstr    aPrimarykey// "PrimaryKey"
0x306f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x306fa  ldarg.3
0x306fb  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_PrimaryKey()
0x30700  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x30705  ldarg.0
0x30706  ldstr    aOwnershiptype// "OwnershipType"
0x3070b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30710  ldarg.3
0x30711  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmOwnershipTypes [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_OwnershipType()
0x30716  ldc.i4.0
0x30717  ldc.i4.0
0x30718  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write13_CrmOwnershipTypes(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmOwnershipTypes o, bool isNullable, bool needType)
0x3071d  ldarg.3
0x3071e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_Attributes()
0x30723  stloc.1
0x30724  ldloc.1
0x30725  brfalse.s loc_30762
0x30727  ldarg.0
0x30728  ldstr    aAttributes// "Attributes"
0x3072d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30732  ldnull
0x30733  ldc.i4.0
0x30734  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x30739  ldc.i4.0
0x3073a  stloc.2
0x3073b  br.s     loc_30756
0x3073d  ldarg.0
0x3073e  ldstr    aAttribute// "Attribute"
0x30743  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30748  ldloc.1
0x30749  ldloc.2
0x3074a  ldelem.ref
0x3074b  ldc.i4.0
0x3074c  ldc.i4.0
0x3074d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write45_AttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata o, bool isNullable, bool needType)
0x30752  ldloc.2
0x30753  ldc.i4.1
0x30754  add
0x30755  stloc.2
0x30756  ldloc.2
0x30757  ldloc.1
0x30758  ldlen
0x30759  conv.i4
0x3075a  blt.s    loc_3073D
0x3075c  ldarg.0
0x3075d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x30762  ldarg.3
0x30763  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_ManyToOneRelationships()
0x30768  stloc.3
0x30769  ldloc.3
0x3076a  brfalse.s loc_307AC
0x3076c  ldarg.0
0x3076d  ldstr    aManytoonerelat// "ManyToOneRelationships"
0x30772  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30777  ldnull
0x30778  ldc.i4.0
0x30779  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3077e  ldc.i4.0
0x3077f  stloc.s  4
0x30781  br.s     loc_3079F
0x30783  ldarg.0
0x30784  ldstr    aFrom// "From"
0x30789  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3078e  ldloc.3
0x3078f  ldloc.s  4
0x30791  ldelem.ref
0x30792  ldc.i4.0
0x30793  ldc.i4.0
0x30794  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write56_OneToManyMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata o, bool isNullable, bool needType)
0x30799  ldloc.s  4
0x3079b  ldc.i4.1
0x3079c  add
0x3079d  stloc.s  4
0x3079f  ldloc.s  4
0x307a1  ldloc.3
0x307a2  ldlen
0x307a3  conv.i4
0x307a4  blt.s    loc_30783
0x307a6  ldarg.0
0x307a7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x307ac  ldarg.3
0x307ad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_OneToManyRelationships()
0x307b2  stloc.s  5
0x307b4  ldloc.s  5
0x307b6  brfalse.s loc_307FA
0x307b8  ldarg.0
0x307b9  ldstr    aOnetomanyrelat// "OneToManyRelationships"
0x307be  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x307c3  ldnull
0x307c4  ldc.i4.0
0x307c5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x307ca  ldc.i4.0
0x307cb  stloc.s  6
0x307cd  br.s     loc_307EC
0x307cf  ldarg.0
0x307d0  ldstr    aTo// "To"
0x307d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x307da  ldloc.s  5
0x307dc  ldloc.s  6
0x307de  ldelem.ref
0x307df  ldc.i4.0
0x307e0  ldc.i4.0
0x307e1  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write56_OneToManyMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OneToManyMetadata o, bool isNullable, bool needType)
0x307e6  ldloc.s  6
0x307e8  ldc.i4.1
0x307e9  add
0x307ea  stloc.s  6
0x307ec  ldloc.s  6
0x307ee  ldloc.s  5
0x307f0  ldlen
0x307f1  conv.i4
0x307f2  blt.s    loc_307CF
0x307f4  ldarg.0
0x307f5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x307fa  ldarg.3
0x307fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityPrivilegeMetadata[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::get_Privileges()
0x30800  stloc.s  7
0x30802  ldloc.s  7
0x30804  brfalse.s loc_30848
  ... truncated ...
```
