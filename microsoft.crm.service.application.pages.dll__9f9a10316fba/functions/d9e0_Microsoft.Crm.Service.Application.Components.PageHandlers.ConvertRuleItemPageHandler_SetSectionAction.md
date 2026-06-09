# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::SetSectionAction

- ea: `0xd9e0`
- end: `0xd9f5`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::SetSectionAction`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xd240`

## callees

- `0xda00`

## pseudocode

```c

```

## disassembly

```asm
0xd9e0  ldarg.0
0xd9e1  ldarg.1
0xd9e2  ldarg.2
0xd9e3  ldarg.3
0xd9e4  ldarg.s  4
0xd9e6  ldarg.s  5
0xd9e8  ldarg.s  6
0xd9ea  ldarg.s  7
0xd9ec  ldnull
0xd9ed  ldarg.s  8
0xd9ef  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::SetSectionAction(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string sectionId, string controlId, string workflowId, string stepId, bool controlDisabled, string[] hiddenSteps, string[] cloneSteps, valuetype [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.ActionMenuType actionMenuType)
0xd9f4  ret
```
