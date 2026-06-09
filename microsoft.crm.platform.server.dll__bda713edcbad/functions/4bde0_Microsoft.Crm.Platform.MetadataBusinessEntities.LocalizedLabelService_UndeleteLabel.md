# Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::UndeleteLabel

- ea: `0x4bde0`
- end: `0x4bf25`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::UndeleteLabel`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x7a0e0`

## callees

- `0x32fb0`
- `0x33770`
- `0x35680`
- `0x356e0`
- `0x35b60`
- `0x35bc0`
- `0x35bf0`
- `0x36170`
- `0x37d90`
- `0x42740`
- `0x42ed0`
- `0x45fe0`
- `0x460c0`
- `0x46190`
- `0x46cc0`
- `0x46f40`
- `0x4bde0`
- `0x66ae0`

## string_xrefs

- `0x4be08`: `Top instance is in an invalid state to undelete a label.  Expected: {0} or {1}; Actual: {2}`
- `0x4beec`: `Expected a component that is marked as Deleted to contain other instances that are not deleted`

## pseudocode

```c

```

## disassembly

```asm
0x4bde0  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.MetadataComponentStateLoader::.ctor()
0x4bde5  ldc.i4.7
0x4bde6  ldarg.1
0x4bde7  ldc.i4.0
0x4bde8  ldarg.2
0x4bde9  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::Load(int32 componentType, valuetype [mscorlib]System.Guid id, valuetype Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoadOption loadOption, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4bdee  stloc.0
0x4bdef  ldloc.0
0x4bdf0  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x4bdf5  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x4bdfa  stloc.1
0x4bdfb  ldloc.1
0x4bdfc  ldc.i4.2
0x4bdfd  beq.s    loc_4BE3E
0x4bdff  ldloc.1
0x4be00  ldc.i4.3
0x4be01  beq.s    loc_4BE3E
0x4be03  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be08  ldstr    aTopInstanceIsI// "Top instance is in an invalid state to "...
0x4be0d  ldc.i4.3
0x4be0e  newarr   [mscorlib]System.Object
0x4be13  dup
0x4be14  ldc.i4.0
0x4be15  ldc.i4.2
0x4be16  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x4be1b  stelem.ref
0x4be1c  dup
0x4be1d  ldc.i4.1
0x4be1e  ldc.i4.3
0x4be1f  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x4be24  stelem.ref
0x4be25  dup
0x4be26  ldc.i4.2
0x4be27  ldloc.1
0x4be28  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x4be2d  stelem.ref
0x4be2e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4be33  ldc.i4   0x8004F003
0x4be38  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4be3d  throw
0x4be3e  ldnull
0x4be3f  stloc.2
0x4be40  ldloc.0
0x4be41  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x4be46  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x4be4b  ldc.i4.1
0x4be4c  sub
0x4be4d  stloc.3
0x4be4e  br       loc_4BEE2
0x4be53  ldloc.0
0x4be54  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x4be59  ldloc.3
0x4be5a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x4be5f  stloc.2
0x4be60  ldloc.0
0x4be61  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x4be66  ldloc.3
0x4be67  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x4be6c  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x4be71  stloc.s  4
0x4be73  ldloc.s  4
0x4be75  ldc.i4.2
0x4be76  beq.s    loc_4BE7D
0x4be78  ldloc.s  4
0x4be7a  ldc.i4.3
0x4be7b  bne.un.s loc_4BEE9
0x4be7d  ldstr    aLocalizedlabel// "LocalizedLabel"
0x4be82  ldarg.2
0x4be83  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression::.ctor(string metadataEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4be88  dup
0x4be89  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression::get_Conditions()
0x4be8e  ldstr    aLocalizedlabel_1// "localizedlabelrowid"
0x4be93  ldloc.0
0x4be94  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x4be99  ldloc.3
0x4be9a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x4be9f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x4bea4  box      [mscorlib]System.Guid
0x4bea9  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, object value)
0x4beae  ldarg.2
0x4beaf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4beb4  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleDeletePlan::.ctor(class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleFilterExpression filter, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4beb9  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryPlan::get_Command()
0x4bebe  stloc.s  5
0x4bec0  ldloc.s  5
0x4bec2  ldarg.2
0x4bec3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4bec8  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4becd  pop
0x4bece  leave.s  loc_4BEDC
0x4bed0  ldloc.s  5
0x4bed2  brfalse.s loc_4BEDB
0x4bed4  ldloc.s  5
0x4bed6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4bedb  endfinally
0x4bedc  ldnull
0x4bedd  stloc.2
0x4bede  ldloc.3
0x4bedf  ldc.i4.1
0x4bee0  sub
0x4bee1  stloc.3
0x4bee2  ldloc.3
0x4bee3  ldc.i4.0
0x4bee4  bge      loc_4BE53
0x4bee9  ldloc.2
0x4beea  brtrue.s loc_4BEFC
0x4beec  ldstr    aExpectedACompo// "Expected a component that is marked as "...
0x4bef1  ldc.i4   0x8004F004
0x4bef6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4befb  throw
0x4befc  ldloc.2
0x4befd  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x4bf02  ldc.i4.1
0x4bf03  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x4bf08  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_OverwriteTime(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime value)
0x4bf0d  ldarg.2
0x4bf0e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4bf13  call     void Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataTimeStampUtility::TryRegisterEventForInsertMetadataTimestamp(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4bf18  ldloc.2
0x4bf19  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.MPOUpdateComponentInstanceAction::.ctor(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x4bf1e  ldarg.2
0x4bf1f  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::Execute(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4bf24  ret
```
