# Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflowWithoutSave

- ea: `0x8af0`
- end: `0x8b82`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflowWithoutSave`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2000`

## callees

- `0x8af0`

## pseudocode

```c

```

## disassembly

```asm
0x8af0  ldnull
0x8af1  stloc.0
0x8af2  ldarg.1
0x8af3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x8af8  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_IsCrmUIWorkflow()
0x8afd  brtrue.s loc_8B07
0x8aff  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.NotCrmWorkflowStepControl::.ctor()
0x8b04  stloc.0
0x8b05  br.s     loc_8B3B
0x8b07  ldc.i4.3
0x8b08  ldarg.2
0x8b09  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8b0e  ldarg.3
0x8b0f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowUIVisitor::.ctor(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowDisplayMode, valuetype [mscorlib]System.Guid, bool)
0x8b14  stloc.3
0x8b15  ldloc.3
0x8b16  ldarg.1
0x8b17  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepVisitorBase::VisitWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x8b1c  ldloc.3
0x8b1d  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowStepControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowUIVisitor::get_WorkflowStepControl()
0x8b22  ldc.i4.1
0x8b23  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8b28  ldloc.3
0x8b29  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowStepControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowUIVisitor::get_WorkflowStepControl()
0x8b2e  stloc.0
0x8b2f  leave.s  loc_8B3B
0x8b31  ldloc.3
0x8b32  brfalse.s loc_8B3A
0x8b34  ldloc.3
0x8b35  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8b3a  endfinally
0x8b3b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x8b40  stloc.1
0x8b41  ldloc.1
0x8b42  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8b47  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x8b4c  stloc.s  4
0x8b4e  ldloc.s  4
0x8b50  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x8b55  stloc.s  5
0x8b57  ldloc.0
0x8b58  ldloc.s  5
0x8b5a  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x8b5f  ldloc.1
0x8b60  callvirt instance string [mscorlib]System.Object::ToString()
0x8b65  stloc.2
0x8b66  leave.s  loc_8B80
0x8b68  ldloc.s  5
0x8b6a  brfalse.s loc_8B73
0x8b6c  ldloc.s  5
0x8b6e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8b73  endfinally
0x8b74  ldloc.s  4
0x8b76  brfalse.s loc_8B7F
0x8b78  ldloc.s  4
0x8b7a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8b7f  endfinally
0x8b80  ldloc.2
0x8b81  ret
```
