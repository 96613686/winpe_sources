# Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::RenderAddStepHeaders

- ea: `0x4c8d0`
- end: `0x4c931`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::RenderAddStepHeaders`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4c840`

## callees

- `0x4c8d0`
- `0x4c940`

## string_xrefs

- `0x4c8fe`: `ProcessControl.Configurator.Stage.Title.StepName`
- `0x4c90f`: `ProcessControl.Configurator.Stage.Title.Value`
- `0x4c920`: `ProcessControl.Configurator.Stage.Title.required`
- `0x4c8d4`: `Expected writer to be not null.`

## pseudocode

```c

```

## disassembly

```asm
0x4c8d0  ldarg.1
0x4c8d1  ldnull
0x4c8d2  cgt.un
0x4c8d4  ldstr    aExpectedWriter// "Expected writer to be not null."
0x4c8d9  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4c8de  ldarg.1
0x4c8df  brtrue.s loc_4C8E2
0x4c8e1  ret
0x4c8e2  ldarg.1
0x4c8e3  ldc.i4.s 0xA
0x4c8e5  ldstr    aStepHeader// "step-header"
0x4c8ea  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x4c8ef  ldarg.1
0x4c8f0  ldc.i4.s 0x19
0x4c8f2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x4c8f7  ldarg.0
0x4c8f8  ldarg.1
0x4c8f9  ldstr    aPcStepNameValu// "pc_step_name_value_container"
0x4c8fe  ldstr    aProcesscontrol_16// "ProcessControl.Configurator.Stage.Title"...
0x4c903  call     instance void Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::renderHeaderColumn(class [System.Web]System.Web.UI.HtmlTextWriter writer, string cssClassName, string labelId)
0x4c908  ldarg.0
0x4c909  ldarg.1
0x4c90a  ldstr    aPcStepNameValu// "pc_step_name_value_container"
0x4c90f  ldstr    aProcesscontrol_17// "ProcessControl.Configurator.Stage.Title"...
0x4c914  call     instance void Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::renderHeaderColumn(class [System.Web]System.Web.UI.HtmlTextWriter writer, string cssClassName, string labelId)
0x4c919  ldarg.0
0x4c91a  ldarg.1
0x4c91b  ldstr    aPcStepRequired// "pc_step_required_container"
0x4c920  ldstr    aProcesscontrol_18// "ProcessControl.Configurator.Stage.Title"...
0x4c925  call     instance void Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::renderHeaderColumn(class [System.Web]System.Web.UI.HtmlTextWriter writer, string cssClassName, string labelId)
0x4c92a  ldarg.1
0x4c92b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x4c930  ret
```
