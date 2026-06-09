# Microsoft.Crm.Application.Controls.AppHtmlBarControl::RenderProcessHtmlBarControls

- ea: `0x88650`
- end: `0x8869a`
- name: `Microsoft.Crm.Application.Controls.AppHtmlBarControl::RenderProcessHtmlBarControls`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x88240`

## callees

- `0x885d0`

## string_xrefs

- `0x88683`: `cmd-insertHyperlink`
- `0x8866e`: `AddHyperlinkEmailBody();`
- `0x88679`: `Web.SFA.Workflow.InsertHyperlinkDialog.Title`
- `0x88688`: `idinserthyperlink`

## pseudocode

```c

```

## disassembly

```asm
0x88650  ldarg.0
0x88651  ldarg.1
0x88652  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter)
0x88657  ldarg.0
0x88658  ldc.i4.0
0x88659  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::set_AllowSpacer(bool)
0x8865e  ldarg.0
0x8865f  ldarg.1
0x88660  call     instance void Microsoft.Crm.Application.Controls.AppHtmlBarControl::AddInsertKBArticleButton(class [mscorlib]System.IO.TextWriter writer)
0x88665  ldarg.0
0x88666  ldarg.1
0x88667  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter)
0x8866c  ldarg.0
0x8866d  ldarg.1
0x8866e  ldstr    aAddhyperlinkem// "AddHyperlinkEmailBody();"
0x88673  ldarg.0
0x88674  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppHtmlBarControl::_rm
0x88679  ldstr    aWebSfaWorkflow_77// "Web.SFA.Workflow.InsertHyperlinkDialog."...
0x8867e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88683  ldstr    aCmdInserthyper// "cmd-insertHyperlink"
0x88688  ldstr    aIdinserthyperl// "idinserthyperlink"
0x8868d  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::AddTextButton(class [mscorlib]System.IO.TextWriter, string, string, string, string)
0x88692  ldarg.0
0x88693  ldc.i4.1
0x88694  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::set_AllowSpacer(bool)
0x88699  ret
```
