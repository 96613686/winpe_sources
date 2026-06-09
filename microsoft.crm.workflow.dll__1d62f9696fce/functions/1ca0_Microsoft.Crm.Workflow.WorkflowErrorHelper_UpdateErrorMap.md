# Microsoft.Crm.Workflow.WorkflowErrorHelper::UpdateErrorMap

- ea: `0x1ca0`
- end: `0x1d39`
- name: `Microsoft.Crm.Workflow.WorkflowErrorHelper::UpdateErrorMap`
- size: `153`
- prototype: ``
- caller_count: `37`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1df0`
- `0x1f90`
- `0x2060`
- `0x2130`
- `0x2270`
- `0x23a0`
- `0x23f0`
- `0x2470`
- `0x24a0`
- `0x2590`
- `0x26f0`
- `0x2730`
- `0x2770`
- `0x2950`
- `0x2a00`
- `0x2aa0`
- `0x2b10`
- `0x2c40`
- `0x2d90`
- `0x2dd0`
- `0x2df0`
- `0x2e20`
- `0x2e70`
- `0x3190`
- `0x32c0`
- `0x3310`
- `0x3340`
- `0x3390`
- `0x3470`
- `0x3570`
- `0x36b0`
- `0x3730`
- `0x3840`
- `0x39b0`
- `0x3ab0`
- `0x3ae0`
- `0x3dd0`

## callees

- `0x12f0`
- `0x1ca0`
- `0x1d50`
- `0x1d60`
- `0x1d70`
- `0x1d80`

## pseudocode

```c

```

## disassembly

```asm
0x1ca0  ldarg.2
0x1ca1  ldarg.2
0x1ca2  callvirt instance valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorTypes()
0x1ca7  ldarg.1
0x1ca8  or
0x1ca9  callvirt instance void Microsoft.Crm.Workflow.WorkflowErrorVisitor::set_ErrorTypes(valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes value)
0x1cae  ldarg.2
0x1caf  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes> Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorMap()
0x1cb4  ldarg.0
0x1cb5  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x1cba  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes>::ContainsKey(var<u1>)
0x1cbf  brfalse.s loc_1CE7
0x1cc1  ldarg.2
0x1cc2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes> Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorMap()
0x1cc7  ldarg.0
0x1cc8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x1ccd  ldarg.2
0x1cce  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes> Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorMap()
0x1cd3  ldarg.0
0x1cd4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x1cd9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes>::get_Item(void)
0x1cde  ldarg.1
0x1cdf  or
0x1ce0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes>::set_Item(var<u1>, !!T0)
0x1ce5  br.s     loc_1CF9
0x1ce7  ldarg.2
0x1ce8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes> Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorMap()
0x1ced  ldarg.0
0x1cee  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x1cf3  ldarg.1
0x1cf4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes>::Add(var<u1>, !!T0)
0x1cf9  ldarg.2
0x1cfa  callvirt instance class Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorVisitorContext()
0x1cff  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext::get_OrganizationId()
0x1d04  ldc.i4.s 0x1E
0x1d06  ldstr    aErrorOfType0In// "Error of type {0} in workflow step {1} "...
0x1d0b  ldc.i4.3
0x1d0c  newarr   [mscorlib]System.Object
0x1d11  dup
0x1d12  ldc.i4.0
0x1d13  ldarga.s 1
0x1d15  constrained. Microsoft.Crm.Workflow.WorkflowErrorTypes
0x1d1b  callvirt instance string [mscorlib]System.Object::ToString()
0x1d20  stelem.ref
0x1d21  dup
0x1d22  ldc.i4.1
0x1d23  ldarg.0
0x1d24  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x1d29  stelem.ref
0x1d2a  dup
0x1d2b  ldc.i4.2
0x1d2c  ldarg.0
0x1d2d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x1d32  stelem.ref
0x1d33  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d38  ret
```
