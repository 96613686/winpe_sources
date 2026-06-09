# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderWorkRuleMode

- ea: `0x54e0`
- end: `0x5502`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderWorkRuleMode`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x52b0`
- `0x5370`
- `0x54e0`

## pseudocode

```c

```

## disassembly

```asm
0x54e0  ldarg.0
0x54e1  call     instance bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsAllTheSameRules()
0x54e6  brfalse.s loc_54EE
0x54e8  ldstr    aAllthesamerule// "AllTheSameRules"
0x54ed  ret
0x54ee  ldarg.0
0x54ef  call     instance bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsVaryByDayRules()
0x54f4  brfalse.s loc_54FC
0x54f6  ldstr    aVarybydayrules// "VaryByDayRules"
0x54fb  ret
0x54fc  ldstr    aNotworking// "NotWorking"
0x5501  ret
```
