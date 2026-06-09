# Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateComponentInstanceAction::Execute

- ea: `0x33780`
- end: `0x338c2`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateComponentInstanceAction::Execute`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x33780`
- `0x34810`
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

- `0x337ca`: `RowGuidId cannot be empty when updating a component row`
- `0x33828`: `Updating only component instance data in a row for metadata entity {0}; {1}: {2}; ComponentState: {3}; OverwriteTime: {4}; SupportSolutionId: {5}`

## pseudocode

```c

```

## disassembly

```asm
0x33780  ldarg.0
0x33781  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33786  castclass Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance
0x3378b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance::get_Entity()
0x33790  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x33795  ldarg.1
0x33796  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3379b  stloc.0
0x3379c  ldarg.0
0x3379d  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x337a2  ldloc.0
0x337a3  call     void Microsoft.Crm.Platform.SolutionAwareComponents.MPOComponentActionHelper::SetInstancePropertiesOnEntity(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity metadataEntity)
0x337a8  ldloc.0
0x337a9  ldstr    aSolutionid_0// "solutionid"
0x337ae  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::Remove(string)
0x337b3  ldarg.0
0x337b4  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x337b9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x337be  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x337c3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x337c8  brfalse.s loc_337DA
0x337ca  ldstr    aRowguididCanno// "RowGuidId cannot be empty when updating"...
0x337cf  ldc.i4   0x80040203
0x337d4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x337d9  throw
0x337da  ldloc.0
0x337db  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x337e0  ldarg.1
0x337e1  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression::.ctor(string metadataEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x337e6  stloc.1
0x337e7  ldloc.1
0x337e8  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression::get_Conditions()
0x337ed  ldloc.0
0x337ee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x337f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x337f8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x337fd  ldarg.0
0x337fe  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33803  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x33808  box      [mscorlib]System.Guid
0x3380d  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, object value)
0x33812  ldloc.0
0x33813  ldloc.1
0x33814  ldarg.1
0x33815  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3381a  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleUpdatePlan::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression filter, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x3381f  stloc.2
0x33820  ldarg.1
0x33821  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x33826  ldc.i4.s 0x14
0x33828  ldstr    aUpdatingOnlyCo// "Updating only component instance data i"...
0x3382d  ldc.i4.6
0x3382e  newarr   [mscorlib]System.Object
0x33833  dup
0x33834  ldc.i4.0
0x33835  ldloc.0
0x33836  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x3383b  stelem.ref
0x3383c  dup
0x3383d  ldc.i4.1
0x3383e  ldloc.0
0x3383f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x33844  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x33849  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x3384e  stelem.ref
0x3384f  dup
0x33850  ldc.i4.2
0x33851  ldloc.0
0x33852  ldloc.0
0x33853  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x33858  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x3385d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x33862  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x33867  stelem.ref
0x33868  dup
0x33869  ldc.i4.3
0x3386a  ldarg.0
0x3386b  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33870  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x33875  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x3387a  stelem.ref
0x3387b  dup
0x3387c  ldc.i4.4
0x3387d  ldarg.0
0x3387e  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33883  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x33888  stelem.ref
0x33889  dup
0x3388a  ldc.i4.5
0x3388b  ldarg.0
0x3388c  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33891  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x33896  box      [mscorlib]System.Guid
0x3389b  stelem.ref
0x3389c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x338a1  ldloc.2
0x338a2  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryPlan::get_Command()
0x338a7  stloc.3
0x338a8  ldloc.3
0x338a9  ldarg.1
0x338aa  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x338af  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x338b4  pop
0x338b5  leave.s  loc_338C1
0x338b7  ldloc.3
0x338b8  brfalse.s loc_338C0
0x338ba  ldloc.3
0x338bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x338c0  endfinally
0x338c1  ret
```
