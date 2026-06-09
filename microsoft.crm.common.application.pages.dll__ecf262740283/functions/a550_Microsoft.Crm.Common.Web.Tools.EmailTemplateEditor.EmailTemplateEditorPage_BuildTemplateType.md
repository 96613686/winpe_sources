# Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::BuildTemplateType

- ea: `0xa550`
- end: `0xa5e8`
- name: `Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::BuildTemplateType`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9b80`

## callees

- `0xa550`

## string_xrefs

- `0xa571`: `Email_Template_Type_Global`
- `0xa59e`: `Email_Template_Type_Entity`

## pseudocode

```c

```

## disassembly

```asm
0xa550  ldarg.0
0xa551  ldstr    aImgAltSrcImgsI// "<img alt='' src='/_imgs/ico_16_2010.gif"...
0xa556  stfld    string Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_templateTypeHtml
0xa55b  ldarg.0
0xa55c  ldfld    int32 Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_templateTypeCode
0xa561  ldc.i4.8
0xa562  bne.un.s loc_A58C
0xa564  ldarg.0
0xa565  ldarg.0
0xa566  ldfld    string Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_templateTypeHtml
0xa56b  ldarg.0
0xa56c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa571  ldstr    aEmailTemplateT// "Email_Template_Type_Global"
0xa576  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa57b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xa580  call     string [mscorlib]System.String::Concat(string, string)
0xa585  stfld    string Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_templateTypeHtml
0xa58a  br.s     loc_A5D1
0xa58c  ldarg.0
0xa58d  ldarg.0
0xa58e  ldfld    string Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_templateTypeHtml
0xa593  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa598  ldarg.0
0xa599  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa59e  ldstr    aEmailTemplateT_0// "Email_Template_Type_Entity"
0xa5a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa5a8  ldc.i4.1
0xa5a9  newarr   [mscorlib]System.Object
0xa5ae  dup
0xa5af  ldc.i4.0
0xa5b0  ldarg.0
0xa5b1  ldfld    int32 Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_templateTypeCode
0xa5b6  ldc.i4.1
0xa5b7  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xa5bc  stelem.ref
0xa5bd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa5c2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xa5c7  call     string [mscorlib]System.String::Concat(string, string)
0xa5cc  stfld    string Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_templateTypeHtml
0xa5d1  ldarg.0
0xa5d2  ldarg.0
0xa5d3  ldfld    string Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_templateTypeHtml
0xa5d8  ldstr    aSpan// "</span>"
0xa5dd  call     string [mscorlib]System.String::Concat(string, string)
0xa5e2  stfld    string Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_templateTypeHtml
0xa5e7  ret
```
