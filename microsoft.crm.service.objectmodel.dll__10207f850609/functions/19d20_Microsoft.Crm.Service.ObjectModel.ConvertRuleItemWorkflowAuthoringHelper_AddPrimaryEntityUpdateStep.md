# Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::AddPrimaryEntityUpdateStep

- ea: `0x19d20`
- end: `0x19e7f`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::AddPrimaryEntityUpdateStep`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x19b80`

## callees

- `0x19d20`

## pseudocode

```c

```

## disassembly

```asm
0x19d20  ldarg.1
0x19d21  brfalse  loc_19E7E
0x19d26  ldarg.1
0x19d27  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep)
0x19d2c  stloc.0
0x19d2d  ldarg.0
0x19d2e  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_organizationContext
0x19d33  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19d38  ldarg.2
0x19d39  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x19d3e  ldc.i4.1
0x19d3f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x19d44  ldarg.0
0x19d45  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_organizationContext
0x19d4a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19d4f  ldarg.1
0x19d50  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_EntityName()
0x19d55  ldc.i4.1
0x19d56  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x19d5b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x19d60  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x19d65  stloc.1
0x19d66  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesFrom()
0x19d6b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x19d70  stloc.2
0x19d71  br       loc_19E5D
0x19d76  ldloc.2
0x19d77  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19d7c  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship
0x19d81  stloc.3
0x19d82  ldloc.3
0x19d83  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x19d88  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x19d8d  ldarg.1
0x19d8e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_EntityName()
0x19d93  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19d98  brfalse  loc_19E5D
0x19d9d  ldloc.3
0x19d9e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedAttribute()
0x19da3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x19da8  ldloc.1
0x19da9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19dae  brfalse  loc_19E5D
0x19db3  ldloc.3
0x19db4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x19db9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x19dbe  ldstr    aRegardingobjec// "regardingobjectid"
0x19dc3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19dc8  brfalse  loc_19E5D
0x19dcd  ldloc.0
0x19dce  ldloc.1
0x19dcf  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x19dd4  stloc.s  4
0x19dd6  ldarg.2
0x19dd7  ldc.i4.0
0x19dd8  ldc.i4.1
0x19dd9  newarr   [mscorlib]System.Object
0x19dde  dup
0x19ddf  ldc.i4.0
0x19de0  ldloc.s  4
0x19de2  stelem.ref
0x19de3  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x19de8  stloc.s  5
0x19dea  ldarg.2
0x19deb  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x19df0  stloc.s  6
0x19df2  ldloc.s  6
0x19df4  ldstr    asc_1EEAE// ""
0x19df9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Description(string)
0x19dfe  ldarg.1
0x19dff  ldc.i4.1
0x19e00  ldloc.s  6
0x19e02  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x19e07  ldloc.s  6
0x19e09  ldarg.2
0x19e0a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x19e0f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x19e14  ldloc.s  6
0x19e16  ldarg.2
0x19e17  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x19e1c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x19e21  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_EntitySpec(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x19e26  ldloc.s  6
0x19e28  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x19e2d  ldstr    aRegardingobjec// "regardingobjectid"
0x19e32  ldloc.s  5
0x19e34  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x19e39  ldarg.2
0x19e3a  ldstr    aB4a31b47Bf1d48// "B4A31B47-BF1D-48CD-97F5-4482294FAEC7"
0x19e3f  ldc.i4.s 0xE
0x19e41  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x19e46  stloc.s  7
0x19e48  ldloc.s  6
0x19e4a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x19e4f  ldstr    aActivityadditi// "activityadditionalparams"
0x19e54  ldloc.s  7
0x19e56  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x19e5b  leave.s  loc_19E7E
0x19e5d  ldloc.2
0x19e5e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19e63  brtrue   loc_19D76
0x19e68  leave.s  loc_19E7E
0x19e6a  ldloc.2
0x19e6b  isinst   [mscorlib]System.IDisposable
0x19e70  stloc.s  8
0x19e72  ldloc.s  8
0x19e74  brfalse.s loc_19E7D
0x19e76  ldloc.s  8
0x19e78  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19e7d  endfinally
0x19e7e  ret
```
