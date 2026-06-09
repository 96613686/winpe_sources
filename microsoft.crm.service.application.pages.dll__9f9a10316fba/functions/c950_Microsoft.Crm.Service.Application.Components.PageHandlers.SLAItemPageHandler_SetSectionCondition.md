# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionCondition

- ea: `0xc950`
- end: `0xc9d8`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionCondition`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xc720`

## callees

- `0xc610`
- `0xc950`

## pseudocode

```c

```

## disassembly

```asm
0xc950  ldarg.1
0xc951  ldarg.2
0xc952  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xc957  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormSection
0xc95c  stloc.0
0xc95d  ldloc.0
0xc95e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xc963  ldc.i4.0
0xc964  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xc969  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormRow
0xc96e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xc973  ldc.i4.0
0xc974  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xc979  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell
0xc97e  stloc.1
0xc97f  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::.ctor()
0xc984  stloc.2
0xc985  ldloc.2
0xc986  ldc.i4.1
0xc987  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_GenerateDynamicId(bool)
0xc98c  ldloc.2
0xc98d  ldarg.1
0xc98e  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_Form(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm)
0xc993  ldloc.2
0xc994  ldarg.0
0xc995  call     instance int32 Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_ObjectTypeId()
0xc99a  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_ObjectTypeId(int32)
0xc99f  ldloc.2
0xc9a0  ldarg.3
0xc9a1  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_ControlId(string)
0xc9a6  ldloc.2
0xc9a7  ldarg.s  4
0xc9a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xc9ae  ldloc.2
0xc9af  ldc.i4.1
0xc9b0  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_IsAutoGrow(bool)
0xc9b5  ldloc.1
0xc9b6  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xc9bb  ldloc.2
0xc9bc  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xc9c1  leave.s  loc_C9D7
0xc9c3  ldloc.2
0xc9c4  brfalse.s loc_C9CC
0xc9c6  ldloc.2
0xc9c7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc9cc  endfinally
0xc9cd  ldloc.0
0xc9ce  brfalse.s loc_C9D6
0xc9d0  ldloc.0
0xc9d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc9d6  endfinally
0xc9d7  ret
```
