# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRecurringRuleVaried

- ea: `0x5680`
- end: `0x56a5`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRecurringRuleVaried`
- size: `37`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4fd0`
- `0x5160`
- `0x52b0`
- `0x5370`
- `0x5390`
- `0x5540`
- `0x55f0`

## callees

- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x5680  ldarg.0
0x5681  brtrue.s loc_5685
0x5683  ldc.i4.0
0x5684  ret
0x5685  ldarg.0
0x5686  ldstr    aIsvaried// "isvaried"
0x568b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5690  brfalse.s loc_56A3
0x5692  ldarg.0
0x5693  ldstr    aIsvaried// "isvaried"
0x5698  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x569d  unbox.any [mscorlib]System.Boolean
0x56a2  ret
0x56a3  ldc.i4.0
0x56a4  ret
```
