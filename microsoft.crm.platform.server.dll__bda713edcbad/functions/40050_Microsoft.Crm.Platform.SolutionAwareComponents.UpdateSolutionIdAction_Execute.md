# Microsoft.Crm.Platform.SolutionAwareComponents.UpdateSolutionIdAction::Execute

- ea: `0x40050`
- end: `0x40188`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.UpdateSolutionIdAction::Execute`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13990`
- `0x13c30`
- `0x1ab10`
- `0x1ae00`
- `0x1ef80`
- `0x222b0`
- `0x35290`
- `0x35b60`
- `0x35b80`
- `0x36040`
- `0x37da0`
- `0x40050`
- `0x42ed0`
- `0x66ae0`
- `0x67920`

## string_xrefs

- `0x40067`: `RowGuidId cannot be empty when updating a component row`
- `0x4010c`: `update SolutionComponentBase set SolutionId = @NewSolutionId where ObjectId = @ObjectId and SolutionId = @OldSolutionId`

## pseudocode

```c

```

## disassembly

```asm
0x40050  ldarg.0
0x40051  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x40056  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x4005b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40060  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x40065  brfalse.s loc_40077
0x40067  ldstr    aRowguididCanno// "RowGuidId cannot be empty when updating"...
0x4006c  ldc.i4   0x80040203
0x40071  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x40076  throw
0x40077  ldarg.0
0x40078  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x4007d  castclass Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance
0x40082  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x40087  stloc.0
0x40088  ldloc.0
0x40089  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x4008e  ldarg.1
0x4008f  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext orgContext)
0x40094  stloc.1
0x40095  ldloc.1
0x40096  ldloc.0
0x40097  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x4009c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_UniqueIdAttribute()
0x400a1  ldc.i4.0
0x400a2  ldarg.0
0x400a3  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x400a8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x400ad  box      [mscorlib]System.Guid
0x400b2  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x400b7  pop
0x400b8  ldloc.0
0x400b9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x400be  ldarg.1
0x400bf  newobj   instance void Microsoft.Crm.Query.ColumnSetExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x400c4  stloc.2
0x400c5  ldloc.2
0x400c6  ldstr    aSolutionid_0// "solutionid"
0x400cb  ldarg.0
0x400cc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.UpdateSolutionIdAction::_newSolutionId
0x400d1  box      [mscorlib]System.Guid
0x400d6  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x400db  ldloc.0
0x400dc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x400e1  ldloc.2
0x400e2  ldloc.1
0x400e3  ldarg.1
0x400e4  newobj   instance void Microsoft.Crm.Query.UpdatePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.ColumnSetExpression 'cs', class Microsoft.Crm.Query.FilterExpression criteria, class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x400e9  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x400ee  stloc.3
0x400ef  ldloc.3
0x400f0  ldarg.1
0x400f1  call     void Microsoft.Crm.Platform.SolutionAwareComponents.UpdateExecutor::ExecuteUpdate(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x400f6  leave.s  loc_40102
0x400f8  ldloc.3
0x400f9  brfalse.s loc_40101
0x400fb  ldloc.3
0x400fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40101  endfinally
0x40102  ldarg.1
0x40103  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x40108  stloc.s  4
0x4010a  ldloc.s  4
0x4010c  ldstr    aUpdateSolution// "update SolutionComponentBase set Soluti"...
0x40111  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x40116  ldloc.s  4
0x40118  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4011d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x40122  dup
0x40123  ldstr    aNewsolutionid// "@NewSolutionId"
0x40128  ldarg.0
0x40129  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.UpdateSolutionIdAction::_newSolutionId
0x4012e  box      [mscorlib]System.Guid
0x40133  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x40138  pop
0x40139  dup
0x4013a  ldstr    aObjectid_3// "@ObjectId"
0x4013f  ldarg.0
0x40140  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.UpdateSolutionIdAction::_objectId
0x40145  box      [mscorlib]System.Guid
0x4014a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4014f  pop
0x40150  ldstr    aOldsolutionid// "@OldSolutionId"
0x40155  ldarg.0
0x40156  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x4015b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x40160  box      [mscorlib]System.Guid
0x40165  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4016a  pop
0x4016b  ldloc.s  4
0x4016d  ldarg.1
0x4016e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x40173  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x40178  pop
0x40179  leave.s  loc_40187
0x4017b  ldloc.s  4
0x4017d  brfalse.s loc_40186
0x4017f  ldloc.s  4
0x40181  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40186  endfinally
0x40187  ret
```
