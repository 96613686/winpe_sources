# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::Render

- ea: `0x79f0`
- end: `0x7c9c`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::Render`
- size: `684`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x4f0`
- `0x1290`
- `0x7860`
- `0x78a0`
- `0x79f0`
- `0x7fb0`

## string_xrefs

- `0x7a8b`: `activityMoreCommands`

## pseudocode

```c

```

## disassembly

```asm
0x79f0  ldarg.0
0x79f1  call     instance void [System.Web]System.Web.UI.Control::EnsureChildControls()
0x79f6  ldarg.0
0x79f7  ldarg.0
0x79f8  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x79fd  stfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_currentTabIndexCount
0x7a02  ldarg.1
0x7a03  ldstr    aDivId// "<div id=\""
0x7a08  ldarg.0
0x7a09  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x7a0e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x7a13  ldstr    asc_319EC// "\">"
0x7a18  call     string [mscorlib]System.String::Concat(string, string, string)
0x7a1d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7a22  ldarg.1
0x7a23  ldc.i4.s 0x19
0x7a25  stloc.1
0x7a26  ldloca.s 1
0x7a28  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x7a2e  callvirt instance string [mscorlib]System.Object::ToString()
0x7a33  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x7a38  ldarg.1
0x7a39  ldc.i4.s 0x3E
0x7a3b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7a40  ldarg.1
0x7a41  ldc.i4.s 0x19
0x7a43  stloc.1
0x7a44  ldloca.s 1
0x7a46  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x7a4c  callvirt instance string [mscorlib]System.Object::ToString()
0x7a51  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x7a56  ldarg.1
0x7a57  ldstr    aClass// "class"
0x7a5c  ldstr    aActivityBarLab// "activity-bar-label"
0x7a61  ldc.i4.0
0x7a62  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x7a67  ldarg.1
0x7a68  ldc.i4.s 0x3E
0x7a6a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7a6f  ldarg.1
0x7a70  ldc.i4.s 0x4C
0x7a72  stloc.1
0x7a73  ldloca.s 1
0x7a75  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x7a7b  callvirt instance string [mscorlib]System.Object::ToString()
0x7a80  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x7a85  ldarg.1
0x7a86  ldstr    aClass// "class"
0x7a8b  ldstr    aActivitymoreco_0// "activityMoreCommands"
0x7a90  ldc.i4.0
0x7a91  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x7a96  ldarg.1
0x7a97  ldstr    aAction// "action"
0x7a9c  ldarg.0
0x7a9d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filterButton
0x7aa2  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Action()
0x7aa7  ldc.i4.0
0x7aa8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x7aad  ldarg.1
0x7aae  ldc.i4.s 0x3E
0x7ab0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ab5  ldarg.0
0x7ab6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filterButton
0x7abb  brfalse.s loc_7B08
0x7abd  ldarg.0
0x7abe  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filterButton
0x7ac3  ldarg.0
0x7ac4  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_currentTabIndexCount
0x7ac9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::set_TabIndex(int32)
0x7ace  ldarg.0
0x7acf  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filterButton
0x7ad4  ldc.i4.1
0x7ad5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_DownArrow(bool)
0x7ada  ldarg.0
0x7adb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filterButton
0x7ae0  ldarg.1
0x7ae1  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x7ae6  ldarg.0
0x7ae7  ldarg.0
0x7ae8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filterButton
0x7aed  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::SetDisabled(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton button)
0x7af2  ldarg.1
0x7af3  ldc.i4.s 0x4C
0x7af5  stloc.1
0x7af6  ldloca.s 1
0x7af8  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x7afe  callvirt instance string [mscorlib]System.Object::ToString()
0x7b03  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x7b08  ldarg.1
0x7b09  ldc.i4.s 0x19
0x7b0b  stloc.1
0x7b0c  ldloca.s 1
0x7b0e  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x7b14  callvirt instance string [mscorlib]System.Object::ToString()
0x7b19  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x7b1e  ldarg.0
0x7b1f  ldarg.0
0x7b20  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_currentTabIndexCount
0x7b25  ldc.i4.s 0xA
0x7b27  add
0x7b28  stfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_currentTabIndexCount
0x7b2d  ldarg.1
0x7b2e  ldc.i4.s 0x19
0x7b30  stloc.1
0x7b31  ldloca.s 1
0x7b33  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x7b39  callvirt instance string [mscorlib]System.Object::ToString()
0x7b3e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x7b43  ldarg.1
0x7b44  ldc.i4.s 0x3E
0x7b46  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7b4b  ldarg.0
0x7b4c  ldarg.1
0x7b4d  call     instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::RenderActivitySelectionBar(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x7b52  stloc.0
0x7b53  ldarg.0
0x7b54  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MoreActivitiesButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_moreActivitiesButton
0x7b59  brfalse.s loc_7B7F
0x7b5b  ldarg.0
0x7b5c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MoreActivitiesButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_moreActivitiesButton
0x7b61  ldloc.0
0x7b62  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::set_TabIndex(int32)
0x7b67  ldarg.0
0x7b68  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MoreActivitiesButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_moreActivitiesButton
0x7b6d  ldarg.1
0x7b6e  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x7b73  ldarg.0
0x7b74  ldarg.0
0x7b75  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MoreActivitiesButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_moreActivitiesButton
0x7b7a  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::SetDisabled(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton button)
0x7b7f  ldarg.1
0x7b80  ldstr    aSpanStyleWidth// "<span style=\"width: 50px;\" class=\"ms"...
0x7b85  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7b8a  ldarg.0
0x7b8b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallSortButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_sortActivitiesButton
0x7b90  brfalse.s loc_7BB6
0x7b92  ldarg.0
0x7b93  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallSortButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_sortActivitiesButton
0x7b98  ldloc.0
0x7b99  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::set_TabIndex(int32)
0x7b9e  ldarg.0
0x7b9f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallSortButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_sortActivitiesButton
0x7ba4  ldarg.1
0x7ba5  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x7baa  ldarg.0
0x7bab  ldarg.0
0x7bac  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallSortButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_sortActivitiesButton
0x7bb1  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::SetDisabled(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton button)
0x7bb6  ldarg.0
0x7bb7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filter
0x7bbc  brfalse.s loc_7BE2
0x7bbe  ldarg.0
0x7bbf  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filter
0x7bc4  ldloc.0
0x7bc5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::set_TabIndex(int32)
0x7bca  ldarg.0
0x7bcb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filter
0x7bd0  ldarg.1
0x7bd1  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x7bd6  ldarg.0
0x7bd7  ldarg.0
0x7bd8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filter
0x7bdd  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::SetDisabled(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton button)
0x7be2  ldarg.0
0x7be3  ldarg.1
0x7be4  ldloc.0
0x7be5  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::RenderAssociatedViewButton(class [System.Web]System.Web.UI.HtmlTextWriter writer, int32 tabIndexCurrent)
0x7bea  ldarg.1
0x7beb  ldc.i4.s 0x19
0x7bed  stloc.1
0x7bee  ldloca.s 1
0x7bf0  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x7bf6  callvirt instance string [mscorlib]System.Object::ToString()
0x7bfb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x7c00  ldarg.1
0x7c01  ldc.i4.s 0x19
0x7c03  stloc.1
0x7c04  ldloca.s 1
0x7c06  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x7c0c  callvirt instance string [mscorlib]System.Object::ToString()
0x7c11  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x7c16  ldarg.0
0x7c17  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_inlineActivities
0x7c1c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity>::GetEnumerator()
0x7c21  stloc.2
0x7c22  br.s     loc_7C52
0x7c24  ldloca.s 2
0x7c26  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity>::get_Current()
0x7c2b  stloc.3
0x7c2c  ldloc.3
0x7c2d  ldarg.0
0x7c2e  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_currentTabIndexCount
0x7c33  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity::set_TabIndex(int32)
0x7c38  ldloc.3
0x7c39  ldarg.1
0x7c3a  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x7c3f  ldarg.0
0x7c40  ldarg.0
0x7c41  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_currentTabIndexCount
0x7c46  ldloc.3
0x7c47  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity::TabIndexCount()
0x7c4c  add
0x7c4d  stfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_currentTabIndexCount
0x7c52  ldloca.s 2
0x7c54  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity>::MoveNext()
0x7c59  brtrue.s loc_7C24
0x7c5b  leave.s  loc_7C6B
0x7c5d  ldloca.s 2
0x7c5f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity>
0x7c65  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7c6a  endfinally
0x7c6b  ldarg.0
0x7c6c  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_activitieswallcontrol
0x7c71  brfalse.s loc_7C90
0x7c73  ldarg.0
0x7c74  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_activitieswallcontrol
0x7c79  ldarg.0
0x7c7a  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_currentTabIndexCount
0x7c7f  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::set_TabIndex(int32 value)
0x7c84  ldarg.0
0x7c85  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_activitieswallcontrol
0x7c8a  ldarg.1
0x7c8b  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x7c90  ldarg.1
0x7c91  ldstr    aDiv_0// "</div>"
0x7c96  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7c9b  ret
```
