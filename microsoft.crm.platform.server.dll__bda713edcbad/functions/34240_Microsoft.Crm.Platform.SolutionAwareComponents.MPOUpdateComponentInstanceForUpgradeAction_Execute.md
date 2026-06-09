# Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateComponentInstanceForUpgradeAction::Execute

- ea: `0x34240`
- end: `0x3449d`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateComponentInstanceForUpgradeAction::Execute`
- size: `605`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callees

- `0x34240`
- `0x344a0`
- `0x34810`
- `0x34860`
- `0x35b60`
- `0x35ba0`
- `0x35bc0`
- `0x35be0`
- `0x36110`
- `0x37da0`
- `0x37fc0`
- `0x42ed0`
- `0x45fe0`
- `0x460c0`
- `0x46190`
- `0x46f40`
- `0x47290`
- `0x66ae0`

## string_xrefs

- `0x34398`: `RowGuidId cannot be empty when updating a component row`
- `0x343f9`: `Updating full data for upgrade in a row for metadata entity {0}; {1}: {2}; ComponentState: {3}; OverwriteTime: {4}; SupportSolutionId: {5}`

## pseudocode

```c

```

## disassembly

```asm
0x34240  ldarg.0
0x34241  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance[] Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateComponentInstanceForUpgradeAction::_instancesToUpdate
0x34246  brtrue.s loc_34249
0x34248  ret
0x34249  ldarg.0
0x3424a  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateComponentInstanceForUpgradeAction::_masterInstance
0x3424f  castclass Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance
0x34254  ldarg.1
0x34255  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3425a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.MPOComponentActionHelper::FillInAllColumns(class Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance instance, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x3425f  stloc.0
0x34260  ldarg.0
0x34261  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x34266  castclass Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance
0x3426b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance::get_Entity()
0x34270  stloc.1
0x34271  ldarg.0
0x34272  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance[] Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateComponentInstanceForUpgradeAction::_instancesToUpdate
0x34277  stloc.2
0x34278  ldc.i4.0
0x34279  stloc.3
0x3427a  br       loc_34493
0x3427f  ldloc.2
0x34280  ldloc.3
0x34281  ldelem.ref
0x34282  stloc.s  4
0x34284  ldloc.s  4
0x34286  castclass Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance
0x3428b  ldarg.1
0x3428c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x34291  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.MPOComponentActionHelper::FillInAllColumns(class Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance instance, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x34296  stloc.s  5
0x34298  ldloc.0
0x34299  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x3429e  ldarg.1
0x3429f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x342a4  stloc.s  6
0x342a6  ldc.i4.0
0x342a7  stloc.s  7
0x342a9  ldloc.1
0x342aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataAttributes()
0x342af  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection::GetEnumerator()
0x342b4  stloc.s  8
0x342b6  br       loc_34346
0x342bb  ldloc.s  8
0x342bd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x342c2  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo
0x342c7  stloc.s  9
0x342c9  ldloc.1
0x342ca  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x342cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadataDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_Attributes()
0x342d4  ldloc.s  9
0x342d6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo::get_Name()
0x342db  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata>::get_Item(void)
0x342e0  stloc.s  0xA
0x342e2  ldloc.s  0xA
0x342e4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x342e9  call     bool Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionHelper::IsSolutionComponentAttribute(string attributeName)
0x342ee  brtrue.s loc_34346
0x342f0  ldloc.s  0xA
0x342f2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_IsRowIdField()
0x342f7  brtrue.s loc_34346
0x342f9  ldloc.s  0xA
0x342fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataManagedPropertyMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_ManagedProperty()
0x34300  brtrue.s loc_34346
0x34302  ldarg.0
0x34303  ldloc.1
0x34304  ldloc.0
0x34305  ldloc.s  9
0x34307  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo::get_MetadataAttribute()
0x3430c  call     instance bool Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateComponentInstanceForUpgradeAction::AreDataValuesDifferent(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityOne, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityTwo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata attribute)
0x34311  brfalse.s loc_34346
0x34313  ldarg.0
0x34314  ldloc.0
0x34315  ldloc.s  5
0x34317  ldloc.s  9
0x34319  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo::get_MetadataAttribute()
0x3431e  call     instance bool Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateComponentInstanceForUpgradeAction::AreDataValuesDifferent(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityOne, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityTwo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata attribute)
0x34323  brtrue.s loc_34346
0x34325  ldloc.s  6
0x34327  ldloc.s  0xA
0x34329  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x3432e  ldloc.1
0x3432f  ldloc.s  0xA
0x34331  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x34336  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3433b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x34340  ldloc.s  7
0x34342  ldc.i4.1
0x34343  or
0x34344  stloc.s  7
0x34346  ldloc.s  8
0x34348  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3434d  brtrue   loc_342BB
0x34352  leave.s  loc_34369
0x34354  ldloc.s  8
0x34356  isinst   [mscorlib]System.IDisposable
0x3435b  stloc.s  0xB
0x3435d  ldloc.s  0xB
0x3435f  brfalse.s loc_34368
0x34361  ldloc.s  0xB
0x34363  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34368  endfinally
0x34369  ldloc.s  7
0x3436b  brfalse  loc_3448F
0x34370  ldloc.s  4
0x34372  ldloc.s  6
0x34374  call     void Microsoft.Crm.Platform.SolutionAwareComponents.MPOComponentActionHelper::SetInstancePropertiesOnEntity(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity metadataEntity)
0x34379  ldloc.s  6
0x3437b  ldstr    aSolutionid_0// "solutionid"
0x34380  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::Remove(string)
0x34385  ldloc.s  4
0x34387  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3438c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x34391  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x34396  brfalse.s loc_343A8
0x34398  ldstr    aRowguididCanno// "RowGuidId cannot be empty when updating"...
0x3439d  ldc.i4   0x80040203
0x343a2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x343a7  throw
0x343a8  ldloc.s  6
0x343aa  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x343af  ldarg.1
0x343b0  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression::.ctor(string metadataEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x343b5  stloc.s  0xC
0x343b7  ldloc.s  0xC
0x343b9  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression::get_Conditions()
0x343be  ldloc.s  6
0x343c0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x343c5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x343ca  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x343cf  ldloc.s  4
0x343d1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x343d6  box      [mscorlib]System.Guid
0x343db  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, object value)
0x343e0  ldloc.s  6
0x343e2  ldloc.s  0xC
0x343e4  ldarg.1
0x343e5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x343ea  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleUpdatePlan::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression filter, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x343ef  stloc.s  0xD
0x343f1  ldarg.1
0x343f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x343f7  ldc.i4.s 0x14
0x343f9  ldstr    aUpdatingFullDa_0// "Updating full data for upgrade in a row"...
0x343fe  ldc.i4.6
0x343ff  newarr   [mscorlib]System.Object
0x34404  dup
0x34405  ldc.i4.0
0x34406  ldloc.s  6
0x34408  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x3440d  stelem.ref
0x3440e  dup
0x3440f  ldc.i4.1
0x34410  ldloc.s  6
0x34412  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x34417  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x3441c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x34421  stelem.ref
0x34422  dup
0x34423  ldc.i4.2
0x34424  ldloc.s  6
0x34426  ldloc.s  6
0x34428  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x3442d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x34432  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x34437  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3443c  stelem.ref
0x3443d  dup
0x3443e  ldc.i4.3
0x3443f  ldloc.s  4
0x34441  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x34446  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x3444b  stelem.ref
0x3444c  dup
0x3444d  ldc.i4.4
0x3444e  ldloc.s  4
0x34450  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x34455  stelem.ref
0x34456  dup
0x34457  ldc.i4.5
0x34458  ldloc.s  4
0x3445a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x3445f  box      [mscorlib]System.Guid
0x34464  stelem.ref
0x34465  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3446a  ldloc.s  0xD
0x3446c  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryPlan::get_Command()
0x34471  stloc.s  0xE
0x34473  ldloc.s  0xE
0x34475  ldarg.1
0x34476  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3447b  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x34480  pop
0x34481  leave.s  loc_3448F
0x34483  ldloc.s  0xE
0x34485  brfalse.s loc_3448E
0x34487  ldloc.s  0xE
0x34489  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3448e  endfinally
0x3448f  ldloc.3
0x34490  ldc.i4.1
0x34491  add
0x34492  stloc.3
0x34493  ldloc.3
0x34494  ldloc.2
0x34495  ldlen
0x34496  conv.i4
0x34497  blt      loc_3427F
0x3449c  ret
```
