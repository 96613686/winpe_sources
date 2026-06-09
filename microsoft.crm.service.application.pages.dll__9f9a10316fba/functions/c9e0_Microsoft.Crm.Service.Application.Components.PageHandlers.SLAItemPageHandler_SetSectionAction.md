# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionAction

- ea: `0xc9e0`
- end: `0xc9f3`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionAction`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xc720`

## callees

- `0xca00`

## pseudocode

```c

```

## disassembly

```asm
0xc9e0  ldarg.0
0xc9e1  ldarg.1
0xc9e2  ldarg.2
0xc9e3  ldarg.3
0xc9e4  ldarg.s  4
0xc9e6  ldarg.s  5
0xc9e8  ldarg.s  6
0xc9ea  ldarg.s  7
0xc9ec  ldnull
0xc9ed  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionAction(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string SectionId, string controlId, string workflowId, string stepId, bool controlDisabled, string[] hiddenSteps, string[] cloneSteps)
0xc9f2  ret
```
