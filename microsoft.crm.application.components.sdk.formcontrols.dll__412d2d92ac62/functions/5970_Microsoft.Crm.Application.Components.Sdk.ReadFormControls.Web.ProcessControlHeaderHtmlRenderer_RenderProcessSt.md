# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlHeaderHtmlRenderer::RenderProcessStages

- ea: `0x5970`
- end: `0x5a5b`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlHeaderHtmlRenderer::RenderProcessStages`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5950`

## callees

- `0x5970`
- `0x5b30`

## string_xrefs

- `0x59c7`: `<div\n				id='stage_{0}'\n				class="{1}"\n				tabindex="1000">\n				<div class="globalActiveStageFlag">\n				</div>\n				<div class="processStageTailContainer" title='{2}'>\n					<div class="processStageHeadContainer">\n						<div class="stageContentArea">\n							<div class="stageContent">\n								<div class="stageIconHolder">\n									<img class="stageIcon" />\n								</div>\n								<span class="stageNameContent">{3}</span>\n							</div>\n						</div>\n					</div>\n				<`

## pseudocode

```c

```

## disassembly

```asm
0x5970  ldarg.1
0x5971  ldstr    aDivIdProcessst_2// "<div id=\"processStagesContainer\" clas"...
0x5976  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x597b  pop
0x597c  ldc.i4.0
0x597d  stloc.0
0x597e  ldarg.0
0x597f  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlHeaderHtmlRenderer::get_Process()
0x5984  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x5989  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0x598e  stloc.1
0x598f  br       loc_5A37
0x5994  ldloc.1
0x5995  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x599a  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep
0x599f  stloc.2
0x59a0  ldloc.2
0x59a1  brfalse  loc_5A37
0x59a6  ldloc.2
0x59a7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x59ac  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0x59b1  stloc.3
0x59b2  br.s     loc_5A23
0x59b4  ldloc.3
0x59b5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x59ba  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep
0x59bf  stloc.s  4
0x59c1  ldarg.1
0x59c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x59c7  ldstr    aDivIdStage0Cla// "<div\r\n\t\t\t\tid='stage_{0}'\r\n\t\t"...
0x59cc  ldc.i4.6
0x59cd  newarr   [mscorlib]System.Object
0x59d2  dup
0x59d3  ldc.i4.0
0x59d4  ldloc.0
0x59d5  box      [mscorlib]System.Int32
0x59da  stelem.ref
0x59db  dup
0x59dc  ldc.i4.1
0x59dd  ldsfld   string [mscorlib]System.String::Empty
0x59e2  stelem.ref
0x59e3  dup
0x59e4  ldc.i4.2
0x59e5  ldsfld   string [mscorlib]System.String::Empty
0x59ea  stelem.ref
0x59eb  dup
0x59ec  ldc.i4.3
0x59ed  ldloc.s  4
0x59ef  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::get_StageName()
0x59f4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x59f9  stelem.ref
0x59fa  dup
0x59fb  ldc.i4.4
0x59fc  ldstr    aImgsProcesscon_1// "/_imgs/processcontrol/process_control_g"...
0x5a01  stelem.ref
0x5a02  dup
0x5a03  ldc.i4.5
0x5a04  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5a09  ldstr    aProcesscontrol_0// "ProcessControl.InProgressStage"
0x5a0e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5a13  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x5a18  stelem.ref
0x5a19  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x5a1e  pop
0x5a1f  ldloc.0
0x5a20  ldc.i4.1
0x5a21  add
0x5a22  stloc.0
0x5a23  ldloc.3
0x5a24  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5a29  brtrue.s loc_59B4
0x5a2b  leave.s  loc_5A37
0x5a2d  ldloc.3
0x5a2e  brfalse.s loc_5A36
0x5a30  ldloc.3
0x5a31  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a36  endfinally
0x5a37  ldloc.1
0x5a38  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5a3d  brtrue   loc_5994
0x5a42  leave.s  loc_5A4E
0x5a44  ldloc.1
0x5a45  brfalse.s loc_5A4D
0x5a47  ldloc.1
0x5a48  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a4d  endfinally
0x5a4e  ldarg.1
0x5a4f  ldstr    aDivDiv// "</div></div>"
0x5a54  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5a59  pop
0x5a5a  ret
```
