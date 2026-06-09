# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::EndRender

- ea: `0x91b0`
- end: `0x93dd`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::EndRender`
- size: `557`
- prototype: ``
- caller_count: `18`
- callee_count: `7`
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

- `0x1330`
- `0x15b0`
- `0x16a0`
- `0x16c0`
- `0x8e20`
- `0x91b0`
- `0x95e0`

## pseudocode

```c

```

## disassembly

```asm
0x91b0  ldarg.0
0x91b1  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::IsTextWrapDisabledForOrganization()
0x91b6  brfalse.s loc_91C3
0x91b8  ldarg.1
0x91b9  ldstr    aDivClassMsCrmI// "<div class=\"ms-crm-Inline-GradientMask"...
0x91be  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x91c3  ldarg.1
0x91c4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x91c9  ldarg.1
0x91ca  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x91cf  ldarg.0
0x91d0  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x91d5  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x91da  brfalse  loc_939D
0x91df  ldarg.0
0x91e0  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x91e5  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x91ea  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x91ef  brfalse  loc_939D
0x91f4  ldarg.0
0x91f5  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x91fa  ldarg.1
0x91fb  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::RenderEditMode(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x9200  ldarg.1
0x9201  ldstr    aSpanClassMsCrm// "<span class=\"ms-crm-Inline-LockIcon\""
0x9206  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x920b  ldstr    aId// "id"
0x9210  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9215  ldstr    a0Lock// "{0}_lock"
0x921a  ldc.i4.1
0x921b  newarr   [mscorlib]System.Object
0x9220  dup
0x9221  ldc.i4.0
0x9222  ldarg.0
0x9223  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x9228  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x922d  stelem.ref
0x922e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9233  ldarg.1
0x9234  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x9239  ldstr    aStyleDisplayNo// "style=\"display: none;\"><img src=\"/{0"...
0x923e  stloc.0
0x923f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9244  ldstr    aToolsFormedito// "Tools.FormEditor.Control.Locked"
0x9249  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x924e  stloc.1
0x924f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x9254  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x9259  brtrue.s loc_927B
0x925b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9260  ldloc.0
0x9261  ldc.i4.2
0x9262  newarr   [mscorlib]System.Object
0x9267  dup
0x9268  ldc.i4.0
0x9269  ldstr    aImgsInlineedit_0// "_imgs/inlineedit/locked_white.png"
0x926e  stelem.ref
0x926f  dup
0x9270  ldc.i4.1
0x9271  ldloc.1
0x9272  stelem.ref
0x9273  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9278  stloc.0
0x9279  br.s     loc_9299
0x927b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9280  ldloc.0
0x9281  ldc.i4.2
0x9282  newarr   [mscorlib]System.Object
0x9287  dup
0x9288  ldc.i4.0
0x9289  ldstr    aImgsImagestrip_0// "_imgs/imagestrips/transparent_spacer.gi"...
0x928e  stelem.ref
0x928f  dup
0x9290  ldc.i4.1
0x9291  ldloc.1
0x9292  stelem.ref
0x9293  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9298  stloc.0
0x9299  ldarg.1
0x929a  ldloc.0
0x929b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x92a0  ldarg.1
0x92a1  ldstr    aSpanClassMsCrm_0// "<span class=\"ms-crm-Inline-fieldChange"...
0x92a6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x92ab  ldstr    aId// "id"
0x92b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x92b5  ldstr    a0Fieldchangein// "{0}_fieldChangeIndicatorImage"
0x92ba  ldc.i4.1
0x92bb  newarr   [mscorlib]System.Object
0x92c0  dup
0x92c1  ldc.i4.0
0x92c2  ldarg.0
0x92c3  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x92c8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x92cd  stelem.ref
0x92ce  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x92d3  ldarg.1
0x92d4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x92d9  ldstr    aStyleVisibilit// "style=\"visibility: hidden;\"><img src="...
0x92de  stloc.2
0x92df  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x92e4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x92e9  brtrue.s loc_9307
0x92eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x92f0  ldloc.2
0x92f1  ldc.i4.1
0x92f2  newarr   [mscorlib]System.Object
0x92f7  dup
0x92f8  ldc.i4.0
0x92f9  ldstr    aImgsInlineedit_1// "_imgs/inlineedit/field_change_indicator"...
0x92fe  stelem.ref
0x92ff  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9304  stloc.2
0x9305  br.s     loc_9321
0x9307  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x930c  ldloc.2
0x930d  ldc.i4.1
0x930e  newarr   [mscorlib]System.Object
0x9313  dup
0x9314  ldc.i4.0
0x9315  ldstr    aImgsImagestrip_0// "_imgs/imagestrips/transparent_spacer.gi"...
0x931a  stelem.ref
0x931b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9320  stloc.2
0x9321  ldarg.1
0x9322  ldloc.2
0x9323  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9328  ldstr    aSpanId0Warnspa// "<span id=\"{0}_warnSpan\" class=\"ms-cr"...
0x932d  stloc.3
0x932e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x9333  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x9338  brtrue.s loc_9369
0x933a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x933f  ldloc.3
0x9340  ldc.i4.2
0x9341  newarr   [mscorlib]System.Object
0x9346  dup
0x9347  ldc.i4.0
0x9348  ldarg.0
0x9349  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x934e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9353  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x9358  stelem.ref
0x9359  dup
0x935a  ldc.i4.1
0x935b  ldstr    aImgsErrorNotif// "/_imgs/error/notif_icn_crit16.png"
0x9360  stelem.ref
0x9361  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9366  stloc.3
0x9367  br.s     loc_9396
0x9369  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x936e  ldloc.3
0x936f  ldc.i4.2
0x9370  newarr   [mscorlib]System.Object
0x9375  dup
0x9376  ldc.i4.0
0x9377  ldarg.0
0x9378  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::get_FormDataControl()
0x937d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9382  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x9387  stelem.ref
0x9388  dup
0x9389  ldc.i4.1
0x938a  ldstr    aImgsImagestrip// "/_imgs/imagestrips/transparent_spacer.g"...
0x938f  stelem.ref
0x9390  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9395  stloc.3
0x9396  ldarg.1
0x9397  ldloc.3
0x9398  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x939d  ldarg.1
0x939e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x93a3  ldarg.0
0x93a4  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::_formDataControl
0x93a9  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_HasCompositeData()
0x93ae  brfalse.s loc_93DC
0x93b0  ldarg.1
0x93b1  ldc.i4.s 0x12
0x93b3  ldstr    aNone// "none"
0x93b8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x93bd  ldarg.1
0x93be  ldc.i4.s 0x19
0x93c0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x93c5  ldarg.0
0x93c6  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::_formDataControl
0x93cb  callvirt instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_CompositionLinkControl()
0x93d0  ldarg.1
0x93d1  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x93d6  ldarg.1
0x93d7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x93dc  ret
```
