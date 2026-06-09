# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionAction_0

- ea: `0xca00`
- end: `0xca68`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionAction_0`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xc720`
- `0xc9e0`

## callees

- `0xca00`

## pseudocode

```c

```

## disassembly

```asm
0xca00  ldarg.1
0xca01  ldarg.2
0xca02  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xca07  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormSection
0xca0c  stloc.0
0xca0d  ldarg.3
0xca0e  ldarg.s  4
0xca10  ldarg.s  5
0xca12  ldarg.s  6
0xca14  ldarg.s  7
0xca16  ldarg.s  8
0xca18  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.WorkflowActionsContainer::.ctor(string, string, string, bool, string[], string[])
0xca1d  stloc.1
0xca1e  ldloc.0
0xca1f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xca24  ldc.i4.0
0xca25  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xca2a  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormRow
0xca2f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xca34  ldc.i4.0
0xca35  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xca3a  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell
0xca3f  ldloc.1
0xca40  ldarg.3
0xca41  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xca46  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xca4b  ldloc.1
0xca4c  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xca51  leave.s  loc_CA67
0xca53  ldloc.1
0xca54  brfalse.s loc_CA5C
0xca56  ldloc.1
0xca57  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xca5c  endfinally
0xca5d  ldloc.0
0xca5e  brfalse.s loc_CA66
0xca60  ldloc.0
0xca61  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xca66  endfinally
0xca67  ret
```
