# Microsoft.Crm.Application.Controls.AppHtmlBarControl::RenderKbTemplateEditorControls

- ea: `0x88320`
- end: `0x883ea`
- name: `Microsoft.Crm.Application.Controls.AppHtmlBarControl::RenderKbTemplateEditorControls`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x88220`

## string_xrefs

- `0x88341`: `PickList_KBTemplateEditor_Selector_Style_Body`
- `0x88361`: `PickList_KBTemplateEditor_Selector_Style_Title`
- `0x88381`: `PickList_KBTemplateEditor_Selector_Style_SectionHeader`
- `0x88396`: `<td style="width:210px;"><table cellpadding=0 cellspacing=0><tr><td CLASS="AppHtmlBarControl_RenderKbTemplateEditorControls_td" nowrap>`
- `0x883a7`: `PickList_KBTemplateEditor_Selector_Label`

## pseudocode

```c

```

## disassembly

```asm
0x88320  ldarg.0
0x88321  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.AppHtmlBarControl::_kbArticleTeplateSelect
0x88326  ldstr    aDonotsubmit// "DoNotSubmit"
0x8832b  ldstr    a1_0// "1"
0x88330  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddExpando(string, string)
0x88335  ldarg.0
0x88336  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.AppHtmlBarControl::_kbArticleTeplateSelect
0x8833b  ldarg.0
0x8833c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppHtmlBarControl::_rm
0x88341  ldstr    aPicklistKbtemp// "PickList_KBTemplateEditor_Selector_Styl"...
0x88346  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8834b  ldstr    aArticle// "article"
0x88350  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x88355  ldarg.0
0x88356  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.AppHtmlBarControl::_kbArticleTeplateSelect
0x8835b  ldarg.0
0x8835c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppHtmlBarControl::_rm
0x88361  ldstr    aPicklistKbtemp_0// "PickList_KBTemplateEditor_Selector_Styl"...
0x88366  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8836b  ldstr    aTitle// "title"
0x88370  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x88375  ldarg.0
0x88376  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.AppHtmlBarControl::_kbArticleTeplateSelect
0x8837b  ldarg.0
0x8837c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppHtmlBarControl::_rm
0x88381  ldstr    aPicklistKbtemp_1// "PickList_KBTemplateEditor_Selector_Styl"...
0x88386  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8838b  ldstr    aHeading_0// "heading"
0x88390  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x88395  ldarg.1
0x88396  ldstr    aTdStyleWidth21// "<td style=\"width:210px;\"><table cellp"...
0x8839b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x883a0  ldarg.1
0x883a1  ldarg.0
0x883a2  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppHtmlBarControl::_rm
0x883a7  ldstr    aPicklistKbtemp_2// "PickList_KBTemplateEditor_Selector_Labe"...
0x883ac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x883b1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x883b6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x883bb  ldarg.1
0x883bc  ldstr    aTdTdStyleWidth// "</td><td style=\"width:100%\" ignorefor"...
0x883c1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x883c6  ldarg.0
0x883c7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.AppHtmlBarControl::_kbArticleTeplateSelect
0x883cc  ldarg.1
0x883cd  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x883d2  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x883d7  ldarg.1
0x883d8  ldstr    aTdTrTableTd// "</td></tr></table></td>"
0x883dd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x883e2  ldarg.0
0x883e3  ldc.i4.1
0x883e4  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::set_AllowSpacer(bool)
0x883e9  ret
```
