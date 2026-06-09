# Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow_2

- ea: `0x8bd0`
- end: `0x8df6`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow_2`
- size: `550`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x8ba0`
- `0x8bc0`

## callees

- `0x1ab0`
- `0x8bd0`

## pseudocode

```c

```

## disassembly

```asm
0x8bd0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x8bd5  stloc.0
0x8bd6  ldarg.3
0x8bd7  dup
0x8bd8  brtrue.s loc_8BE0
0x8bda  pop
0x8bdb  ldstr    asc_A26A// ""
0x8be0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8be5  brtrue   loc_8D09
0x8bea  ldarg.s  4
0x8bec  dup
0x8bed  brtrue.s loc_8BF5
0x8bef  pop
0x8bf0  ldstr    asc_A26A// ""
0x8bf5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8bfa  brtrue   loc_8D09
0x8bff  ldarg.s  4
0x8c01  ldc.i4   0x2617
0x8c06  stloc.1
0x8c07  ldloca.s 1
0x8c09  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8c0e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8c13  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8c18  brtrue.s loc_8C38
0x8c1a  ldarg.s  4
0x8c1c  ldc.i4   0x2455
0x8c21  stloc.1
0x8c22  ldloca.s 1
0x8c24  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8c29  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8c2e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8c33  brfalse  loc_8D09
0x8c38  ldarg.2
0x8c39  brfalse.s loc_8C79
0x8c3b  ldarg.1
0x8c3c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x8c41  ldarg.s  4
0x8c43  ldc.i4   0x2617
0x8c48  stloc.1
0x8c49  ldloca.s 1
0x8c4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8c50  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8c55  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8c5a  brtrue.s loc_8C63
0x8c5c  ldstr    aConvertruleite_0// "convertruleitem"
0x8c61  br.s     loc_8C68
0x8c63  ldstr    aSlaitem// "slaitem"
0x8c68  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_WorkflowRendererObjectTypeCode(string)
0x8c6d  ldarg.0
0x8c6e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x8c73  ldarg.1
0x8c74  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Save(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x8c79  ldloc.0
0x8c7a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8c7f  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x8c84  stloc.2
0x8c85  ldloc.2
0x8c86  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x8c8b  stloc.3
0x8c8c  ldc.i4.0
0x8c8d  ldarg.3
0x8c8e  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.SLAUIVisitor::.ctor(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowDisplayMode, string)
0x8c93  stloc.s  4
0x8c95  ldloc.s  4
0x8c97  ldarg.1
0x8c98  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepVisitorBase::VisitWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x8c9d  ldloc.s  4
0x8c9f  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowStepControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowUIVisitor::get_WorkflowStepControl()
0x8ca4  ldloc.3
0x8ca5  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x8caa  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Hidden::.ctor()
0x8caf  stloc.s  5
0x8cb1  ldloc.s  5
0x8cb3  ldstr    aHidsluginfo// "hidSlugInfo"
0x8cb8  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8cbd  ldloc.s  5
0x8cbf  ldloc.s  4
0x8cc1  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowUIVisitor::get_SlugInfo()
0x8cc6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x8ccb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Hidden::set_Text(string)
0x8cd0  ldloc.s  5
0x8cd2  ldloc.3
0x8cd3  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x8cd8  leave    loc_8DEF
0x8cdd  ldloc.s  5
0x8cdf  brfalse.s loc_8CE8
0x8ce1  ldloc.s  5
0x8ce3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ce8  endfinally
0x8ce9  ldloc.s  4
0x8ceb  brfalse.s loc_8CF4
0x8ced  ldloc.s  4
0x8cef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8cf4  endfinally
0x8cf5  ldloc.3
0x8cf6  brfalse.s loc_8CFE
0x8cf8  ldloc.3
0x8cf9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8cfe  endfinally
0x8cff  ldloc.2
0x8d00  brfalse.s loc_8D08
0x8d02  ldloc.2
0x8d03  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d08  endfinally
0x8d09  ldarg.2
0x8d0a  brfalse.s loc_8D18
0x8d0c  ldarg.0
0x8d0d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x8d12  ldarg.1
0x8d13  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Save(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x8d18  ldloc.0
0x8d19  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8d1e  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x8d23  stloc.s  6
0x8d25  ldloc.s  6
0x8d27  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x8d2c  stloc.s  7
0x8d2e  ldc.i4.0
0x8d2f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowUIVisitor::.ctor(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowDisplayMode)
0x8d34  stloc.s  8
0x8d36  ldloc.s  8
0x8d38  ldarg.1
0x8d39  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepVisitorBase::VisitWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x8d3e  ldloc.s  8
0x8d40  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowStepControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowUIVisitor::get_WorkflowStepControl()
0x8d45  ldloc.s  7
0x8d47  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x8d4c  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Hidden::.ctor()
0x8d51  stloc.s  9
0x8d53  ldloc.s  9
0x8d55  ldstr    aHidsluginfo// "hidSlugInfo"
0x8d5a  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8d5f  ldloc.s  9
0x8d61  ldloc.s  8
0x8d63  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowUIVisitor::get_SlugInfo()
0x8d68  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x8d6d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Hidden::set_Text(string)
0x8d72  ldloc.s  9
0x8d74  ldloc.s  7
0x8d76  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x8d7b  leave.s  loc_8D89
0x8d7d  ldloc.s  9
0x8d7f  brfalse.s loc_8D88
0x8d81  ldloc.s  9
0x8d83  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d88  endfinally
0x8d89  ldarg.1
0x8d8a  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowCategory()
0x8d8f  ldc.i4.3
0x8d90  bne.un.s loc_8DC9
0x8d92  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Hidden::.ctor()
0x8d97  stloc.s  0xA
0x8d99  ldloc.s  0xA
0x8d9b  ldstr    aHidreferredarg// "hidReferredArgumentNames"
0x8da0  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8da5  ldloc.s  0xA
0x8da7  ldarg.1
0x8da8  call     string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowReferredArgumentVisitor::GetArgumentNames(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x8dad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Hidden::set_Text(string)
0x8db2  ldloc.s  0xA
0x8db4  ldloc.s  7
0x8db6  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x8dbb  leave.s  loc_8DEF
0x8dbd  ldloc.s  0xA
0x8dbf  brfalse.s loc_8DC8
0x8dc1  ldloc.s  0xA
0x8dc3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8dc8  endfinally
0x8dc9  leave.s  loc_8DEF
0x8dcb  ldloc.s  8
0x8dcd  brfalse.s loc_8DD6
0x8dcf  ldloc.s  8
0x8dd1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8dd6  endfinally
0x8dd7  ldloc.s  7
0x8dd9  brfalse.s loc_8DE2
0x8ddb  ldloc.s  7
0x8ddd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8de2  endfinally
0x8de3  ldloc.s  6
0x8de5  brfalse.s loc_8DEE
0x8de7  ldloc.s  6
0x8de9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8dee  endfinally
0x8def  ldloc.0
0x8df0  callvirt instance string [mscorlib]System.Object::ToString()
0x8df5  ret
```
