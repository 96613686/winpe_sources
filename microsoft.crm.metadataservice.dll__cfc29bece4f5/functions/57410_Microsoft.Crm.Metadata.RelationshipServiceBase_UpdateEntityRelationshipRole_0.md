# Microsoft.Crm.Metadata.RelationshipServiceBase::UpdateEntityRelationshipRole_0

- ea: `0x57410`
- end: `0x57557`
- name: `Microsoft.Crm.Metadata.RelationshipServiceBase::UpdateEntityRelationshipRole_0`
- size: `327`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4fb00`
- `0x57400`

## callees

- `0x2ed30`
- `0x2ef00`
- `0x57410`
- `0x576f0`
- `0x579d0`
- `0x59330`

## string_xrefs

- `0x5744b`: `The entity relationship role with id {0} has entity relationship id {1} which does not match id {2} of the entity relationship being updated`

## pseudocode

```c

```

## disassembly

```asm
0x57410  ldarg.1
0x57411  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::CreateEntityRelationshipRoleDescriptionForUpdate()
0x57416  stloc.0
0x57417  ldloc.0
0x57418  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_EntityRelationshipRoleId()
0x5741d  stloc.1
0x5741e  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x57423  ldloc.1
0x57424  ldstr    aEntityrelation_2// "EntityRelationshipRole"
0x57429  ldarg.s  6
0x5742b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x57430  stloc.2
0x57431  ldloc.2
0x57432  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x57437  stloc.3
0x57438  ldarg.2
0x57439  ldloc.3
0x5743a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_EntityRelationshipId()
0x5743f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x57444  brfalse.s loc_57486
0x57446  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5744b  ldstr    aTheEntityRelat_4// "The entity relationship role with id {0"...
0x57450  ldc.i4.3
0x57451  newarr   [mscorlib]System.Object
0x57456  dup
0x57457  ldc.i4.0
0x57458  ldloc.1
0x57459  box      [mscorlib]System.Guid
0x5745e  stelem.ref
0x5745f  dup
0x57460  ldc.i4.1
0x57461  ldloc.3
0x57462  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_EntityRelationshipId()
0x57467  box      [mscorlib]System.Guid
0x5746c  stelem.ref
0x5746d  dup
0x5746e  ldc.i4.2
0x5746f  ldarg.2
0x57470  box      [mscorlib]System.Guid
0x57475  stelem.ref
0x57476  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5747b  ldc.i4   0x80040203
0x57480  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x57485  throw
0x57486  ldloc.0
0x57487  ldloc.3
0x57488  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag::CreateDifferenceDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag)
0x5748d  stloc.s  4
0x5748f  ldarg.s  6
0x57491  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x57496  ldc.i4.3
0x57497  beq.s    loc_574A2
0x57499  ldarg.s  6
0x5749b  call     bool Microsoft.Crm.Metadata.UpgradeHelper::IsInSystemConvertedSolutionUpgradeContext(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x574a0  brfalse.s loc_574DF
0x574a2  ldloc.s  4
0x574a4  brtrue.s loc_574B7
0x574a6  ldarg.s  6
0x574a8  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x574ad  stloc.s  4
0x574af  ldloc.s  4
0x574b1  ldloc.1
0x574b2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_EntityRelationshipRoleId(valuetype [mscorlib]System.Guid)
0x574b7  ldloc.0
0x574b8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_NavigationPropertyName()
0x574bd  brfalse.s loc_574DF
0x574bf  ldloc.0
0x574c0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_NavigationPropertyName()
0x574c5  ldloc.3
0x574c6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_NavigationPropertyName()
0x574cb  callvirt instance bool [mscorlib]System.String::Equals(string)
0x574d0  brfalse.s loc_574DF
0x574d2  ldloc.s  4
0x574d4  ldloc.3
0x574d5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_NavigationPropertyName()
0x574da  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavigationPropertyName(string)
0x574df  ldloc.s  4
0x574e1  brfalse.s loc_57526
0x574e3  ldarg.s  4
0x574e5  ldc.i4.s 0xC
0x574e7  ldc.i4.1
0x574e8  ldloc.s  4
0x574ea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_EntityRelationshipRoleId()
0x574ef  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::IsActionQueued(valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [mscorlib]System.Guid)
0x574f4  brtrue.s loc_57526
0x574f6  ldloc.3
0x574f7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_RelationshipRoleType()
0x574fc  brfalse.s loc_5751A
0x574fe  ldarg.s  4
0x57500  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x57505  brtrue.s loc_5751A
0x57507  ldarg.0
0x57508  ldarg.2
0x57509  ldloc.s  4
0x5750b  ldloc.2
0x5750c  ldarg.1
0x5750d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::get_CustomLabels()
0x57512  ldarg.3
0x57513  ldarg.s  6
0x57515  call     instance void Microsoft.Crm.Metadata.RelationshipServiceBase::ValidateAndSetDefaultsOnRelationshipRoleForUpdate(valuetype [mscorlib]System.Guid entityRelationshipId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag differenceReferencingRelationshipRoleData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingReferencingRelationshipRoleData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection newLabels, bool mergeLabels, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x5751a  ldarg.s  4
0x5751c  ldloc.s  4
0x5751e  ldc.i4.1
0x5751f  ldarg.s  5
0x57521  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption)
0x57526  ldarg.1
0x57527  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::get_CustomLabels()
0x5752c  brfalse.s loc_57556
0x5752e  ldnull
0x5752f  stloc.s  5
0x57531  ldloc.1
0x57532  ldarg.s  6
0x57534  ldloca.s 5
0x57536  call     void Microsoft.Crm.Metadata.RelationshipServiceBase::GetExistingCustomLabelInformation(valuetype [mscorlib]System.Guid entityRelationshipRoleId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection& customLabels)
0x5753b  ldarg.1
0x5753c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::get_CustomLabels()
0x57541  ldloc.1
0x57542  ldstr    aCustomlabel// "CustomLabel"
0x57547  ldloc.s  5
0x57549  ldarg.s  4
0x5754b  ldc.i4.3
0x5754c  ldarg.3
0x5754d  ldarg.s  5
0x5754f  ldarg.s  6
0x57551  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocalizedLabel::UpdateDisplayInformation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x57556  ret
```
