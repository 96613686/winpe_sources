# Microsoft.Crm.Workflow.WorkflowErrorVisitor::VisitCreateStep

- ea: `0x23f0`
- end: `0x246a`
- name: `Microsoft.Crm.Workflow.WorkflowErrorVisitor::VisitCreateStep`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x12c0`
- `0x12f0`
- `0x1860`
- `0x1ca0`
- `0x1d80`
- `0x23f0`
- `0x24a0`

## pseudocode

```c

```

## disassembly

```asm
0x23f0  ldarg.1
0x23f1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_EntityName()
0x23f6  brtrue.s loc_2405
0x23f8  ldarg.1
0x23f9  ldc.i4   0x400
0x23fe  ldarg.0
0x23ff  call     void Microsoft.Crm.Workflow.WorkflowErrorHelper::UpdateErrorMap(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase workflowStep, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes errorType, class Microsoft.Crm.Workflow.WorkflowErrorVisitor errorVisitor)
0x2404  ret
0x2405  ldarg.1
0x2406  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_EntityName()
0x240b  ldarg.0
0x240c  call     instance class Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorVisitorContext()
0x2411  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext::get_OrganizationId()
0x2416  call     bool Microsoft.Crm.Workflow.WorkflowErrorHelper::ValidateEntityExists(string entityName, valuetype [mscorlib]System.Guid organizationId)
0x241b  brtrue.s loc_2426
0x241d  ldarg.1
0x241e  ldc.i4.4
0x241f  ldarg.0
0x2420  call     void Microsoft.Crm.Workflow.WorkflowErrorHelper::UpdateErrorMap(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase workflowStep, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes errorType, class Microsoft.Crm.Workflow.WorkflowErrorVisitor errorVisitor)
0x2425  ret
0x2426  ldarg.0
0x2427  call     instance class Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorVisitorContext()
0x242c  ldarg.1
0x242d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_EntityName()
0x2432  ldc.i4.0
0x2433  callvirt instance bool Microsoft.Crm.Workflow.IWorkflowUserPrivilegeCheck::UserHasPrivilege(string entityName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType privilegeType)
0x2438  brtrue.s loc_2446
0x243a  ldarg.1
0x243b  ldc.i4   0x200
0x2440  ldarg.0
0x2441  call     void Microsoft.Crm.Workflow.WorkflowErrorHelper::UpdateErrorMap(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase workflowStep, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes errorType, class Microsoft.Crm.Workflow.WorkflowErrorVisitor errorVisitor)
0x2446  ldarg.1
0x2447  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x244c  brtrue.s loc_245B
0x244e  ldarg.1
0x244f  ldc.i4   0x400
0x2454  ldarg.0
0x2455  call     void Microsoft.Crm.Workflow.WorkflowErrorHelper::UpdateErrorMap(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase workflowStep, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes errorType, class Microsoft.Crm.Workflow.WorkflowErrorVisitor errorVisitor)
0x245a  ret
0x245b  ldarg.0
0x245c  ldarg.1
0x245d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x2462  ldarg.1
0x2463  ldc.i4.1
0x2464  call     instance void Microsoft.Crm.Workflow.WorkflowErrorVisitor::ValidateFields(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification entity, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, bool bCheckRequired)
0x2469  ret
```
