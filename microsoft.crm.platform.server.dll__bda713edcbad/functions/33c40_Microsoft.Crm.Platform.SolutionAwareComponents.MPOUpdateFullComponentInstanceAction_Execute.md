# Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateFullComponentInstanceAction::Execute

- ea: `0x33c40`
- end: `0x33dd1`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateFullComponentInstanceAction::Execute`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x33c40`
- `0x33de0`
- `0x34810`
- `0x34930`
- `0x35b60`
- `0x35ba0`
- `0x35bc0`
- `0x35be0`
- `0x36110`
- `0x37da0`
- `0x42ed0`
- `0x45fe0`
- `0x460c0`
- `0x46190`
- `0x46f40`
- `0x47290`
- `0x66ae0`

## string_xrefs

- `0x33c8d`: `RowGuidId cannot be empty when updating a component row`
- `0x33ceb`: `Updating full data in a row for metadata entity {0}; {1}: {2}; ComponentState: {3}; OverwriteTime: {4}; SupportSolutionId: {5}`

## pseudocode

```c

```

## disassembly

```asm
0x33c40  ldarg.0
0x33c41  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33c46  castclass Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance
0x33c4b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance::get_Entity()
0x33c50  stloc.0
0x33c51  ldarg.0
0x33c52  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33c57  ldloc.0
0x33c58  call     void Microsoft.Crm.Platform.SolutionAwareComponents.MPOComponentActionHelper::SetInstancePropertiesOnEntity(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity metadataEntity)
0x33c5d  ldloc.0
0x33c5e  ldstr    aSolutionid_0// "solutionid"
0x33c63  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::Remove(string)
0x33c68  ldarg.0
0x33c69  ldloc.0
0x33c6a  ldarg.1
0x33c6b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x33c70  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateFullComponentInstanceAction::TransferUnmanagedAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x33c75  stloc.1
0x33c76  ldarg.0
0x33c77  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33c7c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x33c81  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33c86  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x33c8b  brfalse.s loc_33C9D
0x33c8d  ldstr    aRowguididCanno// "RowGuidId cannot be empty when updating"...
0x33c92  ldc.i4   0x80040203
0x33c97  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x33c9c  throw
0x33c9d  ldloc.0
0x33c9e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x33ca3  ldarg.1
0x33ca4  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression::.ctor(string metadataEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33ca9  stloc.2
0x33caa  ldloc.2
0x33cab  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression::get_Conditions()
0x33cb0  ldloc.0
0x33cb1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x33cb6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x33cbb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x33cc0  ldarg.0
0x33cc1  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33cc6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x33ccb  box      [mscorlib]System.Guid
0x33cd0  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, object value)
0x33cd5  ldloc.0
0x33cd6  ldloc.2
0x33cd7  ldarg.1
0x33cd8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x33cdd  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleUpdatePlan::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression filter, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x33ce2  stloc.3
0x33ce3  ldarg.1
0x33ce4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x33ce9  ldc.i4.s 0x14
0x33ceb  ldstr    aUpdatingFullDa// "Updating full data in a row for metadat"...
0x33cf0  ldc.i4.6
0x33cf1  newarr   [mscorlib]System.Object
0x33cf6  dup
0x33cf7  ldc.i4.0
0x33cf8  ldloc.0
0x33cf9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x33cfe  stelem.ref
0x33cff  dup
0x33d00  ldc.i4.1
0x33d01  ldloc.0
0x33d02  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x33d07  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x33d0c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x33d11  stelem.ref
0x33d12  dup
0x33d13  ldc.i4.2
0x33d14  ldloc.0
0x33d15  ldloc.0
0x33d16  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x33d1b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x33d20  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x33d25  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x33d2a  stelem.ref
0x33d2b  dup
0x33d2c  ldc.i4.3
0x33d2d  ldarg.0
0x33d2e  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33d33  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x33d38  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x33d3d  stelem.ref
0x33d3e  dup
0x33d3f  ldc.i4.4
0x33d40  ldarg.0
0x33d41  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33d46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x33d4b  stelem.ref
0x33d4c  dup
0x33d4d  ldc.i4.5
0x33d4e  ldarg.0
0x33d4f  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33d54  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x33d59  box      [mscorlib]System.Guid
0x33d5e  stelem.ref
0x33d5f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x33d64  ldloc.3
0x33d65  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryPlan::get_Command()
0x33d6a  stloc.s  4
0x33d6c  ldloc.s  4
0x33d6e  ldarg.1
0x33d6f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x33d74  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x33d79  pop
0x33d7a  leave.s  loc_33D88
0x33d7c  ldloc.s  4
0x33d7e  brfalse.s loc_33D87
0x33d80  ldloc.s  4
0x33d82  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33d87  endfinally
0x33d88  ldloc.1
0x33d89  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataAttributes()
0x33d8e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection::get_Count()
0x33d93  ldc.i4.0
0x33d94  ble.s    loc_33DBE
0x33d96  ldloc.0
0x33d97  ldloc.0
0x33d98  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x33d9d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x33da2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x33da7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x33dac  brfalse.s loc_33DBE
0x33dae  ldstr    aPrimaryidAttri// "PrimaryId attribute cannot be empty whe"...
0x33db3  ldc.i4   0x80040203
0x33db8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x33dbd  throw
0x33dbe  ldloc.0
0x33dbf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Moniker()
0x33dc4  ldloc.1
0x33dc5  ldarg.1
0x33dc6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x33dcb  call     void Microsoft.Crm.Platform.SolutionAwareComponents.MPOActionHelper::UpdateUnmanagedAttributesForEntityIfNecessary(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityToUpdateAllColumns, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x33dd0  ret
```
