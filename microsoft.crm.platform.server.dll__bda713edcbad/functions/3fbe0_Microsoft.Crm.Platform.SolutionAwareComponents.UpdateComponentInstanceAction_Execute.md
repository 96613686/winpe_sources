# Microsoft.Crm.Platform.SolutionAwareComponents.UpdateComponentInstanceAction::Execute

- ea: `0x3fbe0`
- end: `0x3fcc9`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.UpdateComponentInstanceAction::Execute`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
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
- `0x35ba0`
- `0x35bc0`
- `0x35be0`
- `0x36040`
- `0x37da0`
- `0x3fbe0`

## string_xrefs

- `0x3fc87`: `componentstate`
- `0x3fc71`: `overwritetime`
- `0x3fc15`: `RowGuidId cannot be empty when updating a component row`

## pseudocode

```c

```

## disassembly

```asm
0x3fbe0  ldarg.0
0x3fbe1  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fbe6  castclass Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance
0x3fbeb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x3fbf0  stloc.0
0x3fbf1  ldloc.0
0x3fbf2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3fbf7  ldarg.1
0x3fbf8  newobj   instance void Microsoft.Crm.Query.ColumnSetExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3fbfd  stloc.1
0x3fbfe  ldarg.0
0x3fbff  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fc04  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3fc09  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3fc0e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3fc13  brfalse.s loc_3FC25
0x3fc15  ldstr    aRowguididCanno// "RowGuidId cannot be empty when updating"...
0x3fc1a  ldc.i4   0x80040203
0x3fc1f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3fc24  throw
0x3fc25  ldloc.0
0x3fc26  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3fc2b  ldarg.1
0x3fc2c  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext orgContext)
0x3fc31  stloc.2
0x3fc32  ldloc.2
0x3fc33  ldloc.0
0x3fc34  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x3fc39  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_UniqueIdAttribute()
0x3fc3e  ldc.i4.0
0x3fc3f  ldarg.0
0x3fc40  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fc45  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3fc4a  box      [mscorlib]System.Guid
0x3fc4f  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x3fc54  pop
0x3fc55  ldloc.1
0x3fc56  ldstr    aSupportingsolu// "supportingsolutionid"
0x3fc5b  ldarg.0
0x3fc5c  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fc61  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x3fc66  box      [mscorlib]System.Guid
0x3fc6b  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x3fc70  ldloc.1
0x3fc71  ldstr    aOverwritetime_0// "overwritetime"
0x3fc76  ldarg.0
0x3fc77  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fc7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3fc81  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x3fc86  ldloc.1
0x3fc87  ldstr    aComponentstate// "componentstate"
0x3fc8c  ldarg.0
0x3fc8d  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fc92  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3fc97  box      [mscorlib]System.Int32
0x3fc9c  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x3fca1  ldloc.0
0x3fca2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3fca7  ldloc.1
0x3fca8  ldloc.2
0x3fca9  ldarg.1
0x3fcaa  newobj   instance void Microsoft.Crm.Query.UpdatePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.ColumnSetExpression 'cs', class Microsoft.Crm.Query.FilterExpression criteria, class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x3fcaf  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x3fcb4  stloc.3
0x3fcb5  ldloc.3
0x3fcb6  ldarg.1
0x3fcb7  call     void Microsoft.Crm.Platform.SolutionAwareComponents.UpdateExecutor::ExecuteUpdate(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3fcbc  leave.s  loc_3FCC8
0x3fcbe  ldloc.3
0x3fcbf  brfalse.s loc_3FCC7
0x3fcc1  ldloc.3
0x3fcc2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3fcc7  endfinally
0x3fcc8  ret
```
