# Microsoft.Crm.Workflow.WorkflowReferredArgumentVisitor::VisitEntityCreatedByStep

- ea: `0x4cd0`
- end: `0x4d19`
- name: `Microsoft.Crm.Workflow.WorkflowReferredArgumentVisitor::VisitEntityCreatedByStep`
- size: `73`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4780`
- `0x47b0`
- `0x4860`
- `0x4890`
- `0x4b70`

## callees

- `0x4cd0`

## pseudocode

```c

```

## disassembly

```asm
0x4cd0  ldarg.1
0x4cd1  brfalse.s loc_4D18
0x4cd3  ldarg.1
0x4cd4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::get_Step()
0x4cd9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4cde  ldtoken  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep
0x4ce3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ce8  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x4ced  brfalse.s loc_4D18
0x4cef  ldarg.0
0x4cf0  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Workflow.WorkflowReferredArgumentVisitor::_referredArguments
0x4cf5  ldarg.1
0x4cf6  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_ParameterName()
0x4cfb  ldc.i4.0
0x4cfc  ldarg.1
0x4cfd  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_ParameterName()
0x4d02  ldstr    asc_3068C// "#"
0x4d07  ldc.i4.4
0x4d08  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x4d0d  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4d12  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x4d17  pop
0x4d18  ret
```
