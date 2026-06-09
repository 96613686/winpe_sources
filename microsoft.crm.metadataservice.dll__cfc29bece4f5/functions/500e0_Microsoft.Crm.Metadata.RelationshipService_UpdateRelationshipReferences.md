# Microsoft.Crm.Metadata.RelationshipService::UpdateRelationshipReferences

- ea: `0x500e0`
- end: `0x502e7`
- name: `Microsoft.Crm.Metadata.RelationshipService::UpdateRelationshipReferences`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x4fb00`

## callees

- `0x500e0`
- `0x50520`
- `0x50560`
- `0x505a0`
- `0x505e0`
- `0x55bd0`

## string_xrefs

- `0x501ab`: `entityrelationshiprelationshipsid`

## pseudocode

```c

```

## disassembly

```asm
0x500e0  ldarg.0
0x500e1  ldarg.1
0x500e2  ldarg.s  5
0x500e4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x500e9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.RelationshipService::RetrieveEntityRelationshipRoles(valuetype [mscorlib]System.Guid entityRelationshipId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x500ee  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x500f3  stloc.0
0x500f4  br.s     loc_5013E
0x500f6  ldloc.0
0x500f7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x500fc  stloc.1
0x500fd  ldarg.s  5
0x500ff  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50104  stloc.2
0x50105  ldloc.2
0x50106  ldloc.1
0x50107  ldstr    aEntityrelation_1// "entityrelationshiproleid"
0x5010c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x50111  unbox.any [mscorlib]System.Guid
0x50116  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_EntityRelationshipRoleId(valuetype [mscorlib]System.Guid)
0x5011b  ldarg.s  4
0x5011d  ldc.i4.s 0xC
0x5011f  ldc.i4.1
0x50120  ldloc.2
0x50121  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_EntityRelationshipRoleId()
0x50126  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::IsActionQueued(valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [mscorlib]System.Guid)
0x5012b  brtrue.s loc_5013E
0x5012d  ldarg.s  4
0x5012f  ldloc.2
0x50130  ldc.i4.1
0x50131  ldarg.3
0x50132  ldarg.s  5
0x50134  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.RelationshipService::GetContextModifierOption(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x50139  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption)
0x5013e  ldloc.0
0x5013f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x50144  brtrue.s loc_500F6
0x50146  leave.s  loc_50152
0x50148  ldloc.0
0x50149  brfalse.s loc_50151
0x5014b  ldloc.0
0x5014c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x50151  endfinally
0x50152  ldarg.s  4
0x50154  ldc.i4.s 0xB
0x50156  ldc.i4.1
0x50157  ldarg.1
0x50158  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::IsActionQueued(valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [mscorlib]System.Guid)
0x5015d  brtrue.s loc_5017F
0x5015f  ldarg.s  5
0x50161  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50166  stloc.3
0x50167  ldloc.3
0x50168  ldarg.1
0x50169  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescription::set_EntityRelationshipId(valuetype [mscorlib]System.Guid)
0x5016e  ldarg.s  4
0x50170  ldloc.3
0x50171  ldc.i4.1
0x50172  ldarg.3
0x50173  ldarg.s  5
0x50175  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.RelationshipService::GetContextModifierOption(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5017a  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption)
0x5017f  ldarg.0
0x50180  ldarg.1
0x50181  ldarg.2
0x50182  ldarg.s  5
0x50184  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x50189  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.RelationshipService::RetrieveEntityRelationshipRelationships(valuetype [mscorlib]System.Guid entityRelationshipId, valuetype [mscorlib]System.Guid relationshipId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x5018e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x50193  stloc.0
0x50194  br.s     loc_501E4
0x50196  ldloc.0
0x50197  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x5019c  stloc.s  4
0x5019e  ldarg.s  5
0x501a0  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x501a5  stloc.s  5
0x501a7  ldloc.s  5
0x501a9  ldloc.s  4
0x501ab  ldstr    aEntityrelation_7// "entityrelationshiprelationshipsid"
0x501b0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x501b5  unbox.any [mscorlib]System.Guid
0x501ba  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::set_EntityRelationshipRelationshipsId(valuetype [mscorlib]System.Guid)
0x501bf  ldarg.s  4
0x501c1  ldc.i4.s 0xD
0x501c3  ldc.i4.1
0x501c4  ldloc.s  5
0x501c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::get_EntityRelationshipRelationshipsId()
0x501cb  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::IsActionQueued(valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [mscorlib]System.Guid)
0x501d0  brtrue.s loc_501E4
0x501d2  ldarg.s  4
0x501d4  ldloc.s  5
0x501d6  ldc.i4.1
0x501d7  ldarg.3
0x501d8  ldarg.s  5
0x501da  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.RelationshipService::GetContextModifierOption(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x501df  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRelationshipsDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption)
0x501e4  ldloc.0
0x501e5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x501ea  brtrue.s loc_50196
0x501ec  leave.s  loc_501F8
0x501ee  ldloc.0
0x501ef  brfalse.s loc_501F7
0x501f1  ldloc.0
0x501f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x501f7  endfinally
0x501f8  ldarg.0
0x501f9  ldarg.2
0x501fa  ldarg.s  5
0x501fc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x50201  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.RelationshipService::RetrieveRelationshipExtraConditions(valuetype [mscorlib]System.Guid relationshipId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x50206  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x5020b  stloc.0
0x5020c  br.s     loc_5025B
0x5020e  ldloc.0
0x5020f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x50214  stloc.s  6
0x50216  ldarg.s  5
0x50218  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipExtraConditionDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5021d  stloc.s  7
0x5021f  ldloc.s  7
0x50221  ldloc.s  6
0x50223  ldstr    aConditionid// "conditionid"
0x50228  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5022d  unbox.any [mscorlib]System.Guid
0x50232  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipExtraConditionDescription::set_ConditionId(valuetype [mscorlib]System.Guid)
0x50237  ldarg.s  4
0x50239  ldc.i4.4
0x5023a  ldc.i4.1
0x5023b  ldloc.s  7
0x5023d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipExtraConditionDescription::get_ConditionId()
0x50242  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::IsActionQueued(valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [mscorlib]System.Guid)
0x50247  brtrue.s loc_5025B
0x50249  ldarg.s  4
0x5024b  ldloc.s  7
0x5024d  ldc.i4.1
0x5024e  ldarg.3
0x5024f  ldarg.s  5
0x50251  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.RelationshipService::GetContextModifierOption(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x50256  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipExtraConditionDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption)
0x5025b  ldloc.0
0x5025c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x50261  brtrue.s loc_5020E
0x50263  leave.s  loc_5026F
0x50265  ldloc.0
0x50266  brfalse.s loc_5026E
0x50268  ldloc.0
0x50269  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5026e  endfinally
0x5026f  ldarg.0
0x50270  ldarg.2
0x50271  ldarg.s  5
0x50273  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x50278  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.RelationshipService::RetrieveViewAttributes(valuetype [mscorlib]System.Guid relationshipId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x5027d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x50282  stloc.0
0x50283  br.s     loc_502D2
0x50285  ldloc.0
0x50286  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x5028b  stloc.s  8
0x5028d  ldarg.s  5
0x5028f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfoDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50294  stloc.s  9
0x50296  ldloc.s  9
0x50298  ldloc.s  8
0x5029a  ldstr    aViewattributei// "viewattributeid"
0x5029f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x502a4  unbox.any [mscorlib]System.Guid
0x502a9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfoDescription::set_ViewAttributeId(valuetype [mscorlib]System.Guid)
0x502ae  ldarg.s  4
0x502b0  ldc.i4.3
0x502b1  ldc.i4.1
0x502b2  ldloc.s  9
0x502b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfoDescription::get_ViewAttributeId()
0x502b9  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::IsActionQueued(valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [mscorlib]System.Guid)
0x502be  brtrue.s loc_502D2
0x502c0  ldarg.s  4
0x502c2  ldloc.s  9
0x502c4  ldc.i4.1
0x502c5  ldarg.3
0x502c6  ldarg.s  5
0x502c8  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.RelationshipService::GetContextModifierOption(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x502cd  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IViewInfoDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption)
0x502d2  ldloc.0
0x502d3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x502d8  brtrue.s loc_50285
0x502da  leave.s  loc_502E6
0x502dc  ldloc.0
0x502dd  brfalse.s loc_502E5
0x502df  ldloc.0
0x502e0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x502e5  endfinally
0x502e6  ret
```
