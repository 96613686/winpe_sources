# Microsoft.Crm.Application.Controls.StepBaseControl::RenderConfigureButton

- ea: `0x77b80`
- end: `0x77d2b`
- name: `Microsoft.Crm.Application.Controls.StepBaseControl::RenderConfigureButton`
- size: `427`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x70a20`
- `0x729a0`
- `0x77d40`

## callees

- `0x77020`
- `0x77070`
- `0x77080`
- `0x770d0`
- `0x77b80`
- `0x77d70`

## string_xrefs

- `0x77cc7`: `Id could not contain '_' as it is used to separate id component`
- `0x77b91`: `Web.SFA.Workflow.ConfigureAction.Button.Label`
- `0x77bfb`: `readonly`
- `0x77c0d`: `readonly`

## pseudocode

```c

```

## disassembly

```asm
0x77b80  ldarg.s  4
0x77b82  brtrue.s loc_77B9E
0x77b84  ldarg.0
0x77b85  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x77b8a  brtrue.s loc_77B9E
0x77b8c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x77b91  ldstr    aWebSfaWorkflow_53// "Web.SFA.Workflow.ConfigureAction.Button"...
0x77b96  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x77b9b  stloc.0
0x77b9c  br.s     loc_77BAE
0x77b9e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x77ba3  ldstr    aWebSfaWorkflow_9// "Web.SFA.Workflow.ViewAction.Button.Labe"...
0x77ba8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x77bad  stloc.0
0x77bae  ldarg.0
0x77baf  call     instance valuetype Microsoft.Crm.Application.Controls.WorkflowDisplayMode Microsoft.Crm.Application.Controls.StepBaseControl::get_DisplayMode()
0x77bb4  brfalse.s loc_77BC2
0x77bb6  ldarg.0
0x77bb7  call     instance valuetype Microsoft.Crm.Application.Controls.WorkflowDisplayMode Microsoft.Crm.Application.Controls.StepBaseControl::get_DisplayMode()
0x77bbc  ldc.i4.1
0x77bbd  bne.un   loc_77C62
0x77bc2  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor()
0x77bc7  stloc.1
0x77bc8  ldloc.1
0x77bc9  ldstr    aId_1// "id"
0x77bce  ldarg.0
0x77bcf  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Application.Controls.StepBaseControl::get_Step()
0x77bd4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x77bd9  ldstr    aButton_1// "_button"
0x77bde  call     string [mscorlib]System.String::Concat(string, string)
0x77be3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x77be8  ldloc.1
0x77be9  ldarg.2
0x77bea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_OnClick(string)
0x77bef  ldloc.1
0x77bf0  ldloc.0
0x77bf1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Text(string)
0x77bf6  ldarg.s  4
0x77bf8  brfalse.s loc_77C0C
0x77bfa  ldloc.1
0x77bfb  ldstr    aReadonly_0// "readonly"
0x77c00  ldstr    aTrue// "true"
0x77c05  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x77c0a  br.s     loc_77C1C
0x77c0c  ldloc.1
0x77c0d  ldstr    aReadonly_0// "readonly"
0x77c12  ldstr    aFalse// "false"
0x77c17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x77c1c  ldarg.s  5
0x77c1e  brfalse.s loc_77C30
0x77c20  ldloc.1
0x77c21  ldstr    aSetdisabled// "setDisabled"
0x77c26  ldstr    aTrue// "true"
0x77c2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x77c30  ldarg.0
0x77c31  call     instance bool Microsoft.Crm.Application.Controls.StepBaseControl::get_RenderInErrorMode()
0x77c36  brtrue.s loc_77C43
0x77c38  ldarg.0
0x77c39  call     instance valuetype Microsoft.Crm.Application.Controls.WorkflowDisplayMode Microsoft.Crm.Application.Controls.StepBaseControl::get_DisplayMode()
0x77c3e  ldc.i4.1
0x77c3f  ceq
0x77c41  br.s     loc_77C44
0x77c43  ldc.i4.1
0x77c44  ldarg.s  6
0x77c46  or
0x77c47  brfalse.s loc_77C59
0x77c49  ldloc.1
0x77c4a  ldstr    aDisabled_1// "disabled"
0x77c4f  ldstr    aTrue// "true"
0x77c54  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x77c59  ldloc.1
0x77c5a  ldarg.1
0x77c5b  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x77c60  br.s     loc_77C93
0x77c62  ldarg.0
0x77c63  call     instance valuetype Microsoft.Crm.Application.Controls.WorkflowDisplayMode Microsoft.Crm.Application.Controls.StepBaseControl::get_DisplayMode()
0x77c68  ldc.i4.4
0x77c69  beq.s    loc_77C93
0x77c6b  ldarg.0
0x77c6c  call     instance bool Microsoft.Crm.Application.Controls.StepBaseControl::get_RenderInErrorMode()
0x77c71  brtrue.s loc_77C93
0x77c73  ldarg.0
0x77c74  call     instance bool Microsoft.Crm.Application.Controls.StepBaseControl::get_HideConfigureButton()
0x77c79  brtrue.s loc_77C93
0x77c7b  ldarg.1
0x77c7c  ldarg.0
0x77c7d  ldstr    aJavascript_0// "javascript:"
0x77c82  ldarg.2
0x77c83  call     string [mscorlib]System.String::Concat(string, string)
0x77c88  ldloc.0
0x77c89  callvirt instance string Microsoft.Crm.Application.Controls.StepBaseControl::BuildHyperlink(string eventHandler, string text)
0x77c8e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x77c93  ldarg.1
0x77c94  ldstr    aInput// "input"
0x77c99  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x77c9e  ldarg.1
0x77c9f  ldstr    aType// "type"
0x77ca4  ldstr    aHidden// "hidden"
0x77ca9  ldc.i4.0
0x77caa  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x77caf  ldarg.0
0x77cb0  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Application.Controls.StepBaseControl::get_Step()
0x77cb5  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x77cba  ldstr    asc_1295C0// "_"
0x77cbf  callvirt instance bool [mscorlib]System.String::Contains(string)
0x77cc4  ldc.i4.0
0x77cc5  ceq
0x77cc7  ldstr    aIdCouldNotCont// "Id could not contain '_' as it is used "...
0x77ccc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x77cd1  ldarg.1
0x77cd2  ldstr    aId_1// "id"
0x77cd7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x77cdc  ldstr    a0Activitystate// "{0}_activitystatewfc"
0x77ce1  ldc.i4.1
0x77ce2  newarr   [mscorlib]System.Object
0x77ce7  dup
0x77ce8  ldc.i4.0
0x77ce9  ldarg.0
0x77cea  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Application.Controls.StepBaseControl::get_Step()
0x77cef  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x77cf4  stelem.ref
0x77cf5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x77cfa  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x77cff  ldc.i4.0
0x77d00  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x77d05  ldarg.1
0x77d06  ldstr    aValue// "value"
0x77d0b  ldarg.3
0x77d0c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x77d11  ldc.i4.0
0x77d12  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x77d17  ldarg.1
0x77d18  ldc.i4.s 0x3E
0x77d1a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x77d1f  ldarg.1
0x77d20  ldstr    aInput// "input"
0x77d25  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x77d2a  ret
```
