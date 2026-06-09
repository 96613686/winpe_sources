# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::SetSectionAction_0

- ea: `0xda00`
- end: `0xda6a`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::SetSectionAction_0`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xd9e0`

## callees

- `0xda00`

## pseudocode

```c

```

## disassembly

```asm
0xda00  ldarg.1
0xda01  ldarg.2
0xda02  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xda07  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormSection
0xda0c  stloc.0
0xda0d  ldarg.3
0xda0e  ldarg.s  4
0xda10  ldarg.s  5
0xda12  ldarg.s  6
0xda14  ldarg.s  7
0xda16  ldarg.s  8
0xda18  ldarg.s  9
0xda1a  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.WorkflowActionsContainer::.ctor(string, string, string, bool, string[], string[], valuetype [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.ActionMenuType)
0xda1f  stloc.1
0xda20  ldloc.0
0xda21  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xda26  ldc.i4.0
0xda27  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xda2c  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormRow
0xda31  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xda36  ldc.i4.0
0xda37  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xda3c  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell
0xda41  ldloc.1
0xda42  ldarg.3
0xda43  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xda48  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xda4d  ldloc.1
0xda4e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xda53  leave.s  loc_DA69
0xda55  ldloc.1
0xda56  brfalse.s loc_DA5E
0xda58  ldloc.1
0xda59  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xda5e  endfinally
0xda5f  ldloc.0
0xda60  brfalse.s loc_DA68
0xda62  ldloc.0
0xda63  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xda68  endfinally
0xda69  ret
```
