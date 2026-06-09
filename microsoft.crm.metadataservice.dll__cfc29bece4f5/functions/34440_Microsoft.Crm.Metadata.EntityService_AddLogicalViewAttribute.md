# Microsoft.Crm.Metadata.EntityService::AddLogicalViewAttribute

- ea: `0x34440`
- end: `0x3452a`
- name: `Microsoft.Crm.Metadata.EntityService::AddLogicalViewAttribute`
- size: `234`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x30a80`
- `0x336a0`
- `0x33fd0`
- `0x351b0`

## callees

- `0x261b0`
- `0x34440`
- `0x3c3c0`
- `0x56300`
- `0x56320`
- `0x59340`

## string_xrefs

- `0x344b0`: `CheckExistingBeforeCreateForInternalSystemConvertedSolutions`
- `0x344c3`: `CheckExistingBeforeCreateForInternalSystemConvertedSolutions`

## pseudocode

```c

```

## disassembly

```asm
0x34440  ldarg.s  4
0x34442  call     bool Microsoft.Crm.Metadata.UpgradeHelper::IsInUpdateViaCreateDuringUpgradeContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x34447  brfalse.s loc_3444E
0x34449  ldarg.s  5
0x3444b  brtrue.s loc_3444E
0x3444d  ret
0x3444e  ldarg.3
0x3444f  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x34454  brfalse.s loc_3446B
0x34456  ldarg.s  4
0x34458  newobj   instance void Microsoft.Crm.Metadata.RelationshipViewAttributeOverrider::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3445d  ldarg.0
0x3445e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag::get_InnerEntityData()
0x34463  callvirt instance bool Microsoft.Crm.Metadata.RelationshipViewAttributeOverrider::ShouldSkipViewAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity)
0x34468  brfalse.s loc_3446B
0x3446a  ret
0x3446b  ldarg.s  4
0x3446d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfoDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x34472  stloc.0
0x34473  ldloc.0
0x34474  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x34479  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfoDescription::set_ViewAttributeId(valuetype [mscorlib]System.Guid)
0x3447e  ldloc.0
0x3447f  ldarg.0
0x34480  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_RelationshipId()
0x34485  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfoDescription::set_RelationshipId(valuetype [mscorlib]System.Guid)
0x3448a  ldloc.0
0x3448b  ldarg.1
0x3448c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfoDescription::set_AttributeId(valuetype [mscorlib]System.Guid)
0x34491  ldloc.0
0x34492  ldarg.2
0x34493  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfoDescription::set_RemoteAttributeId(valuetype [mscorlib]System.Guid)
0x34498  ldarg.s  4
0x3449a  call     bool Microsoft.Crm.Metadata.UpgradeHelper::IsInUpdateViaCreateDuringUpgradeContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3449f  brtrue.s loc_344D4
0x344a1  ldarg.3
0x344a2  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x344a7  brfalse.s loc_3451A
0x344a9  ldarg.s  4
0x344ab  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x344b0  ldstr    aCheckexistingb// "CheckExistingBeforeCreateForInternalSys"...
0x344b5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x344ba  brfalse.s loc_3451A
0x344bc  ldarg.s  4
0x344be  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x344c3  ldstr    aCheckexistingb// "CheckExistingBeforeCreateForInternalSys"...
0x344c8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x344cd  unbox.any [mscorlib]System.Boolean
0x344d2  brfalse.s loc_3451A
0x344d4  ldloca.s 1
0x344d6  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x344dc  ldarg.s  4
0x344de  call     bool Microsoft.Crm.Metadata.UpgradeHelper::IsInUpdateViaCreateDuringUpgradeContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x344e3  brfalse.s loc_344F1
0x344e5  ldloca.s 1
0x344e7  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x344ec  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x344f1  ldloc.0
0x344f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfoDescription::get_RelationshipId()
0x344f7  ldloc.0
0x344f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfoDescription::get_AttributeId()
0x344fd  ldloc.0
0x344fe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfoDescription::get_RemoteAttributeId()
0x34503  ldloc.1
0x34504  ldarg.3
0x34505  ldarg.s  4
0x34507  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.EntityService::RetrieveLogicalViewAttribute(valuetype [mscorlib]System.Guid relationshipId, valuetype [mscorlib]System.Guid attributeId, valuetype [mscorlib]System.Guid remoteAttributeId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> solutionId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3450c  stloc.2
0x3450d  ldloc.2
0x3450e  brfalse.s loc_3451A
0x34510  ldloc.2
0x34511  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x34516  ldc.i4.0
0x34517  ble.s    loc_3451A
0x34519  ret
0x3451a  ldarg.3
0x3451b  ldloc.0
0x3451c  ldc.i4.0
0x3451d  ldarg.s  4
0x3451f  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.AttributeService::GetContextModifierOption(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x34524  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IViewInfoDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption)
0x34529  ret
```
