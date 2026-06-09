# Microsoft.Crm.Metadata.RelationshipService::AddRelationshipToQueueForCreate

- ea: `0x55090`
- end: `0x554c0`
- name: `Microsoft.Crm.Metadata.RelationshipService::AddRelationshipToQueueForCreate`
- size: `1072`
- prototype: ``
- caller_count: `13`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1dd60`
- `0x1e140`
- `0x30240`
- `0x30430`
- `0x34530`
- `0x34660`
- `0x35040`
- `0x3b260`
- `0x3bb10`
- `0x4f690`
- `0x51680`
- `0x521c0`
- `0x524c0`

## callees

- `0x4f8d0`
- `0x55090`
- `0x554c0`
- `0x55810`
- `0x559d0`
- `0x55aa0`
- `0x55bf0`
- `0x56440`
- `0x56490`
- `0x59340`
- `0x59360`

## string_xrefs

- `0x550cf`: `CheckExistingBeforeCreateForInternalSystemConvertedSolutions`
- `0x550e2`: `CheckExistingBeforeCreateForInternalSystemConvertedSolutions`

## pseudocode

```c

```

## disassembly

```asm
0x55090  ldarg.0
0x55091  ldarg.1
0x55092  ldarg.s  5
0x55094  call     void Microsoft.Crm.Metadata.RelationshipService::FixRelationshipPropertiesOverride(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescriptionPropertyBag entityRelationshipDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x55099  ldarg.s  5
0x5509b  call     bool Microsoft.Crm.Metadata.UpgradeHelper::IsInUpdateViaCreateDuringUpgradeContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x550a0  brfalse.s loc_550BF
0x550a2  ldarg.0
0x550a3  ldarg.1
0x550a4  ldarg.s  5
0x550a6  ldarg.s  4
0x550a8  call     bool Microsoft.Crm.Metadata.RelationshipService::TryUpdateRelationshipInsteadOfCreate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescriptionPropertyBag entityRelationshipDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x550ad  brtrue.s loc_550B8
0x550af  ldarg.s  5
0x550b1  call     bool Microsoft.Crm.Metadata.UpgradeHelper::DoCreateIfExistingNotFoundInUpgradeContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x550b6  brtrue.s loc_5512E
0x550b8  ldarg.1
0x550b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_RelationshipId()
0x550be  ret
0x550bf  ldarg.s  4
0x550c1  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x550c6  brfalse.s loc_5512E
0x550c8  ldarg.s  5
0x550ca  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x550cf  ldstr    aCheckexistingb// "CheckExistingBeforeCreateForInternalSys"...
0x550d4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x550d9  brfalse.s loc_5512E
0x550db  ldarg.s  5
0x550dd  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x550e2  ldstr    aCheckexistingb// "CheckExistingBeforeCreateForInternalSys"...
0x550e7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x550ec  unbox.any [mscorlib]System.Boolean
0x550f1  brfalse.s loc_5512E
0x550f3  ldarg.1
0x550f4  ldloca.s 6
0x550f6  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x550fc  ldloc.s  6
0x550fe  ldc.i4.0
0x550ff  ldarg.s  5
0x55101  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.RelationshipService::RetrieveRelationshipsByName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> solutionId, bool addAllColumns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x55106  stloc.s  5
0x55108  ldloc.s  5
0x5510a  brfalse.s loc_5512E
0x5510c  ldloc.s  5
0x5510e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x55113  ldc.i4.0
0x55114  ble.s    loc_5512E
0x55116  ldloc.s  5
0x55118  ldc.i4.0
0x55119  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x5511e  ldstr    aRelationshipid// "relationshipid"
0x55123  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x55128  unbox.any [mscorlib]System.Guid
0x5512d  ret
0x5512e  ldarg.s  8
0x55130  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x55135  brtrue.s loc_5513B
0x55137  ldarg.s  8
0x55139  br.s     loc_55141
0x5513b  ldarg.1
0x5513c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_Name()
0x55141  starg.s  8
0x55143  ldarg.0
0x55144  ldstr    aEntityrelation_10// "entityRelationshipDescription"
0x55149  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5514e  ldarg.1
0x5514f  ldstr    aRelationshipde// "relationshipDescription"
0x55154  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x55159  ldarg.2
0x5515a  ldstr    aReferencingent_0// "referencingEntityRoleDescription"
0x5515f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x55164  ldarg.s  4
0x55166  ldstr    aHelper// "helper"
0x5516b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x55170  ldarg.1
0x55171  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag::get_InnerEntityData()
0x55176  stloc.0
0x55177  ldloc.0
0x55178  ldstr    aName// "name"
0x5517d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x55182  brtrue.s loc_551B8
0x55184  ldloc.0
0x55185  ldstr    aIscustomrelati// "iscustomrelationship"
0x5518a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5518f  brtrue.s loc_551B8
0x55191  ldloc.0
0x55192  ldstr    aReferencingent// "referencingentityid"
0x55197  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5519c  brtrue.s loc_551B8
0x5519e  ldloc.0
0x5519f  ldstr    aReferencedenti// "referencedentityid"
0x551a4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x551a9  brtrue.s loc_551B8
0x551ab  ldloc.0
0x551ac  ldstr    aRelationshipid// "relationshipid"
0x551b1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x551b6  brfalse.s loc_551E1
0x551b8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x551bd  ldstr    aOneOrMoreExpec// "One or more expected properties were no"...
0x551c2  ldc.i4.1
0x551c3  newarr   [mscorlib]System.Object
0x551c8  dup
0x551c9  ldc.i4.0
0x551ca  ldarg.1
0x551cb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_RelationshipId()
0x551d0  box      [mscorlib]System.Guid
0x551d5  stelem.ref
0x551d6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x551db  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x551e0  throw
0x551e1  ldarg.0
0x551e2  ldstr    aEntityrelation// "entityrelationshipid"
0x551e7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x551ec  brfalse.s loc_5521D
0x551ee  ldarg.0
0x551ef  ldstr    aSchemaname// "schemaname"
0x551f4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x551f9  brfalse.s loc_5521D
0x551fb  ldarg.0
0x551fc  ldstr    aEntityrelation_0// "entityrelationshiptype"
0x55201  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x55206  brfalse.s loc_5521D
0x55208  ldarg.0
0x55209  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescription::get_EntityRelationshipType()
0x5520e  brtrue.s loc_5521D
0x55210  ldarg.0
0x55211  ldstr    aIscustomrelati// "iscustomrelationship"
0x55216  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x5521b  brtrue.s loc_55246
0x5521d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x55222  ldstr    aOneOrMoreExpec_0// "One or more expected properties were no"...
0x55227  ldc.i4.1
0x55228  newarr   [mscorlib]System.Object
0x5522d  dup
0x5522e  ldc.i4.0
0x5522f  ldarg.0
0x55230  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescription::get_EntityRelationshipId()
0x55235  box      [mscorlib]System.Guid
0x5523a  stelem.ref
0x5523b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x55240  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x55245  throw
0x55246  ldarg.2
0x55247  ldstr    aEntityrelation_1// "entityrelationshiproleid"
0x5524c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x55251  brfalse.s loc_55283
0x55253  ldarg.2
0x55254  ldstr    aEntityrelation// "entityrelationshipid"
0x55259  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x5525e  brfalse.s loc_55283
0x55260  ldarg.2
0x55261  ldstr    aEntityid// "entityid"
0x55266  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x5526b  brfalse.s loc_55283
0x5526d  ldarg.2
0x5526e  ldstr    aRelationshipro// "relationshiproletype"
0x55273  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x55278  brfalse.s loc_55283
0x5527a  ldarg.2
0x5527b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_RelationshipRoleType()
0x55280  ldc.i4.1
0x55281  beq.s    loc_552AC
0x55283  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x55288  ldstr    aOneOrMoreExpec_0// "One or more expected properties were no"...
0x5528d  ldc.i4.1
0x5528e  newarr   [mscorlib]System.Object
0x55293  dup
0x55294  ldc.i4.0
0x55295  ldarg.0
0x55296  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescription::get_EntityRelationshipId()
0x5529b  box      [mscorlib]System.Guid
0x552a0  stelem.ref
0x552a1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x552a6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x552ab  throw
0x552ac  ldarg.2
0x552ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_EntityId()
0x552b2  ldarg.1
0x552b3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_ReferencingEntityId()
0x552b8  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x552bd  brfalse.s loc_552CF
0x552bf  ldstr    aTheEntityIdOfT// "The entity id of the referencing entity"...
0x552c4  ldc.i4   0x80040216
0x552c9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x552ce  throw
0x552cf  ldarg.2
0x552d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_EntityRelationshipId()
0x552d5  ldarg.0
0x552d6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescription::get_EntityRelationshipId()
0x552db  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x552e0  brfalse.s loc_552F2
0x552e2  ldstr    aTheEntityRelat_2// "The entity relationship id of the refer"...
0x552e7  ldc.i4   0x80040216
0x552ec  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x552f1  throw
0x552f2  ldarga.s 0xA
0x552f4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption>::get_HasValue()
0x552f9  brtrue.s loc_55305
0x552fb  ldloc.0
0x552fc  ldarg.s  5
0x552fe  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.RelationshipService::GetContextModifierOption(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity relationship, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x55303  br.s     loc_5530C
0x55305  ldarga.s 0xA
0x55307  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption>::get_Value()
0x5530c  stloc.1
0x5530d  ldarg.s  4
0x5530f  ldarg.0
0x55310  ldc.i4.0
0x55311  ldloc.1
0x55312  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption)
0x55317  ldarg.s  5
0x55319  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5531e  stloc.2
0x5531f  ldloc.2
0x55320  ldarg.1
0x55321  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_ReferencedEntityId()
0x55326  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_EntityId(valuetype [mscorlib]System.Guid)
0x5532b  ldloc.2
0x5532c  ldarg.0
0x5532d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescription::get_EntityRelationshipId()
0x55332  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_EntityRelationshipId(valuetype [mscorlib]System.Guid)
0x55337  ldloc.2
0x55338  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x5533d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_EntityRelationshipRoleId(valuetype [mscorlib]System.Guid)
0x55342  ldloc.2
0x55343  ldc.i4.0
0x55344  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_RelationshipRoleType(int32)
0x55349  ldarg.s  5
0x5534b  call     bool Microsoft.Crm.Metadata.RelationshipService::CheckIfNavigationPropertyNameExists(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x55350  brfalse.s loc_55388
0x55352  ldarg.s  8
0x55354  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x55359  brtrue.s loc_55388
0x5535b  ldloc.2
0x5535c  ldarg.s  8
0x5535e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavigationPropertyName(string)
0x55363  ldarg.s  5
0x55365  ldarg.s  6
0x55367  ldarg.s  8
0x55369  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityRelationshipRoleService::DoesDuplicateNavigationPropertyNameExist(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, string, string)
0x5536e  brfalse.s loc_55388
0x55370  ldloc.2
0x55371  dup
0x55372  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_NavigationPropertyName()
0x55377  ldstr    asc_89446// "_"
0x5537c  ldarg.s  7
0x5537e  call     string [mscorlib]System.String::Concat(string, string, string)
0x55383  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavigationPropertyName(string)
0x55388  ldarg.s  4
0x5538a  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x5538f  brfalse  loc_55436
0x55394  ldloc.2
0x55395  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag::get_InnerEntityData()
0x5539a  dup
0x5539b  ldstr    aNavpaneiscusto// "navpaneiscustomizable"
0x553a0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x553a5  brfalse.s loc_553AE
0x553a7  ldloc.2
0x553a8  ldc.i4.0
0x553a9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneIsCustomizable(bool)
0x553ae  ldstr    aNavpaneoffline// "navpaneoffline"
0x553b3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x553b8  brfalse.s loc_553C1
0x553ba  ldloc.2
0x553bb  ldc.i4.1
0x553bc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneOffline(bool)
0x553c1  ldarg.2
0x553c2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag::get_InnerEntityData()
0x553c7  dup
0x553c8  ldstr    aNavpaneiscusto// "navpaneiscustomizable"
0x553cd  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x553d2  brfalse.s loc_553DB
0x553d4  ldarg.2
0x553d5  ldc.i4.0
0x553d6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneIsCustomizable(bool)
0x553db  ldstr    aNavpaneoffline// "navpaneoffline"
0x553e0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x553e5  brfalse.s loc_553EE
0x553e7  ldarg.2
0x553e8  ldc.i4.1
0x553e9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneOffline(bool)
0x553ee  ldarg.s  5
0x553f0  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleOverrider::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x553f5  dup
0x553f6  ldarg.0
0x553f7  ldstr    aSchemaname// "schemaname"
0x553fc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x55401  callvirt instance string [mscorlib]System.Object::ToString()
0x55406  ldstr    aReferenced// "Referenced"
0x5540b  ldloc.2
0x5540c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag::get_InnerEntityData()
0x55411  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleOverrider::OverrideEntityRelationshipRole(string schemaName, string roleTypeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity)
0x55416  ldarg.0
0x55417  ldstr    aSchemaname// "schemaname"
0x5541c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x55421  callvirt instance string [mscorlib]System.Object::ToString()
0x55426  ldstr    aReferencing// "Referencing"
0x5542b  ldarg.2
0x5542c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag::get_InnerEntityData()
0x55431  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleOverrider::OverrideEntityRelationshipRole(string schemaName, string roleTypeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity)
  ... truncated ...
```
