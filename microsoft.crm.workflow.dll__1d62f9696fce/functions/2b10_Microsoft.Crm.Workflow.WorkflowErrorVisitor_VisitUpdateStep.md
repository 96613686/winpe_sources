# Microsoft.Crm.Workflow.WorkflowErrorVisitor::VisitUpdateStep

- ea: `0x2b10`
- end: `0x2c23`
- name: `Microsoft.Crm.Workflow.WorkflowErrorVisitor::VisitUpdateStep`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x12c0`
- `0x12f0`
- `0x15e0`
- `0x1ca0`
- `0x1d80`
- `0x2490`
- `0x24a0`
- `0x2b10`
- `0x2f10`
- `0x3680`
- `0x36a0`

## pseudocode

```c

```

## disassembly

```asm
0x2b10  ldarg.1
0x2b11  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x2b16  brfalse  loc_2C22
0x2b1b  ldarg.1
0x2b1c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x2b21  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.InvalidEntity
0x2b26  brfalse.s loc_2B31
0x2b28  ldarg.1
0x2b29  ldc.i4.4
0x2b2a  ldarg.0
0x2b2b  call     void Microsoft.Crm.Workflow.WorkflowErrorHelper::UpdateErrorMap(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase workflowStep, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes errorType, class Microsoft.Crm.Workflow.WorkflowErrorVisitor errorVisitor)
0x2b30  ret
0x2b31  ldarg.1
0x2b32  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x2b37  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity
0x2b3c  brfalse.s loc_2B51
0x2b3e  ldarg.0
0x2b3f  ldarg.1
0x2b40  ldc.i4.1
0x2b41  call     instance bool Microsoft.Crm.Workflow.WorkflowErrorVisitor::ValidateRelationship(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, valuetype Microsoft.Crm.Workflow.StepControlType controlType)
0x2b46  brtrue.s loc_2B51
0x2b48  ldarg.1
0x2b49  ldc.i4.8
0x2b4a  ldarg.0
0x2b4b  call     void Microsoft.Crm.Workflow.WorkflowErrorHelper::UpdateErrorMap(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase workflowStep, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes errorType, class Microsoft.Crm.Workflow.WorkflowErrorVisitor errorVisitor)
0x2b50  ret
0x2b51  ldarg.1
0x2b52  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x2b57  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep
0x2b5c  brfalse.s loc_2B7F
0x2b5e  ldarg.1
0x2b5f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x2b64  ldarg.0
0x2b65  call     instance class Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorVisitorContext()
0x2b6a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext::get_OrganizationId()
0x2b6f  call     bool Microsoft.Crm.Workflow.WorkflowErrorHelper::ValidateEntityValid(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase entity, valuetype [mscorlib]System.Guid organizationId)
0x2b74  brtrue.s loc_2B7F
0x2b76  ldarg.1
0x2b77  ldc.i4.4
0x2b78  ldarg.0
0x2b79  call     void Microsoft.Crm.Workflow.WorkflowErrorHelper::UpdateErrorMap(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase workflowStep, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes errorType, class Microsoft.Crm.Workflow.WorkflowErrorVisitor errorVisitor)
0x2b7e  ret
0x2b7f  ldarg.0
0x2b80  call     instance class Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorVisitorContext()
0x2b85  ldarg.1
0x2b86  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x2b8b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x2b90  ldc.i4.2
0x2b91  callvirt instance bool Microsoft.Crm.Workflow.IWorkflowUserPrivilegeCheck::UserHasPrivilege(string entityName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType privilegeType)
0x2b96  brtrue.s loc_2BA4
0x2b98  ldarg.1
0x2b99  ldc.i4   0x200
0x2b9e  ldarg.0
0x2b9f  call     void Microsoft.Crm.Workflow.WorkflowErrorHelper::UpdateErrorMap(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase workflowStep, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes errorType, class Microsoft.Crm.Workflow.WorkflowErrorVisitor errorVisitor)
0x2ba4  ldarg.0
0x2ba5  ldarg.1
0x2ba6  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x2bab  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x2bb0  ldarg.1
0x2bb1  call     instance bool Microsoft.Crm.Workflow.WorkflowErrorVisitor::ValidatePublicFormExist(string entityName, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step)
0x2bb6  pop
0x2bb7  ldarg.0
0x2bb8  ldarg.1
0x2bb9  ldarg.0
0x2bba  call     instance class Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorVisitorContext()
0x2bbf  newobj   instance void Microsoft.Crm.Workflow.WorkflowExpressionErrorVisitor::.ctor(class Microsoft.Crm.Workflow.WorkflowErrorVisitor visitor, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, class Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext errorVisitorContext)
0x2bc4  stloc.0
0x2bc5  ldc.i4.0
0x2bc6  stloc.1
0x2bc7  br.s     loc_2C01
0x2bc9  ldarg.1
0x2bca  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x2bcf  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::get_Properties()
0x2bd4  ldloc.1
0x2bd5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::get_Item(!!T0)
0x2bda  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::get_Value()
0x2bdf  brfalse.s loc_2BFD
0x2be1  ldloc.0
0x2be2  ldarg.1
0x2be3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x2be8  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::get_Properties()
0x2bed  ldloc.1
0x2bee  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::get_Item(!!T0)
0x2bf3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::get_Value()
0x2bf8  callvirt instance void Microsoft.Crm.Workflow.WorkflowExpressionErrorVisitor::FindErrorsAndUpdateMap(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase expression)
0x2bfd  ldloc.1
0x2bfe  ldc.i4.1
0x2bff  add
0x2c00  stloc.1
0x2c01  ldloc.1
0x2c02  ldarg.1
0x2c03  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x2c08  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::get_Properties()
0x2c0d  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::get_Count()
0x2c12  blt.s    loc_2BC9
0x2c14  ldarg.0
0x2c15  ldarg.1
0x2c16  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x2c1b  ldarg.1
0x2c1c  ldc.i4.0
0x2c1d  call     instance void Microsoft.Crm.Workflow.WorkflowErrorVisitor::ValidateFields(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification entity, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, bool bCheckRequired)
0x2c22  ret
```
