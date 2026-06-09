# Microsoft.Crm.Application.WebServices.ConvertRuleDefaultPropertiesProvider::IsPrimaryCreateStep

- ea: `0xa80`
- end: `0xaa3`
- name: `Microsoft.Crm.Application.WebServices.ConvertRuleDefaultPropertiesProvider::IsPrimaryCreateStep`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa20`

## callees

- `0xa80`

## pseudocode

```c

```

## disassembly

```asm
0xa80  ldarg.1
0xa81  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0xa86  brfalse.s loc_AA1
0xa88  ldarg.1
0xa89  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0xa8e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0xa93  ldstr    aConditionbranc// "ConditionBranchStep2"
0xa98  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa9d  brfalse.s loc_AA1
0xa9f  ldc.i4.1
0xaa0  ret
0xaa1  ldc.i4.0
0xaa2  ret
```
