# Microsoft.Crm.Application.Controls.AsyncWorkflowPublicationParameterControl::RenderWorkflowLogRetention

- ea: `0x75c20`
- end: `0x75cc9`
- name: `Microsoft.Crm.Application.Controls.AsyncWorkflowPublicationParameterControl::RenderWorkflowLogRetention`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x74670`
- `0x75950`
- `0x75a30`
- `0x75a70`

## string_xrefs

- `0x75c3b`: `Web.SFA.Workflow.Section.AsyncAutoDelete`
- `0x75c83`: `asyncautodelete`
- `0x75c88`: `asyncautodelete`
- `0x75ca2`: `Web.SFA.Workflow.AsyncAutoDelete`

## pseudocode

```c

```

## disassembly

```asm
0x75c20  ldarg.0
0x75c21  ldarg.1
0x75c22  call     instance void Microsoft.Crm.Application.Controls.PublicationParameterControl::RenderBeginRow(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x75c27  ldarg.1
0x75c28  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x75c2d  ldstr    aTdColspan3Clas_0// "<td colspan=\"3\" class=\"ms-crm-Field-"...
0x75c32  ldc.i4.1
0x75c33  newarr   [mscorlib]System.Object
0x75c38  dup
0x75c39  ldc.i4.0
0x75c3a  ldarg.0
0x75c3b  ldstr    aWebSfaWorkflow_32// "Web.SFA.Workflow.Section.AsyncAutoDelet"...
0x75c40  call     instance string Microsoft.Crm.Application.Controls.PublicationParameterControl::GetHtmlEncodedResourceString(string resourceName)
0x75c45  stelem.ref
0x75c46  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x75c4b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x75c50  ldarg.1
0x75c51  ldstr    aTr_0// "tr"
0x75c56  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x75c5b  ldarg.0
0x75c5c  ldarg.1
0x75c5d  call     instance void Microsoft.Crm.Application.Controls.PublicationParameterControl::RenderBeginRow(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x75c62  ldarg.1
0x75c63  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x75c68  ldstr    aTdColspan3// "<td colspan=\"3\">"
0x75c6d  ldc.i4.0
0x75c6e  newarr   [mscorlib]System.Object
0x75c73  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x75c78  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x75c7d  ldarg.0
0x75c7e  ldstr    aCheckbox// "checkbox"
0x75c83  ldstr    aAsyncautodelet// "asyncautodelete"
0x75c88  ldstr    aAsyncautodelet// "asyncautodelete"
0x75c8d  ldarg.0
0x75c8e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Controls.PublicationParameterControl::get_WorkflowStep()
0x75c93  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x75c98  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x75c9d  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_AsyncAutoDelete()
0x75ca2  ldstr    aWebSfaWorkflow_33// "Web.SFA.Workflow.AsyncAutoDelete"
0x75ca7  ldstr    asc_F537C// ""
0x75cac  ldarg.1
0x75cad  call     instance void Microsoft.Crm.Application.Controls.PublicationParameterControl::RenderInputControl(string type, string id, string name, bool isChecked, string labelTag, string onClick, class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x75cb2  ldarg.1
0x75cb3  ldstr    aTd_0// "td"
0x75cb8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x75cbd  ldarg.1
0x75cbe  ldstr    aTr_0// "tr"
0x75cc3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x75cc8  ret
```
