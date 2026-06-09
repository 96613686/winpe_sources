# Microsoft.Crm.Service.Application.Components.PageHandlers.RoutingRuleItemRecordPageHandler::SetSectionCondition

- ea: `0xd150`
- end: `0xd1f4`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.RoutingRuleItemRecordPageHandler::SetSectionCondition`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xcfb0`

## callees

- `0xd150`

## pseudocode

```c

```

## disassembly

```asm
0xd150  ldarg.1
0xd151  ldarg.2
0xd152  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xd157  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormSection
0xd15c  stloc.0
0xd15d  ldloc.0
0xd15e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd163  ldc.i4.0
0xd164  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xd169  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormRow
0xd16e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd173  ldc.i4.0
0xd174  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xd179  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell
0xd17e  pop
0xd17f  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::.ctor()
0xd184  stloc.1
0xd185  ldloc.1
0xd186  ldarg.1
0xd187  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_Form(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm)
0xd18c  ldloc.1
0xd18d  ldc.i4.s 0x70
0xd18f  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_ObjectTypeId(int32)
0xd194  ldloc.1
0xd195  ldarg.3
0xd196  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_ControlId(string)
0xd19b  ldloc.1
0xd19c  ldc.i4.0
0xd19d  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_GenerateDynamicId(bool)
0xd1a2  ldloc.1
0xd1a3  ldc.i4.1
0xd1a4  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_IsFixedHeight(bool)
0xd1a9  ldloc.1
0xd1aa  ldarg.s  4
0xd1ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xd1b1  ldloc.0
0xd1b2  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd1b7  ldc.i4.0
0xd1b8  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xd1bd  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormRow
0xd1c2  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd1c7  ldc.i4.0
0xd1c8  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xd1cd  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell
0xd1d2  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd1d7  ldloc.1
0xd1d8  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd1dd  leave.s  loc_D1F3
0xd1df  ldloc.1
0xd1e0  brfalse.s loc_D1E8
0xd1e2  ldloc.1
0xd1e3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1e8  endfinally
0xd1e9  ldloc.0
0xd1ea  brfalse.s loc_D1F2
0xd1ec  ldloc.0
0xd1ed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1f2  endfinally
0xd1f3  ret
```
