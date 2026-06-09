# Microsoft.Crm.Application.Controls.PublicationParameterControl::RenderDeleteTriggerCheckBox

- ea: `0x758e0`
- end: `0x7594f`
- name: `Microsoft.Crm.Application.Controls.PublicationParameterControl::RenderDeleteTriggerCheckBox`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x75870`

## callees

- `0x74670`
- `0x755c0`
- `0x758e0`
- `0x75970`

## string_xrefs

- `0x75908`: `chkOnDelete`
- `0x7592b`: `WorkflowActivationTriggerOnDelete`
- `0x75932`: `WorkflowActivationTriggerOnProcessDelete`
- `0x75937`: `OnDeleteCheckboxChanged()`

## pseudocode

```c

```

## disassembly

```asm
0x758e0  ldarg.0
0x758e1  call     instance bool Microsoft.Crm.Application.Controls.PublicationParameterControl::IsBPFEntity()
0x758e6  stloc.0
0x758e7  ldarg.1
0x758e8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x758ed  ldstr    aTdColspan2Nowr// "<td colspan=\"2\" nowrap>"
0x758f2  ldc.i4.0
0x758f3  newarr   [mscorlib]System.Object
0x758f8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x758fd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x75902  ldarg.0
0x75903  ldstr    aCheckbox// "checkbox"
0x75908  ldstr    aChkondelete// "chkOnDelete"
0x7590d  ldstr    asc_F537C// ""
0x75912  ldarg.0
0x75913  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Controls.PublicationParameterControl::get_WorkflowStep()
0x75918  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x7591d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x75922  ldc.i4.4
0x75923  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ContainsTriggerCondition(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerConditions)
0x75928  ldloc.0
0x75929  brtrue.s loc_75932
0x7592b  ldstr    aWorkflowactiva_17// "WorkflowActivationTriggerOnDelete"
0x75930  br.s     loc_75937
0x75932  ldstr    aWorkflowactiva_18// "WorkflowActivationTriggerOnProcessDelet"...
0x75937  ldstr    aOndeletecheckb// "OnDeleteCheckboxChanged()"
0x7593c  ldarg.1
0x7593d  ldarg.2
0x7593e  call     instance void Microsoft.Crm.Application.Controls.PublicationParameterControl::RenderInputControl(string type, string id, string name, bool isChecked, string labelTag, string onClick, class [System.Web]System.Web.UI.HtmlTextWriter writer, bool isDisabled)
0x75943  ldarg.1
0x75944  ldstr    aTd_0// "td"
0x75949  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x7594e  ret
```
