# Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::AfterLoad

- ea: `0xa2c0`
- end: `0xa323`
- name: `Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::AfterLoad`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa2c0`
- `0xa4f0`

## string_xrefs

- `0xa2c6`: `presentationxml`
- `0xa2ec`: `subjectpresentationxml`

## pseudocode

```c

```

## disassembly

```asm
0xa2c0  ldarg.0
0xa2c1  ldfld    class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Template Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_template
0xa2c6  ldstr    aPresentationxm// "presentationxml"
0xa2cb  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xa2d0  castclass [mscorlib]System.String
0xa2d5  stloc.0
0xa2d6  ldloc.0
0xa2d7  brfalse.s loc_A2E6
0xa2d9  ldarg.0
0xa2da  ldloc.0
0xa2db  ldarg.0
0xa2dc  ldflda   string Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_presentationHtml
0xa2e1  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::PresentationXMLToHTML(string xml, string& html)
0xa2e6  ldarg.0
0xa2e7  ldfld    class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Template Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_template
0xa2ec  ldstr    aSubjectpresent// "subjectpresentationxml"
0xa2f1  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xa2f6  castclass [mscorlib]System.String
0xa2fb  stloc.0
0xa2fc  ldloc.0
0xa2fd  brfalse.s loc_A30C
0xa2ff  ldarg.0
0xa300  ldloc.0
0xa301  ldarg.0
0xa302  ldflda   string Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_subjectHtml
0xa307  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::PresentationXMLToHTML(string xml, string& html)
0xa30c  ldarg.0
0xa30d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_powerAppsNavBar
0xa312  ldarg.2
0xa313  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0xa318  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Title()
0xa31d  stfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar::ComponentName
0xa322  ret
```
