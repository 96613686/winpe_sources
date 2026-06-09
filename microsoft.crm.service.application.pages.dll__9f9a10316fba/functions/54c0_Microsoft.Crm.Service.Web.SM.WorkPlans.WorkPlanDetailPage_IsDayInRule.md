# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsDayInRule

- ea: `0x54c0`
- end: `0x54d2`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsDayInRule`
- size: `18`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4fd0`
- `0x5540`

## callees

- `0x54c0`

## pseudocode

```c

```

## disassembly

```asm
0x54c0  ldarg.0
0x54c1  brfalse.s loc_54D0
0x54c3  ldarg.0
0x54c4  callvirt instance string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Pattern()
0x54c9  ldarg.1
0x54ca  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::IsDayInRule(string, int32)
0x54cf  ret
0x54d0  ldc.i4.1
0x54d1  ret
```
