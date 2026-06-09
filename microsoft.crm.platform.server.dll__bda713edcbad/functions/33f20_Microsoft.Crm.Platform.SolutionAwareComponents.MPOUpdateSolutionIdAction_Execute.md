# Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateSolutionIdAction::Execute

- ea: `0x33f20`
- end: `0x340d3`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateSolutionIdAction::Execute`
- size: `435`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x33f20`
- `0x35b60`
- `0x35b80`
- `0x36110`
- `0x37da0`
- `0x42ed0`
- `0x45fe0`
- `0x460c0`
- `0x46190`
- `0x46f40`
- `0x47290`
- `0x66ae0`
- `0x67920`

## string_xrefs

- `0x33f37`: `RowGuidId cannot be empty when updating a component row`
- `0x34057`: `update SolutionComponentBase set SolutionId = @NewSolutionId where ObjectId = @ObjectId and SolutionId = @OldSolutionId`

## pseudocode

```c

```

## disassembly

```asm
0x33f20  ldarg.0
0x33f21  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33f26  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x33f2b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33f30  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x33f35  brfalse.s loc_33F47
0x33f37  ldstr    aRowguididCanno// "RowGuidId cannot be empty when updating"...
0x33f3c  ldc.i4   0x80040203
0x33f41  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x33f46  throw
0x33f47  ldarg.0
0x33f48  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33f4d  castclass Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance
0x33f52  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance::get_Entity()
0x33f57  stloc.0
0x33f58  ldloc.0
0x33f59  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x33f5e  ldarg.1
0x33f5f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x33f64  dup
0x33f65  ldstr    aSolutionid_0// "solutionid"
0x33f6a  ldarg.0
0x33f6b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateSolutionIdAction::_newSolutionId
0x33f70  box      [mscorlib]System.Guid
0x33f75  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x33f7a  ldloc.0
0x33f7b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x33f80  ldarg.1
0x33f81  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression::.ctor(string metadataEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33f86  stloc.1
0x33f87  ldloc.1
0x33f88  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression::get_Conditions()
0x33f8d  ldloc.0
0x33f8e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x33f93  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x33f98  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x33f9d  ldarg.0
0x33f9e  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x33fa3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x33fa8  box      [mscorlib]System.Guid
0x33fad  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, object value)
0x33fb2  ldloc.1
0x33fb3  ldarg.1
0x33fb4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x33fb9  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleUpdatePlan::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression filter, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x33fbe  stloc.2
0x33fbf  ldarg.1
0x33fc0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x33fc5  ldc.i4.s 0x14
0x33fc7  ldstr    aUpdatingSoluti// "Updating solution id in a row for metad"...
0x33fcc  ldc.i4.5
0x33fcd  newarr   [mscorlib]System.Object
0x33fd2  dup
0x33fd3  ldc.i4.0
0x33fd4  ldloc.0
0x33fd5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityName()
0x33fda  stelem.ref
0x33fdb  dup
0x33fdc  ldc.i4.1
0x33fdd  ldloc.0
0x33fde  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x33fe3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x33fe8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x33fed  stelem.ref
0x33fee  dup
0x33fef  ldc.i4.2
0x33ff0  ldloc.0
0x33ff1  ldloc.0
0x33ff2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x33ff7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x33ffc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x34001  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x34006  stelem.ref
0x34007  dup
0x34008  ldc.i4.3
0x34009  ldarg.0
0x3400a  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3400f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x34014  box      [mscorlib]System.Guid
0x34019  stelem.ref
0x3401a  dup
0x3401b  ldc.i4.4
0x3401c  ldarg.0
0x3401d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateSolutionIdAction::_newSolutionId
0x34022  box      [mscorlib]System.Guid
0x34027  stelem.ref
0x34028  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3402d  ldloc.2
0x3402e  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryPlan::get_Command()
0x34033  stloc.3
0x34034  ldloc.3
0x34035  ldarg.1
0x34036  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3403b  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x34040  pop
0x34041  leave.s  loc_3404D
0x34043  ldloc.3
0x34044  brfalse.s loc_3404C
0x34046  ldloc.3
0x34047  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3404c  endfinally
0x3404d  ldarg.1
0x3404e  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x34053  stloc.s  4
0x34055  ldloc.s  4
0x34057  ldstr    aUpdateSolution// "update SolutionComponentBase set Soluti"...
0x3405c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x34061  ldloc.s  4
0x34063  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x34068  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3406d  dup
0x3406e  ldstr    aNewsolutionid// "@NewSolutionId"
0x34073  ldarg.0
0x34074  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateSolutionIdAction::_newSolutionId
0x34079  box      [mscorlib]System.Guid
0x3407e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x34083  pop
0x34084  dup
0x34085  ldstr    aObjectid_3// "@ObjectId"
0x3408a  ldarg.0
0x3408b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateSolutionIdAction::_objectId
0x34090  box      [mscorlib]System.Guid
0x34095  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3409a  pop
0x3409b  ldstr    aOldsolutionid// "@OldSolutionId"
0x340a0  ldarg.0
0x340a1  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x340a6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x340ab  box      [mscorlib]System.Guid
0x340b0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x340b5  pop
0x340b6  ldloc.s  4
0x340b8  ldarg.1
0x340b9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x340be  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x340c3  pop
0x340c4  leave.s  loc_340D2
0x340c6  ldloc.s  4
0x340c8  brfalse.s loc_340D1
0x340ca  ldloc.s  4
0x340cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x340d1  endfinally
0x340d2  ret
```
