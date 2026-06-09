# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.KBViewerControl::Render

- ea: `0x2910`
- end: `0x2afd`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.KBViewerControl::Render`
- size: `493`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1290`
- `0x1330`
- `0x2910`

## string_xrefs

- `0x29c0`: `" onclick="Mscrm.ReadFormUtilities.toggleArticleViewer('`
- `0x29ff`: `)" onkeydown="Mscrm.ReadFormUtilities.showKBCheckBoxKeyDownHandler(new Sys.UI.DomEvent(event))" />`

## pseudocode

```c

```

## disassembly

```asm
0x2910  ldarg.0
0x2911  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2916  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x291b  stloc.0
0x291c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2921  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x2926  ldc.i4.2
0x2927  newarr   [mscorlib]System.Object
0x292c  dup
0x292d  ldc.i4.0
0x292e  ldstr    aKbarticleid// "kbarticleid"
0x2933  stelem.ref
0x2934  dup
0x2935  ldc.i4.1
0x2936  ldstr    aOid// "oid"
0x293b  stelem.ref
0x293c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2941  stloc.1
0x2942  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2947  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x294c  ldc.i4.2
0x294d  newarr   [mscorlib]System.Object
0x2952  dup
0x2953  ldc.i4.0
0x2954  ldstr    aKbarticleid// "kbarticleid"
0x2959  stelem.ref
0x295a  dup
0x295b  ldc.i4.1
0x295c  ldstr    aVisible// "_visible"
0x2961  stelem.ref
0x2962  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2967  stloc.2
0x2968  ldarg.0
0x2969  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x296e  stloc.3
0x296f  ldarg.0
0x2970  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2975  ldc.i4.s 0xA
0x2977  add
0x2978  stloc.s  4
0x297a  ldarg.1
0x297b  ldstr    aTableStyleWidt// "<table style=\"width:100%;display:"
0x2980  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2985  ldarg.1
0x2986  ldloc.2
0x2987  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x298c  ldarg.1
0x298d  ldstr    aTrValignTopTdI// "\"><tr valign=\"top\" ><td ><input type"...
0x2992  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2997  ldstr    aShowkbviewer// "showKBViewer"
0x299c  ldarg.1
0x299d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x29a2  ldarg.1
0x29a3  ldstr    aClassMsCrmChec// "\" class=\"ms-crm-CheckBox\" style=\"be"...
0x29a8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29ad  ldloca.s 3
0x29af  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29b4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x29b9  ldarg.1
0x29ba  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x29bf  ldarg.1
0x29c0  ldstr    aOnclickMscrmRe// "\" onclick=\"Mscrm.ReadFormUtilities.to"...
0x29c5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29ca  ldloc.0
0x29cb  ldarg.1
0x29cc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x29d1  ldarg.0
0x29d2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x29d7  brfalse.s loc_29F3
0x29d9  ldarg.0
0x29da  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x29df  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x29e4  brfalse.s loc_29F3
0x29e6  ldarg.1
0x29e7  ldstr    aTrue_0// "',true"
0x29ec  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29f1  br.s     loc_29FE
0x29f3  ldarg.1
0x29f4  ldstr    asc_318FC// "'"
0x29f9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29fe  ldarg.1
0x29ff  ldstr    aOnkeydownMscrm// ")\" onkeydown=\"Mscrm.ReadFormUtilities"...
0x2a04  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2a09  ldarg.1
0x2a0a  ldstr    aNbspLabelFor// "&nbsp;<label for=\""
0x2a0f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2a14  ldstr    aShowkbviewer// "showKBViewer"
0x2a19  ldarg.1
0x2a1a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x2a1f  ldarg.1
0x2a20  ldstr    asc_319EC// "\">"
0x2a25  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2a2a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2a2f  ldstr    aKbviewerLabelS// "KBViewer_Label_ShowViewer"
0x2a34  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2a39  ldarg.1
0x2a3a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x2a3f  ldarg.1
0x2a40  ldstr    aLabelTdTr// "</label></td></tr>"
0x2a45  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2a4a  ldarg.1
0x2a4b  ldstr    aTrHeightAutoTd// "<tr height=\"auto\"  ><td ><iframe id="...
0x2a50  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2a55  ldloc.0
0x2a56  ldarg.1
0x2a57  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x2a5c  ldarg.1
0x2a5d  ldstr    aTabindex_1// "\" tabIndex=\""
0x2a62  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2a67  ldloca.s 4
0x2a69  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2a6e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2a73  ldarg.1
0x2a74  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x2a79  ldarg.1
0x2a7a  ldstr    aClassNoneStyle// "\" class=\"none\" style=\"display:none;"...
0x2a7f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2a84  ldarg.1
0x2a85  ldstr    aStaticBlankHtm// "/_static/blank.htm"
0x2a8a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2a8f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2a94  callvirt instance void [mscorlib]System.IO.TextWriter::Write(object)
0x2a99  ldarg.1
0x2a9a  ldstr    aUrl_1// "\" url=\""
0x2a9f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2aa4  ldstr    aCsArticlesView// "/CS/articles/viewer/default.aspx?IsRest"...
0x2aa9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2aae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2ab3  dup
0x2ab4  callvirt instance string [mscorlib]System.Object::ToString()
0x2ab9  ldarg.1
0x2aba  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x2abf  ldarg.0
0x2ac0  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x2ac5  brfalse.s loc_2ADB
0x2ac7  ldarg.0
0x2ac8  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x2acd  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x2ad2  brtrue.s loc_2ADB
0x2ad4  ldarg.1
0x2ad5  ldloc.1
0x2ad6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2adb  ldarg.1
0x2adc  ldstr    aBasesrc// "\" baseSrc=\""
0x2ae1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2ae6  callvirt instance string [mscorlib]System.Object::ToString()
0x2aeb  ldarg.1
0x2aec  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x2af1  ldarg.1
0x2af2  ldstr    aIframeTdTrTabl// "\"></iframe></td></tr></table>"
0x2af7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2afc  ret
```
