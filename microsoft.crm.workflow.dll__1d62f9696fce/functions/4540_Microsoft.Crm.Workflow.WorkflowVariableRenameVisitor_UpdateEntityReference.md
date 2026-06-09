# Microsoft.Crm.Workflow.WorkflowVariableRenameVisitor::UpdateEntityReference

- ea: `0x4540`
- end: `0x45a5`
- name: `Microsoft.Crm.Workflow.WorkflowVariableRenameVisitor::UpdateEntityReference`
- size: `101`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3ef0`
- `0x3f20`
- `0x3f50`
- `0x3fc0`
- `0x4050`
- `0x41b0`

## callees

- `0x4540`

## pseudocode

```c

```

## disassembly

```asm
0x4540  ldarg.1
0x4541  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep
0x4546  stloc.0
0x4547  ldloc.0
0x4548  brfalse.s loc_45A3
0x454a  ldloc.0
0x454b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::get_Step()
0x4550  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4555  ldtoken  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep
0x455a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x455f  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x4564  brfalse.s loc_45A3
0x4566  ldloc.0
0x4567  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_ParameterName()
0x456c  ldarg.0
0x456d  ldfld    string Microsoft.Crm.Workflow.WorkflowVariableRenameVisitor::_currentName
0x4572  ldstr    asc_3068C// "#"
0x4577  ldloc.0
0x4578  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x457d  call     string [mscorlib]System.String::Concat(string, string, string)
0x4582  ldc.i4.4
0x4583  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x4588  brfalse.s loc_45A3
0x458a  ldloc.0
0x458b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_Workflow()
0x4590  ldloc.0
0x4591  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x4596  ldarg.0
0x4597  ldfld    string Microsoft.Crm.Workflow.WorkflowVariableRenameVisitor::_newName
0x459c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x45a1  starg.s  1
0x45a3  ldarg.1
0x45a4  ret
```
