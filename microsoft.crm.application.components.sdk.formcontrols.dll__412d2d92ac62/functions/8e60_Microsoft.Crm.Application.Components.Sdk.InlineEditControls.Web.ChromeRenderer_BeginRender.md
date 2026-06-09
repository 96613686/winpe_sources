# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::BeginRender

- ea: `0x8e60`
- end: `0x91a8`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::BeginRender`
- size: `840`
- prototype: ``
- caller_count: `18`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x8bd0`
- `0x9840`
- `0xa430`
- `0xb050`
- `0xb120`
- `0xb1d0`
- `0xe810`
- `0xfaf0`
- `0x10a30`
- `0x10eb0`
- `0x11070`
- `0x11a00`
- `0x11b20`
- `0x11dd0`
- `0x12080`
- `0x128e0`
- `0x12970`
- `0x12a90`

## callees

- `0x1290`
- `0x1330`
- `0x1370`
- `0x1450`
- `0x15b0`
- `0x16a0`
- `0x8e20`
- `0x8e60`
- `0x93e0`
- `0x9500`
- `0x9510`

## string_xrefs

- `0x8ffb`: `compositeRequiredLevel`
- `0x901c`: `hasCompositeData`
- `0x902c`: `compositionLinkControlId`

## pseudocode

```c

```

## disassembly

```asm
0x8e60  ldarg.1
0x8e61  ldc.i4.s 0x11
0x8e63  ldarg.0
0x8e64  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x8e69  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x8e6e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x8e73  ldarg.0
0x8e74  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x8e79  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x8e7e  brfalse.s loc_8E9B
0x8e80  ldarg.0
0x8e81  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x8e86  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x8e8b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8e90  dup
0x8e91  brtrue.s loc_8EB0
0x8e93  pop
0x8e94  ldsfld   string [mscorlib]System.String::Empty
0x8e99  br.s     loc_8EB0
0x8e9b  ldstr    aUnbound// "unbound_"
0x8ea0  ldarg.0
0x8ea1  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x8ea6  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x8eab  call     string [mscorlib]System.String::Concat(string, string)
0x8eb0  stloc.0
0x8eb1  ldarg.1
0x8eb2  ldsfld   string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.InlineEditConstants::HtmlAttributeForAttributeLogicalName
0x8eb7  ldloc.0
0x8eb8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x8ebd  ldsfld   string [mscorlib]System.String::Empty
0x8ec2  stloc.1
0x8ec3  ldsfld   string [mscorlib]System.String::Empty
0x8ec8  stloc.2
0x8ec9  ldarg.0
0x8eca  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x8ecf  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x8ed4  brfalse.s loc_8F07
0x8ed6  ldarg.0
0x8ed7  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x8edc  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x8ee1  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_FormDataEntityId()
0x8ee6  stloc.1
0x8ee7  ldarg.0
0x8ee8  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x8eed  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x8ef2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm::get_CurrentFormId()
0x8ef7  stloc.s  4
0x8ef9  ldloca.s 4
0x8efb  constrained. [mscorlib]System.Guid
0x8f01  callvirt instance string [mscorlib]System.Object::ToString()
0x8f06  stloc.2
0x8f07  ldarg.1
0x8f08  ldstr    aDataFormid// "data-formid"
0x8f0d  ldloc.2
0x8f0e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x8f13  ldarg.1
0x8f14  ldstr    aDataFdeid// "data-fdeid"
0x8f19  ldloc.1
0x8f1a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x8f1f  ldarg.0
0x8f20  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x8f25  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ControlLayout Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_LayoutMode()
0x8f2a  stloc.3
0x8f2b  ldarg.1
0x8f2c  ldstr    aDataLayout// "data-layout"
0x8f31  ldloca.s 3
0x8f33  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f38  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8f3d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x8f42  ldarg.0
0x8f43  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::IsHiddenControl()
0x8f48  brtrue.s loc_8F7F
0x8f4a  ldarg.1
0x8f4b  ldc.i4.s 0x20
0x8f4d  ldarg.0
0x8f4e  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x8f53  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x8f58  brfalse.s loc_8F75
0x8f5a  ldarg.0
0x8f5b  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x8f60  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x8f65  stloc.s  5
0x8f67  ldloca.s 5
0x8f69  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f6e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8f73  br.s     loc_8F7A
0x8f75  ldstr    a0// "0"
0x8f7a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x8f7f  ldarg.0
0x8f80  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::_customHtmlAttributes
0x8f85  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x8f8a  stloc.s  6
0x8f8c  br.s     loc_8FAC
0x8f8e  ldloca.s 6
0x8f90  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x8f95  stloc.s  7
0x8f97  ldarg.1
0x8f98  ldloca.s 7
0x8f9a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x8f9f  ldloca.s 7
0x8fa1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x8fa6  ldc.i4.0
0x8fa7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string, bool)
0x8fac  ldloca.s 6
0x8fae  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x8fb3  brtrue.s loc_8F8E
0x8fb5  leave.s  loc_8FC5
0x8fb7  ldloca.s 6
0x8fb9  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x8fbf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8fc4  endfinally
0x8fc5  ldarg.0
0x8fc6  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::_formDataControl
0x8fcb  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_HasCompositeData()
0x8fd0  brfalse.s loc_9046
0x8fd2  ldarg.0
0x8fd3  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::_formDataControl
0x8fd8  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::get_Parent()
0x8fdd  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell
0x8fe2  brfalse.s loc_901B
0x8fe4  ldarg.0
0x8fe5  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::_formDataControl
0x8fea  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::get_Parent()
0x8fef  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell
0x8ff4  stloc.s  8
0x8ff6  ldloc.s  8
0x8ff8  brfalse.s loc_901B
0x8ffa  ldarg.1
0x8ffb  ldstr    aCompositerequi// "compositeRequiredLevel"
0x9000  ldloc.s  8
0x9002  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_RequiredLevel()
0x9007  stloc.s  9
0x9009  ldloca.s 9
0x900b  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel
0x9011  callvirt instance string [mscorlib]System.Object::ToString()
0x9016  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x901b  ldarg.1
0x901c  ldstr    aHascompositeda// "hasCompositeData"
0x9021  ldstr    aTrue// "true"
0x9026  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x902b  ldarg.1
0x902c  ldstr    aCompositionlin_0// "compositionLinkControlId"
0x9031  ldarg.0
0x9032  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::_formDataControl
0x9037  callvirt instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_CompositionLinkControl()
0x903c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9041  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x9046  ldarg.0
0x9047  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x904c  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x9051  brfalse  loc_9133
0x9056  ldarg.0
0x9057  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x905c  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x9061  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x9066  brfalse  loc_9133
0x906b  ldarg.0
0x906c  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x9071  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x9076  brtrue.s loc_907F
0x9078  ldstr    aUnbound_0// "unbound"
0x907d  br.s     loc_9094
0x907f  ldarg.0
0x9080  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x9085  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x908a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x908f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x9094  stloc.s  0xA
0x9096  ldarg.0
0x9097  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x909c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x90a1  brfalse.s loc_90BC
0x90a3  ldarg.1
0x90a4  ldc.i4.s 0xA
0x90a6  ldstr    aMsCrmInlineChr// "ms-crm-Inline-Chrome "
0x90ab  ldloc.s  0xA
0x90ad  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x90b2  call     string [mscorlib]System.String::Concat(string, string)
0x90b7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x90bc  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x90c1  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x90c6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSafari(class [System.Web]System.Web.HttpRequest)
0x90cb  brfalse  loc_9178
0x90d0  ldarg.0
0x90d1  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x90d6  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x90db  ldstr    aHeader// "header_"
0x90e0  ldloc.0
0x90e1  call     string [mscorlib]System.String::Concat(string, string)
0x90e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x90eb  brfalse  loc_9178
0x90f0  ldarg.0
0x90f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::_customHtmlAttributes
0x90f6  ldstr    aLookupstyle// "lookupstyle"
0x90fb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x9100  brtrue.s loc_9178
0x9102  ldarg.1
0x9103  ldstr    aAriaLabelledby// "aria-labelledby"
0x9108  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x910d  ldstr    a0C0D// "{0}_c  {0}_d"
0x9112  ldc.i4.1
0x9113  newarr   [mscorlib]System.Object
0x9118  dup
0x9119  ldc.i4.0
0x911a  ldarg.0
0x911b  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x9120  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9125  stelem.ref
0x9126  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x912b  ldc.i4.1
0x912c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string, bool)
0x9131  br.s     loc_9178
0x9133  ldarg.0
0x9134  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x9139  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x913e  brfalse.s loc_9178
0x9140  ldarg.0
0x9141  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x9146  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x914b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x9150  brfalse.s loc_9178
0x9152  ldarg.0
0x9153  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x9158  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x915d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x9162  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x9167  ldc.i4.s 0x17
0x9169  bne.un.s loc_9178
0x916b  ldarg.1
0x916c  ldc.i4.s 0xA
0x916e  ldstr    aMsCrmInlineChr// "ms-crm-Inline-Chrome "
0x9173  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x9178  ldarg.1
0x9179  ldc.i4.s 0x19
0x917b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x9180  ldarg.1
0x9181  ldc.i4.s 0xA
0x9183  ldarg.0
0x9184  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::GetValueElementCssClass()
0x9189  ldc.i4.0
0x918a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string, bool)
0x918f  ldarg.1
0x9190  ldc.i4.s 0x19
0x9192  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x9197  ldarg.0
0x9198  ldarg.1
0x9199  ldloc.0
0x919a  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::RenderAccessibilityTags(class [System.Web]System.Web.UI.HtmlTextWriter writer, string attributeLogicalName)
0x919f  ldarg.1
0x91a0  ldc.i4.s 0x4C
0x91a2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x91a7  ret
```
