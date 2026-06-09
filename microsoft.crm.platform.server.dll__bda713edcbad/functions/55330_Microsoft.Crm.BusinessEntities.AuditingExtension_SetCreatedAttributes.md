# Microsoft.Crm.BusinessEntities.AuditingExtension::SetCreatedAttributes

- ea: `0x55330`
- end: `0x554a6`
- name: `Microsoft.Crm.BusinessEntities.AuditingExtension::SetCreatedAttributes`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x551c0`

## callees

- `0x55330`
- `0x61e70`
- `0x66b10`

## string_xrefs

- `0x5534b`: `overriddencreatedby`
- `0x55398`: `overriddencreatedby`
- `0x553be`: `overriddencreatedby`
- `0x553ce`: `overriddencreatedby`
- `0x55358`: `overriddencreatedon`
- `0x553df`: `overriddencreatedon`
- `0x553f9`: `overriddencreatedon`
- `0x5543a`: `overriddencreatedon`
- `0x55378`: `prvOverrideCreatedOnCreatedBy`
- `0x553a5`: `createdby`
- `0x553b8`: `createdby`
- `0x55458`: `createdby`
- `0x55465`: `createdby`
- `0x553ec`: `createdon`
- `0x5542e`: `createdon`
- `0x55447`: `createdon`
- `0x55488`: `createdonbehalfby`
- `0x55495`: `createdonbehalfby`

## pseudocode

```c

```

## disassembly

```asm
0x55330  ldarg.0
0x55331  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x55336  stloc.0
0x55337  ldloc.0
0x55338  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsImportable()
0x5533d  brtrue.s loc_5534A
0x5533f  ldloc.0
0x55340  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x55345  brfalse  loc_55446
0x5534a  ldarg.0
0x5534b  ldstr    aOverriddencrea// "overriddencreatedby"
0x55350  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x55355  brfalse.s loc_55367
0x55357  ldarg.0
0x55358  ldstr    aOverriddencrea_0// "overriddencreatedon"
0x5535d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x55362  brtrue   loc_55446
0x55367  ldarg.s  4
0x55369  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5536e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x55373  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x55378  ldstr    aPrvoverridecre// "prvOverrideCreatedOnCreatedBy"
0x5537d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x55382  stloc.1
0x55383  ldarg.s  4
0x55385  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x5538a  ldloc.1
0x5538b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x55390  ldarg.s  4
0x55392  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid user, valuetype [mscorlib]System.Guid privilege, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x55397  ldarg.0
0x55398  ldstr    aOverriddencrea// "overriddencreatedby"
0x5539d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x553a2  brfalse.s loc_553B7
0x553a4  ldarg.0
0x553a5  ldstr    aCreatedby// "createdby"
0x553aa  ldarg.1
0x553ab  box      [mscorlib]System.Guid
0x553b0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x553b5  br.s     loc_553DE
0x553b7  ldarg.0
0x553b8  ldstr    aCreatedby// "createdby"
0x553bd  ldarg.0
0x553be  ldstr    aOverriddencrea// "overriddencreatedby"
0x553c3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x553c8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x553cd  ldarg.0
0x553ce  ldstr    aOverriddencrea// "overriddencreatedby"
0x553d3  ldarg.1
0x553d4  box      [mscorlib]System.Guid
0x553d9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x553de  ldarg.0
0x553df  ldstr    aOverriddencrea_0// "overriddencreatedon"
0x553e4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x553e9  brfalse.s loc_553F8
0x553eb  ldarg.0
0x553ec  ldstr    aCreatedon// "createdon"
0x553f1  ldarg.3
0x553f2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x553f7  ret
0x553f8  ldarg.0
0x553f9  ldstr    aOverriddencrea_0// "overriddencreatedon"
0x553fe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x55403  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x55408  stloc.2
0x55409  ldloc.2
0x5540a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x5540f  ldarg.3
0x55410  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x55415  call     int32 [mscorlib]System.DateTime::Compare(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5541a  ldc.i4.0
0x5541b  ble.s    loc_5542D
0x5541d  ldstr    aSystemDateCann// "System date cannot be set to a date in "...
0x55422  ldc.i4   0x80040239
0x55427  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5542c  throw
0x5542d  ldarg.0
0x5542e  ldstr    aCreatedon// "createdon"
0x55433  ldloc.2
0x55434  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x55439  ldarg.0
0x5543a  ldstr    aOverriddencrea_0// "overriddencreatedon"
0x5543f  ldarg.3
0x55440  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x55445  ret
0x55446  ldarg.0
0x55447  ldstr    aCreatedon// "createdon"
0x5544c  ldarg.3
0x5544d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x55452  ldarg.0
0x55453  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x55458  ldstr    aCreatedby// "createdby"
0x5545d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x55462  brfalse.s loc_55475
0x55464  ldarg.0
0x55465  ldstr    aCreatedby// "createdby"
0x5546a  ldarg.1
0x5546b  box      [mscorlib]System.Guid
0x55470  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x55475  ldarg.2
0x55476  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5547b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x55480  brfalse.s loc_554A5
0x55482  ldarg.0
0x55483  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x55488  ldstr    aCreatedonbehal// "createdonbehalfby"
0x5548d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x55492  brfalse.s loc_554A5
0x55494  ldarg.0
0x55495  ldstr    aCreatedonbehal// "createdonbehalfby"
0x5549a  ldarg.2
0x5549b  box      [mscorlib]System.Guid
0x554a0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x554a5  ret
```
