# Microsoft.Crm.Application.ProcessControl.Configuration.BpfPageControl::RenderAddStepHeaders

- ea: `0x4ce60`
- end: `0x4cec1`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfPageControl::RenderAddStepHeaders`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4c940`
- `0x4ce60`

## string_xrefs

- `0x4ce8e`: `ProcessControl.Configurator.Stage.Title.PageStepLabel`
- `0x4ce9f`: `ProcessControl.Configurator.Stage.Title.PageStepSource`
- `0x4ceb0`: `ProcessControl.Configurator.Stage.Title.PageStepField`
- `0x4ce64`: `Expected writer to be not null.`

## pseudocode

```c

```

## disassembly

```asm
0x4ce60  ldarg.1
0x4ce61  ldnull
0x4ce62  cgt.un
0x4ce64  ldstr    aExpectedWriter// "Expected writer to be not null."
0x4ce69  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4ce6e  ldarg.1
0x4ce6f  brtrue.s loc_4CE72
0x4ce71  ret
0x4ce72  ldarg.1
0x4ce73  ldc.i4.s 0xA
0x4ce75  ldstr    aStepHeader// "step-header"
0x4ce7a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x4ce7f  ldarg.1
0x4ce80  ldc.i4.s 0x19
0x4ce82  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x4ce87  ldarg.0
0x4ce88  ldarg.1
0x4ce89  ldstr    aPcPagestepName// "pc_pagestep_name_value_container"
0x4ce8e  ldstr    aProcesscontrol_22// "ProcessControl.Configurator.Stage.Title"...
0x4ce93  call     instance void Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::renderHeaderColumn(class [System.Web]System.Web.UI.HtmlTextWriter writer, string cssClassName, string labelId)
0x4ce98  ldarg.0
0x4ce99  ldarg.1
0x4ce9a  ldstr    aPcPagestepName// "pc_pagestep_name_value_container"
0x4ce9f  ldstr    aProcesscontrol_23// "ProcessControl.Configurator.Stage.Title"...
0x4cea4  call     instance void Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::renderHeaderColumn(class [System.Web]System.Web.UI.HtmlTextWriter writer, string cssClassName, string labelId)
0x4cea9  ldarg.0
0x4ceaa  ldarg.1
0x4ceab  ldstr    aPcPagestepName// "pc_pagestep_name_value_container"
0x4ceb0  ldstr    aProcesscontrol_24// "ProcessControl.Configurator.Stage.Title"...
0x4ceb5  call     instance void Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::renderHeaderColumn(class [System.Web]System.Web.UI.HtmlTextWriter writer, string cssClassName, string labelId)
0x4ceba  ldarg.1
0x4cebb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x4cec0  ret
```
