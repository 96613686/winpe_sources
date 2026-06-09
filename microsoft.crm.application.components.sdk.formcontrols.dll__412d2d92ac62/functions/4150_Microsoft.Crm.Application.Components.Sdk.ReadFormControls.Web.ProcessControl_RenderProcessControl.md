# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderProcessControl

- ea: `0x4150`
- end: `0x4351`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderProcessControl`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x3ec0`

## callees

- `0x3570`
- `0x4120`
- `0x4150`
- `0x4360`
- `0x43e0`
- `0x4cc0`
- `0x5940`
- `0x5950`
- `0x5c80`
- `0x5de0`
- `0x5e20`
- `0x5e60`

## string_xrefs

- `0x4159`: `Process was removed before layout was called. Try to reload page`

## pseudocode

```c

```

## disassembly

```asm
0x4150  ldarg.0
0x4151  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x4156  ldnull
0x4157  cgt.un
0x4159  ldstr    aProcessWasRemo// "Process was removed before layout was c"...
0x415e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4163  ldarg.1
0x4164  ldarg.0
0x4165  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_OrganizationContext()
0x416a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x416f  stloc.0
0x4170  ldarg.0
0x4171  ldarg.0
0x4172  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x4177  ldloc.0
0x4178  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x417d  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderStages(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase process, string currentEntity)
0x4182  stloc.1
0x4183  call     string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlIcons::GetBack()
0x4188  stloc.2
0x4189  call     string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlIcons::GetAdvance()
0x418e  stloc.3
0x418f  call     string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlIcons::GetArrowLayout()
0x4194  stloc.s  4
0x4196  call     string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlIcons::GetSetActive()
0x419b  stloc.s  5
0x419d  ldarg.0
0x419e  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderProcessInfo()
0x41a3  stloc.s  6
0x41a5  ldarg.0
0x41a6  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderEmptyWarningBar()
0x41ab  stloc.s  7
0x41ad  ldarg.0
0x41ae  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderProcessName()
0x41b3  stloc.s  8
0x41b5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x41ba  ldstr    aProcesscontrol_43// "ProcessControl.Advance"
0x41bf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x41c4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x41c9  stloc.s  9
0x41cb  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x41d0  stloc.s  0xA
0x41d2  ldarg.0
0x41d3  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x41d8  newobj   instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlHeaderHtmlRenderer::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep process)
0x41dd  ldloc.s  0xA
0x41df  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlHeaderHtmlRenderer::Render(class [mscorlib]System.Text.StringBuilder htmlBuilder)
0x41e4  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x41e9  ldstr    aImgsProcesscon// "/_imgs/processcontrol/8x6_collapse_icon"...
0x41ee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0x41f3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x41f8  stloc.s  0xB
0x41fa  ldarg.2
0x41fb  brtrue.s loc_4204
0x41fd  ldstr    aGetprocesscont// "{{:~getProcessControlCollapsibleClass(#"...
0x4202  br.s     loc_4209
0x4204  ldsfld   string [mscorlib]System.String::Empty
0x4209  stloc.s  0xC
0x420b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4210  ldstr    aDivIdProcessco// "<div id=\"processControlContainer\"\r\n"...
0x4215  ldc.i4.s 0x17
0x4217  newarr   [mscorlib]System.Object
0x421c  dup
0x421d  ldc.i4.0
0x421e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4223  ldstr    aProcesscontrol_44// "ProcessControl.Back"
0x4228  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x422d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x4232  stelem.ref
0x4233  dup
0x4234  ldc.i4.1
0x4235  ldloc.s  9
0x4237  stelem.ref
0x4238  dup
0x4239  ldc.i4.2
0x423a  ldloc.1
0x423b  stelem.ref
0x423c  dup
0x423d  ldc.i4.3
0x423e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4243  ldstr    aSalesProcessco_7// "Sales.ProcessControl.Collapse"
0x4248  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x424d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x4252  stelem.ref
0x4253  dup
0x4254  ldc.i4.4
0x4255  ldloc.2
0x4256  stelem.ref
0x4257  dup
0x4258  ldc.i4.5
0x4259  ldloc.3
0x425a  stelem.ref
0x425b  dup
0x425c  ldc.i4.6
0x425d  ldc.i4   0x3E8
0x4262  box      [mscorlib]System.Int32
0x4267  stelem.ref
0x4268  dup
0x4269  ldc.i4.7
0x426a  ldloc.s  6
0x426c  stelem.ref
0x426d  dup
0x426e  ldc.i4.8
0x426f  ldloc.s  9
0x4271  stelem.ref
0x4272  dup
0x4273  ldc.i4.s 9
0x4275  ldloc.s  7
0x4277  stelem.ref
0x4278  dup
0x4279  ldc.i4.s 0xA
0x427b  ldloc.s  8
0x427d  stelem.ref
0x427e  dup
0x427f  ldc.i4.s 0xB
0x4281  ldloc.s  9
0x4283  stelem.ref
0x4284  dup
0x4285  ldc.i4.s 0xC
0x4287  ldloc.s  4
0x4289  stelem.ref
0x428a  dup
0x428b  ldc.i4.s 0xD
0x428d  ldloc.s  0xB
0x428f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x4294  callvirt instance string [mscorlib]System.Object::ToString()
0x4299  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x429e  stelem.ref
0x429f  dup
0x42a0  ldc.i4.s 0xE
0x42a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42a7  ldstr    a01// "{0} {1}"
0x42ac  ldc.i4.2
0x42ad  newarr   [mscorlib]System.Object
0x42b2  dup
0x42b3  ldc.i4.0
0x42b4  ldloc.s  0xB
0x42b6  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x42bb  stelem.ref
0x42bc  dup
0x42bd  ldc.i4.1
0x42be  ldstr    aCollapsebutton// "collapseButtonIcon"
0x42c3  stelem.ref
0x42c4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42c9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x42ce  stelem.ref
0x42cf  dup
0x42d0  ldc.i4.s 0xF
0x42d2  ldloc.s  0xC
0x42d4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x42d9  stelem.ref
0x42da  dup
0x42db  ldc.i4.s 0x10
0x42dd  ldloc.s  0xA
0x42df  stelem.ref
0x42e0  dup
0x42e1  ldc.i4.s 0x11
0x42e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x42e8  ldstr    aProcesscontrol_45// "ProcessControl.SetActive"
0x42ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x42f2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x42f7  stelem.ref
0x42f8  dup
0x42f9  ldc.i4.s 0x12
0x42fb  ldloc.s  5
0x42fd  stelem.ref
0x42fe  dup
0x42ff  ldc.i4.s 0x13
0x4301  ldloc.3
0x4302  stelem.ref
0x4303  dup
0x4304  ldc.i4.s 0x14
0x4306  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x430b  ldstr    aProcesscontrol_46// "ProcessControl.Finish"
0x4310  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4315  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x431a  stelem.ref
0x431b  dup
0x431c  ldc.i4.s 0x15
0x431e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4323  ldstr    aProcesscontrol_38// "ProcessControl.Finished"
0x4328  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x432d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x4332  stelem.ref
0x4333  dup
0x4334  ldc.i4.s 0x16
0x4336  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x433b  ldstr    aBusinessproces// "BusinessProcessFlow"
0x4340  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4345  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x434a  stelem.ref
0x434b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4350  ret
```
