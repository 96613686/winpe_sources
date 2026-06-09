# Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::OnNew

- ea: `0x96c0`
- end: `0x970e`
- name: `Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::OnNew`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x96c0`
- `0x9750`

## string_xrefs

- `0x96c6`: `presentationxml`

## pseudocode

```c

```

## disassembly

```asm
0x96c0  ldarg.0
0x96c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x96c6  ldstr    aPresentationxm// "presentationxml"
0x96cb  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x96d0  castclass [mscorlib]System.String
0x96d5  stloc.0
0x96d6  ldloc.0
0x96d7  brfalse.s loc_96E8
0x96d9  ldarg.0
0x96da  ldloc.0
0x96db  ldarg.0
0x96dc  ldflda   string Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::_presentationHtml
0x96e1  call     instance string Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::PresentationXMLToHTML(string xml, string& html)
0x96e6  pop
0x96e7  ret
0x96e8  ldarg.0
0x96e9  ldstr    aFontFace// "<font face=\""
0x96ee  ldarg.0
0x96ef  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96f4  ldstr    aMicrosoftCrmMs// "Microsoft_Crm_Msgbody_Default_fonts"
0x96f9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96fe  ldstr    aSize2StyleDisp// "\" size=\"2\" style=\"display:inline\">"...
0x9703  call     string [mscorlib]System.String::Concat(string, string, string)
0x9708  stfld    string Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::_presentationHtml
0x970d  ret
```
