# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::Render

- ea: `0x2fe0`
- end: `0x34e2`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::Render`
- size: `1282`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xfaf0`

## callees

- `0x1230`
- `0x1330`
- `0x1450`
- `0x2e40`
- `0x2f80`
- `0x2fe0`

## string_xrefs

- `0x30b8`: `ms-crm-Lookup-Item-Read`
- `0x330a`: `ms-crm-Lookup-Item-Read`
- `0x32bf`: `_noread`
- `0x337d`: `Mscrm.ReadFormUtilities.openLookup(true, new Sys.UI.DomEvent(event))`
- `0x33b0`: `Mscrm.ReadFormUtilities.keyDownHandler(new Sys.UI.DomEvent(event));`

## pseudocode

```c

```

## disassembly

```asm
0x2fe0  ldarg.0
0x2fe1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x2fe6  brtrue.s loc_2FF0
0x2fe8  ldarg.0
0x2fe9  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2fee  br.s     loc_2FFB
0x2ff0  ldarg.0
0x2ff1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x2ff6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x2ffb  stloc.0
0x2ffc  ldarg.0
0x2ffd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x3002  brfalse.s loc_3039
0x3004  ldarg.0
0x3005  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x300a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x300f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x3014  ldc.i4.s 0xB
0x3016  bne.un.s loc_3039
0x3018  ldarg.0
0x3019  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x301e  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x3023  brtrue.s loc_3039
0x3025  ldarg.1
0x3026  ldarg.0
0x3027  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TemplateRenderer()
0x302c  ldc.i4.1
0x302d  ldloc.0
0x302e  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer::GetTemplateBindingHtml(bool, string)
0x3033  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3038  ret
0x3039  ldarg.0
0x303a  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TemplateRenderer()
0x303f  ldc.i4.0
0x3040  ldloc.0
0x3041  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer::GetTemplateBindingHtml(bool, string)
0x3046  stloc.1
0x3047  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x304c  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x3051  ldc.i4.2
0x3052  newarr   [mscorlib]System.Object
0x3057  dup
0x3058  ldc.i4.0
0x3059  ldloc.0
0x305a  stelem.ref
0x305b  dup
0x305c  ldc.i4.1
0x305d  ldstr    aImg// "img"
0x3062  stelem.ref
0x3063  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3068  stloc.2
0x3069  ldarg.0
0x306a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x306f  brfalse  loc_31F3
0x3074  ldarg.0
0x3075  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x307a  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x307f  brfalse  loc_31F3
0x3084  ldarg.0
0x3085  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::_lookupStyle
0x308a  ldstr    aMulti// "multi"
0x308f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3094  brfalse.s loc_3106
0x3096  ldarg.1
0x3097  ldstr    aSpan// "span"
0x309c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x30a1  ldarg.1
0x30a2  ldstr    aContenteditabl// "contentEditable"
0x30a7  ldstr    aFalse// "false"
0x30ac  ldc.i4.0
0x30ad  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x30b2  ldarg.1
0x30b3  ldstr    aClass// "class"
0x30b8  ldstr    aMsCrmLookupIte// "ms-crm-Lookup-Item-Read"
0x30bd  ldc.i4.0
0x30be  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x30c3  ldstr    aId// "id"
0x30c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30cd  ldstr    a0Lookupvalue// "{0}_lookupValue"
0x30d2  ldc.i4.1
0x30d3  newarr   [mscorlib]System.Object
0x30d8  dup
0x30d9  ldc.i4.0
0x30da  ldarg.0
0x30db  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x30e0  stelem.ref
0x30e1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x30e6  ldarg.1
0x30e7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x30ec  ldarg.1
0x30ed  ldc.i4.s 0x3E
0x30ef  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x30f4  ldarg.1
0x30f5  ldloc.1
0x30f6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x30fb  ldarg.1
0x30fc  ldstr    aSpan// "span"
0x3101  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x3106  ldarg.1
0x3107  ldstr    aDiv// "div"
0x310c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x3111  ldarg.1
0x3112  ldstr    aClass// "class"
0x3117  ldstr    aMsCrmInlineEdi// "ms-crm-Inline-EditIcon"
0x311c  ldc.i4.0
0x311d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x3122  ldstr    aId// "id"
0x3127  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x312c  ldstr    a0Lookupsearchi// "{0}_lookupSearchIconDiv"
0x3131  ldc.i4.1
0x3132  newarr   [mscorlib]System.Object
0x3137  dup
0x3138  ldc.i4.0
0x3139  ldarg.0
0x313a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x313f  stelem.ref
0x3140  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3145  ldarg.1
0x3146  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x314b  ldarg.1
0x314c  ldc.i4.s 0x3E
0x314e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x3153  ldarg.1
0x3154  ldstr    aImg// "img"
0x3159  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x315e  ldarg.1
0x315f  ldstr    aSrc// "src"
0x3164  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x3169  ldc.i4.1
0x316a  newarr   [mscorlib]System.Char
0x316f  dup
0x3170  ldc.i4.0
0x3171  ldc.i4.s 0x2F
0x3173  stelem.i2
0x3174  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x3179  ldstr    aImgsImagestrip// "/_imgs/imagestrips/transparent_spacer.g"...
0x317e  call     string [mscorlib]System.String::Concat(string, string)
0x3183  ldc.i4.0
0x3184  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x3189  ldstr    aId// "id"
0x318e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3193  ldstr    a0Lookupsearchi_0// "{0}_lookupSearchIcon"
0x3198  ldc.i4.1
0x3199  newarr   [mscorlib]System.Object
0x319e  dup
0x319f  ldc.i4.0
0x31a0  ldarg.0
0x31a1  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x31a6  stelem.ref
0x31a7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31ac  ldarg.1
0x31ad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x31b2  ldarg.1
0x31b3  ldstr    aClass// "class"
0x31b8  ldstr    aMsCrmImagestri_0// "ms-crm-ImageStrip-search_normal ms-crm-"...
0x31bd  ldc.i4.0
0x31be  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x31c3  ldarg.1
0x31c4  ldstr    aAlt// "alt"
0x31c9  ldsfld   string [mscorlib]System.String::Empty
0x31ce  ldc.i4.0
0x31cf  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x31d4  ldarg.1
0x31d5  ldc.i4.s 0x3E
0x31d7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x31dc  ldarg.1
0x31dd  ldstr    aImg// "img"
0x31e2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x31e7  ldarg.1
0x31e8  ldstr    aDiv// "div"
0x31ed  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x31f2  ret
0x31f3  ldarg.0
0x31f4  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_ShowAsBreadcrumbControl()
0x31f9  brfalse.s loc_3203
0x31fb  ldstr    aNone// "none"
0x3200  stloc.3
0x3201  br.s     loc_3225
0x3203  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3208  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x320d  ldc.i4.2
0x320e  newarr   [mscorlib]System.Object
0x3213  dup
0x3214  ldc.i4.0
0x3215  ldloc.0
0x3216  stelem.ref
0x3217  dup
0x3218  ldc.i4.1
0x3219  ldstr    aVisible// "_visible"
0x321e  stelem.ref
0x321f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3224  stloc.3
0x3225  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x322a  ldstr    aDisplay0// "display:{0};"
0x322f  ldc.i4.1
0x3230  newarr   [mscorlib]System.Object
0x3235  dup
0x3236  ldc.i4.0
0x3237  ldloc.3
0x3238  stelem.ref
0x3239  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x323e  stloc.s  4
0x3240  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3245  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x324a  ldc.i4.2
0x324b  newarr   [mscorlib]System.Object
0x3250  dup
0x3251  ldc.i4.0
0x3252  ldloc.0
0x3253  stelem.ref
0x3254  dup
0x3255  ldc.i4.1
0x3256  ldstr    aOid// "oid"
0x325b  stelem.ref
0x325c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3261  stloc.s  5
0x3263  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3268  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x326d  ldc.i4.2
0x326e  newarr   [mscorlib]System.Object
0x3273  dup
0x3274  ldc.i4.0
0x3275  ldloc.0
0x3276  stelem.ref
0x3277  dup
0x3278  ldc.i4.1
0x3279  ldstr    aOtype// "otype"
0x327e  stelem.ref
0x327f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3284  stloc.s  6
0x3286  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x328b  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x3290  ldc.i4.2
0x3291  newarr   [mscorlib]System.Object
0x3296  dup
0x3297  ldc.i4.0
0x3298  ldloc.0
0x3299  stelem.ref
0x329a  dup
0x329b  ldc.i4.1
0x329c  ldstr    aOtypename// "otypename"
0x32a1  stelem.ref
0x32a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32a7  stloc.s  7
0x32a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32ae  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x32b3  ldc.i4.2
0x32b4  newarr   [mscorlib]System.Object
0x32b9  dup
0x32ba  ldc.i4.0
0x32bb  ldloc.0
0x32bc  stelem.ref
0x32bd  dup
0x32be  ldc.i4.1
0x32bf  ldstr    aNoread// "_noread"
0x32c4  stelem.ref
0x32c5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32ca  stloc.s  8
0x32cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32d1  ldstr    aDisplay0// "display:{0};"
0x32d6  ldc.i4.1
0x32d7  newarr   [mscorlib]System.Object
0x32dc  dup
0x32dd  ldc.i4.0
0x32de  ldloc.s  8
0x32e0  stelem.ref
0x32e1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32e6  stloc.s  9
0x32e8  ldarg.1
0x32e9  ldstr    aSpan// "span"
0x32ee  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x32f3  ldarg.1
0x32f4  ldstr    aContenteditabl// "contentEditable"
0x32f9  ldstr    aFalse// "false"
0x32fe  ldc.i4.0
0x32ff  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x3304  ldarg.1
0x3305  ldstr    aClass// "class"
0x330a  ldstr    aMsCrmLookupIte// "ms-crm-Lookup-Item-Read"
0x330f  ldc.i4.0
0x3310  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x3315  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x331a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x331f  brtrue.s loc_3332
0x3321  ldarg.1
0x3322  ldstr    aRole// "role"
0x3327  ldstr    aLink// "link"
0x332c  ldc.i4.0
0x332d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x3332  ldarg.1
0x3333  ldstr    aStyle// "style"
0x3338  ldloc.s  4
0x333a  ldc.i4.0
0x333b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x3340  ldarg.1
0x3341  ldstr    aTitle// "title"
0x3346  ldloc.1
0x3347  ldc.i4.0
0x3348  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x334d  ldarg.1
  ... truncated ...
```
