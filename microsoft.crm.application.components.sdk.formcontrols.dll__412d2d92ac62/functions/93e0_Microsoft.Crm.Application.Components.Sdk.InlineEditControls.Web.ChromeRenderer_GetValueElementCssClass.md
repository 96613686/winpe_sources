# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::GetValueElementCssClass

- ea: `0x93e0`
- end: `0x94f7`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::GetValueElementCssClass`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x8e60`

## callees

- `0x1230`
- `0x1330`
- `0x1450`
- `0x8e00`
- `0x8e20`
- `0x93e0`
- `0x9500`

## pseudocode

```c

```

## disassembly

```asm
0x93e0  ldstr    asc_30804// ""
0x93e5  stloc.0
0x93e6  ldarg.0
0x93e7  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::IsHiddenControl()
0x93ec  brfalse.s loc_93F9
0x93ee  ldstr    aMsCrmInlineVal// "ms-crm-Inline-Value ms-crm-Hidden"
0x93f3  stloc.0
0x93f4  br       loc_94D6
0x93f9  ldarg.0
0x93fa  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x93ff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x9404  brtrue.s loc_946D
0x9406  ldarg.0
0x9407  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x940c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppControl::get_ClassId()
0x9411  ldstr    aE0dece4b6fc84a// "{E0DECE4B-6FC8-4A8F-A065-082708572369}"
0x9416  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x941b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9420  brfalse.s loc_9428
0x9422  ldstr    aMsCrmTextareaM// "ms-crm-TextArea-MDD "
0x9427  stloc.0
0x9428  ldarg.0
0x9429  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x942e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9433  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9438  brtrue.s loc_945F
0x943a  ldarg.0
0x943b  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x9440  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9445  ldstr    aFlowsiframecon// "FlowsIFrameControl"
0x944a  callvirt instance bool [mscorlib]System.String::Equals(string)
0x944f  brfalse.s loc_945F
0x9451  ldloc.0
0x9452  ldstr    aMsCrmInlineVal_0// "ms-crm-Inline-Value ms-crm-Inline-Flows"...
0x9457  call     string [mscorlib]System.String::Concat(string, string)
0x945c  stloc.0
0x945d  br.s     loc_94D6
0x945f  ldloc.0
0x9460  ldstr    aMsCrmInlineVal_1// "ms-crm-Inline-Value ms-crm-Inline-Empty"...
0x9465  call     string [mscorlib]System.String::Concat(string, string)
0x946a  stloc.0
0x946b  br.s     loc_94D6
0x946d  ldarg.0
0x946e  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x9473  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x9478  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x947d  stloc.1
0x947e  ldarg.0
0x947f  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x9484  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TemplateRenderer()
0x9489  ldloc.1
0x948a  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer::GetCssTemplate(string)
0x948f  stloc.2
0x9490  ldloc.2
0x9491  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9496  brfalse.s loc_94CA
0x9498  ldarg.0
0x9499  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x949e  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x94a3  brfalse.s loc_94CA
0x94a5  ldarg.0
0x94a6  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x94ab  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x94b0  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x94b5  brfalse.s loc_94CA
0x94b7  ldarg.0
0x94b8  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x94bd  isinst   Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl
0x94c2  brfalse.s loc_94CA
0x94c4  ldstr    aMsCrmInlineLoo// "ms-crm-Inline-Lookup"
0x94c9  stloc.2
0x94ca  ldstr    aMsCrmInlineVal_2// "ms-crm-Inline-Value "
0x94cf  ldloc.2
0x94d0  call     string [mscorlib]System.String::Concat(string, string)
0x94d5  stloc.0
0x94d6  ldarg.0
0x94d7  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_ValueElementAdditionalCssClass()
0x94dc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x94e1  brtrue.s loc_94F5
0x94e3  ldloc.0
0x94e4  ldstr    asc_38C0C// " "
0x94e9  ldarg.0
0x94ea  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_ValueElementAdditionalCssClass()
0x94ef  call     string [mscorlib]System.String::Concat(string, string, string)
0x94f4  stloc.0
0x94f5  ldloc.0
0x94f6  ret
```
