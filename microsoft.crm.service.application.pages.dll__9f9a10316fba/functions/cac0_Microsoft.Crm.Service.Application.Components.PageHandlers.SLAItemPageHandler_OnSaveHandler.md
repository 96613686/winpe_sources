# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::OnSaveHandler

- ea: `0xcac0`
- end: `0xcb35`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::OnSaveHandler`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xcac0`
- `0xcb40`

## pseudocode

```c

```

## disassembly

```asm
0xcac0  ldarg.0
0xcac1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xcac6  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0xcacb  ldc.i4.1
0xcacc  bne.un.s loc_CAFC
0xcace  ldarg.0
0xcacf  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xcad4  ldc.i4.1
0xcad5  newobj   instance void [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, bool)
0xcada  stloc.0
0xcadb  ldarg.0
0xcadc  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xcae1  ldstr    aWorkflowid// "workflowid"
0xcae6  ldloc.0
0xcae7  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowErrorVisitorContext::.ctor()
0xcaec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::CreateWorkflow(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0xcaf1  box      [mscorlib]System.Guid
0xcaf6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xcafb  ret
0xcafc  ldarg.0
0xcafd  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xcb02  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0xcb07  ldc.i4.2
0xcb08  bne.un.s loc_CB34
0xcb0a  ldarg.0
0xcb0b  ldarg.0
0xcb0c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xcb11  call     instance bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::WorkflowUpdateRequired(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0xcb16  brfalse.s loc_CB34
0xcb18  ldarg.0
0xcb19  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xcb1e  ldc.i4.0
0xcb1f  newobj   instance void [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, bool)
0xcb24  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowErrorVisitorContext::.ctor()
0xcb29  ldarg.0
0xcb2a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xcb2f  callvirt instance void [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::UpdateWorkflow(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xcb34  ret
```
