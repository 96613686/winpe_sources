# Microsoft.Crm.Platform.SolutionAwareComponents.UpdateFullComponentInstanceAction::Execute

- ea: `0x3fdb0`
- end: `0x4001a`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.UpdateFullComponentInstanceAction::Execute`
- size: `618`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13990`
- `0x13c30`
- `0x14230`
- `0x1ab10`
- `0x1ae00`
- `0x1af20`
- `0x1ef80`
- `0x222b0`
- `0x35290`
- `0x35b40`
- `0x35b60`
- `0x35ba0`
- `0x35bc0`
- `0x35be0`
- `0x36040`
- `0x37da0`
- `0x37fc0`
- `0x3fdb0`
- `0x66ae0`

## string_xrefs

- `0x3fe64`: `componentstate`
- `0x3fe4e`: `overwritetime`
- `0x3fdf2`: `RowGuidId cannot be empty when updating a component row`

## pseudocode

```c

```

## disassembly

```asm
0x3fdb0  ldarg.0
0x3fdb1  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fdb6  castclass Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance
0x3fdbb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x3fdc0  stloc.0
0x3fdc1  ldloc.0
0x3fdc2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3fdc7  ldarg.1
0x3fdc8  newobj   instance void Microsoft.Crm.Query.ColumnSetExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3fdcd  stloc.1
0x3fdce  ldloc.0
0x3fdcf  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3fdd4  ldarg.1
0x3fdd5  newobj   instance void Microsoft.Crm.Query.ColumnSetExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3fdda  stloc.2
0x3fddb  ldarg.0
0x3fddc  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fde1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3fde6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3fdeb  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3fdf0  brfalse.s loc_3FE02
0x3fdf2  ldstr    aRowguididCanno// "RowGuidId cannot be empty when updating"...
0x3fdf7  ldc.i4   0x80040203
0x3fdfc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3fe01  throw
0x3fe02  ldloc.0
0x3fe03  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3fe08  ldarg.1
0x3fe09  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext orgContext)
0x3fe0e  stloc.3
0x3fe0f  ldloc.3
0x3fe10  ldloc.0
0x3fe11  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x3fe16  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_UniqueIdAttribute()
0x3fe1b  ldc.i4.0
0x3fe1c  ldarg.0
0x3fe1d  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fe22  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3fe27  box      [mscorlib]System.Guid
0x3fe2c  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x3fe31  pop
0x3fe32  ldloc.1
0x3fe33  ldstr    aSupportingsolu// "supportingsolutionid"
0x3fe38  ldarg.0
0x3fe39  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fe3e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x3fe43  box      [mscorlib]System.Guid
0x3fe48  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x3fe4d  ldloc.1
0x3fe4e  ldstr    aOverwritetime_0// "overwritetime"
0x3fe53  ldarg.0
0x3fe54  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fe59  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3fe5e  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x3fe63  ldloc.1
0x3fe64  ldstr    aComponentstate// "componentstate"
0x3fe69  ldarg.0
0x3fe6a  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3fe6f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3fe74  box      [mscorlib]System.Int32
0x3fe79  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x3fe7e  ldloc.0
0x3fe7f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x3fe84  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x3fe89  stloc.s  4
0x3fe8b  br       loc_3FF78
0x3fe90  ldloc.s  4
0x3fe92  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3fe97  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfo
0x3fe9c  stloc.s  5
0x3fe9e  ldloc.0
0x3fe9f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x3fea4  ldloc.s  5
0x3fea6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x3feab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x3feb0  stloc.s  6
0x3feb2  ldloc.s  5
0x3feb4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Value()
0x3feb9  brfalse  loc_3FF78
0x3febe  ldloc.s  6
0x3fec0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsLogical()
0x3fec5  brtrue   loc_3FF78
0x3feca  ldloc.s  6
0x3fecc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsPKAttribute()
0x3fed1  brtrue   loc_3FF78
0x3fed6  ldloc.s  6
0x3fed8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsRowGuidAttribute()
0x3fedd  brtrue   loc_3FF78
0x3fee2  ldloc.s  5
0x3fee4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x3fee9  call     bool Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionHelper::IsSolutionComponentAttribute(string attributeName)
0x3feee  brtrue   loc_3FF78
0x3fef3  ldloc.s  6
0x3fef5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsUnmanagedAttribute()
0x3fefa  brtrue.s loc_3FF1B
0x3fefc  ldloc.s  6
0x3fefe  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsOneWayBooleanAttribute()
0x3ff03  brtrue.s loc_3FF1B
0x3ff05  ldloc.1
0x3ff06  ldloc.s  5
0x3ff08  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x3ff0d  ldloc.s  5
0x3ff0f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Value()
0x3ff14  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x3ff19  br.s     loc_3FF78
0x3ff1b  ldloc.s  6
0x3ff1d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsOneWayBooleanAttribute()
0x3ff22  brfalse.s loc_3FF64
0x3ff24  ldloc.s  5
0x3ff26  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Value()
0x3ff2b  unbox.any [mscorlib]System.Boolean
0x3ff30  brtrue.s loc_3FF4E
0x3ff32  ldarg.1
0x3ff33  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3ff38  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_IsSystemContext()
0x3ff3d  brtrue.s loc_3FF4E
0x3ff3f  ldarg.0
0x3ff40  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3ff45  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x3ff4a  ldc.i4.3
0x3ff4b  and
0x3ff4c  brtrue.s loc_3FF78
0x3ff4e  ldloc.2
0x3ff4f  ldloc.s  5
0x3ff51  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x3ff56  ldloc.s  5
0x3ff58  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Value()
0x3ff5d  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x3ff62  br.s     loc_3FF78
0x3ff64  ldloc.2
0x3ff65  ldloc.s  5
0x3ff67  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x3ff6c  ldloc.s  5
0x3ff6e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Value()
0x3ff73  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x3ff78  ldloc.s  4
0x3ff7a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3ff7f  brtrue   loc_3FE90
0x3ff84  leave.s  loc_3FF9B
0x3ff86  ldloc.s  4
0x3ff88  isinst   [mscorlib]System.IDisposable
0x3ff8d  stloc.s  7
0x3ff8f  ldloc.s  7
0x3ff91  brfalse.s loc_3FF9A
0x3ff93  ldloc.s  7
0x3ff95  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3ff9a  endfinally
0x3ff9b  ldloc.0
0x3ff9c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3ffa1  ldloc.1
0x3ffa2  ldloc.3
0x3ffa3  ldarg.1
0x3ffa4  newobj   instance void Microsoft.Crm.Query.UpdatePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.ColumnSetExpression 'cs', class Microsoft.Crm.Query.FilterExpression criteria, class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x3ffa9  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x3ffae  stloc.s  8
0x3ffb0  ldloc.s  8
0x3ffb2  ldarg.1
0x3ffb3  call     void Microsoft.Crm.Platform.SolutionAwareComponents.UpdateExecutor::ExecuteUpdate(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3ffb8  leave.s  loc_3FFC6
0x3ffba  ldloc.s  8
0x3ffbc  brfalse.s loc_3FFC5
0x3ffbe  ldloc.s  8
0x3ffc0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3ffc5  endfinally
0x3ffc6  ldloc.2
0x3ffc7  callvirt instance class Microsoft.Crm.Query.AttributeExpressionCollection Microsoft.Crm.Query.ColumnSetExpression::get_Attributes()
0x3ffcc  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.AttributeExpression>::get_Count()
0x3ffd1  ldc.i4.0
0x3ffd2  ble.s    loc_40019
0x3ffd4  ldloc.0
0x3ffd5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3ffda  ldarg.1
0x3ffdb  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext orgContext)
0x3ffe0  stloc.3
0x3ffe1  ldloc.3
0x3ffe2  ldloc.0
0x3ffe3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x3ffe8  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddPrimaryKeyCondition(object primaryKeyValue)
0x3ffed  pop
0x3ffee  ldloc.0
0x3ffef  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3fff4  ldloc.2
0x3fff5  ldloc.3
0x3fff6  ldarg.1
0x3fff7  newobj   instance void Microsoft.Crm.Query.UpdatePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.ColumnSetExpression 'cs', class Microsoft.Crm.Query.FilterExpression criteria, class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x3fffc  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x40001  stloc.s  9
0x40003  ldloc.s  9
0x40005  ldarg.1
0x40006  call     void Microsoft.Crm.Platform.SolutionAwareComponents.UpdateExecutor::ExecuteUpdate(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4000b  leave.s  loc_40019
0x4000d  ldloc.s  9
0x4000f  brfalse.s loc_40018
0x40011  ldloc.s  9
0x40013  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40018  endfinally
0x40019  ret
```
