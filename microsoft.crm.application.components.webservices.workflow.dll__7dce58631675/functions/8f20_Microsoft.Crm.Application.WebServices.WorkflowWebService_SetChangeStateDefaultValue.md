# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChangeStateDefaultValue

- ea: `0x8f20`
- end: `0x9163`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChangeStateDefaultValue`
- size: `579`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a50`
- `0x5ac0`

## callees

- `0x8f20`

## pseudocode

```c

```

## disassembly

```asm
0x8f20  ldnull
0x8f21  stloc.0
0x8f22  ldarg.2
0x8f23  call     bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::IsGlobalCustomOperation(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x8f28  brtrue   loc_9036
0x8f2d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8f32  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x8f37  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8f3c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8f41  ldarg.2
0x8f42  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x8f47  ldc.i4.1
0x8f48  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8f4d  stloc.2
0x8f4e  ldloc.2
0x8f4f  ldc.i4.2
0x8f50  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowUserPrivilegeCheck::.ctor()
0x8f55  call     bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.StepControlHelper::IsValidEntityForControl(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.StepControlType, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowUserPrivilegeCheck)
0x8f5a  brfalse.s loc_8F83
0x8f5c  ldarg.1
0x8f5d  ldarg.2
0x8f5e  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x8f63  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x8f68  ldloc.2
0x8f69  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x8f6e  ldstr    aStatecode// "statecode"
0x8f73  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x8f78  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x8f7d  stloc.0
0x8f7e  br       loc_9036
0x8f83  ldloc.2
0x8f84  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesFrom()
0x8f89  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x8f8e  stloc.3
0x8f8f  br       loc_9015
0x8f94  ldloc.3
0x8f95  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8f9a  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship
0x8f9f  stloc.s  4
0x8fa1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8fa6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x8fab  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8fb0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8fb5  ldloc.s  4
0x8fb7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x8fbc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x8fc1  ldc.i4.1
0x8fc2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8fc7  stloc.s  5
0x8fc9  ldloc.s  5
0x8fcb  ldc.i4.2
0x8fcc  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowUserPrivilegeCheck::.ctor()
0x8fd1  call     bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.StepControlHelper::IsValidEntityForControl(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.StepControlType, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowUserPrivilegeCheck)
0x8fd6  brfalse.s loc_9015
0x8fd8  ldarg.1
0x8fd9  ldarg.2
0x8fda  ldloc.s  4
0x8fdc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x8fe1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8fe6  ldloc.s  4
0x8fe8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x8fed  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x8ff2  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x8ff7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x8ffc  ldloc.s  5
0x8ffe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x9003  ldstr    aStatecode// "statecode"
0x9008  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x900d  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x9012  stloc.0
0x9013  leave.s  loc_9036
0x9015  ldloc.3
0x9016  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x901b  brtrue   loc_8F94
0x9020  leave.s  loc_9036
0x9022  ldloc.3
0x9023  isinst   [mscorlib]System.IDisposable
0x9028  stloc.s  6
0x902a  ldloc.s  6
0x902c  brfalse.s loc_9035
0x902e  ldloc.s  6
0x9030  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9035  endfinally
0x9036  ldloc.0
0x9037  brtrue   loc_90F8
0x903c  ldarg.2
0x903d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x9042  ldarg.1
0x9043  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataSourceCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetDataSourceForStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x9048  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IDataSource> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataSourceCollection::GetEnumerator()
0x904d  stloc.s  7
0x904f  br       loc_90DE
0x9054  ldloc.s  7
0x9056  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IDataSource>::get_Current()
0x905b  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityDataSource
0x9060  stloc.s  8
0x9062  ldloc.s  8
0x9064  brfalse.s loc_90DE
0x9066  ldloc.s  8
0x9068  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityDataSource::get_EntitySource()
0x906d  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep
0x9072  stloc.s  9
0x9074  ldloc.s  9
0x9076  brfalse.s loc_90DE
0x9078  ldloc.s  9
0x907a  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x907f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9084  brtrue.s loc_90DE
0x9086  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x908b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9090  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9095  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x909a  ldloc.s  9
0x909c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x90a1  ldc.i4.1
0x90a2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x90a7  stloc.s  0xA
0x90a9  ldloc.s  0xA
0x90ab  ldc.i4.2
0x90ac  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowUserPrivilegeCheck::.ctor()
0x90b1  call     bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.StepControlHelper::IsValidEntityForControl(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.StepControlType, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowUserPrivilegeCheck)
0x90b6  brfalse.s loc_90DE
0x90b8  ldarg.1
0x90b9  ldloc.s  9
0x90bb  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep)
0x90c0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x90c5  ldloc.s  0xA
0x90c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x90cc  ldstr    aStatecode// "statecode"
0x90d1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x90d6  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x90db  stloc.0
0x90dc  leave.s  loc_90F8
0x90de  ldloc.s  7
0x90e0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x90e5  brtrue   loc_9054
0x90ea  leave.s  loc_90F8
0x90ec  ldloc.s  7
0x90ee  brfalse.s loc_90F7
0x90f0  ldloc.s  7
0x90f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x90f7  endfinally
0x90f8  ldloc.0
0x90f9  brtrue.s loc_910B
0x90fb  ldstr    aNoEntitiesAvai_0// "No entities available for changing stat"...
0x9100  ldstr    aEntity// "entity"
0x9105  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x910a  throw
0x910b  ldloc.0
0x910c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStateOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata::get_StateOptions()
0x9111  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::GetEnumerator()
0x9116  stloc.1
0x9117  ldloc.1
0x9118  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x911d  pop
0x911e  ldarg.1
0x911f  ldarg.2
0x9120  ldloc.1
0x9121  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9126  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption
0x912b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x9130  box      [mscorlib]System.Int32
0x9135  ldc.i4.5
0x9136  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x913b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::set_State(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x9140  ldarg.1
0x9141  ldarg.2
0x9142  ldloc.1
0x9143  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9148  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption
0x914d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption::get_DefaultStatus()
0x9152  box      [mscorlib]System.Int32
0x9157  ldc.i4.5
0x9158  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x915d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::set_Status(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x9162  ret
```
