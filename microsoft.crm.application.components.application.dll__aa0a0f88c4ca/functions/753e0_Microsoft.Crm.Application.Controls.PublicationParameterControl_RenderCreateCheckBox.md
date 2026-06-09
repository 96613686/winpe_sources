# Microsoft.Crm.Application.Controls.PublicationParameterControl::RenderCreateCheckBox

- ea: `0x753e0`
- end: `0x75464`
- name: `Microsoft.Crm.Application.Controls.PublicationParameterControl::RenderCreateCheckBox`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x75380`

## callees

- `0x74670`
- `0x74680`
- `0x753e0`
- `0x75470`
- `0x755c0`
- `0x75970`

## string_xrefs

- `0x75408`: `chkOnCreate`
- `0x7542b`: `WorkflowActivationTriggerOnCreate`
- `0x75437`: `OnCreateCheckboxChanged()`
- `0x75446`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x753e0  ldarg.0
0x753e1  call     instance bool Microsoft.Crm.Application.Controls.PublicationParameterControl::IsBPFEntity()
0x753e6  stloc.0
0x753e7  ldarg.1
0x753e8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x753ed  ldstr    aTdColspan2Nowr// "<td colspan=\"2\" nowrap>"
0x753f2  ldc.i4.0
0x753f3  newarr   [mscorlib]System.Object
0x753f8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x753fd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x75402  ldarg.0
0x75403  ldstr    aCheckbox// "checkbox"
0x75408  ldstr    aChkoncreate// "chkOnCreate"
0x7540d  ldstr    asc_F537C// ""
0x75412  ldarg.0
0x75413  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Controls.PublicationParameterControl::get_WorkflowStep()
0x75418  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x7541d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x75422  ldc.i4.2
0x75423  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ContainsTriggerCondition(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerConditions)
0x75428  ldloc.0
0x75429  brtrue.s loc_75432
0x7542b  ldstr    aWorkflowactiva_8// "WorkflowActivationTriggerOnCreate"
0x75430  br.s     loc_75437
0x75432  ldstr    aWorkflowactiva_9// "WorkflowActivationTriggerOnProcessAppli"...
0x75437  ldstr    aOncreatecheckb// "OnCreateCheckboxChanged()"
0x7543c  ldarg.1
0x7543d  ldarg.0
0x7543e  call     instance bool Microsoft.Crm.Application.Controls.PublicationParameterControl::get_IsDisabled()
0x75443  brtrue.s loc_75452
0x75445  ldarg.0
0x75446  ldstr    aCreate// "Create"
0x7544b  callvirt instance bool Microsoft.Crm.Application.Controls.PublicationParameterControl::ShouldDisableMessage(string messageName)
0x75450  br.s     loc_75453
0x75452  ldc.i4.1
0x75453  call     instance void Microsoft.Crm.Application.Controls.PublicationParameterControl::RenderInputControl(string type, string id, string name, bool isChecked, string labelTag, string onClick, class [System.Web]System.Web.UI.HtmlTextWriter writer, bool isDisabled)
0x75458  ldarg.1
0x75459  ldstr    aTd_0// "td"
0x7545e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x75463  ret
```
