# Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::AfterLoad

- ea: `0x9710`
- end: `0x9747`
- name: `Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::AfterLoad`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9710`
- `0x9750`

## string_xrefs

- `0x9716`: `presentationxml`
- `0x972f`: `presentationxml`

## pseudocode

```c

```

## disassembly

```asm
0x9710  ldarg.0
0x9711  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x9716  ldstr    aPresentationxm// "presentationxml"
0x971b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x9720  castclass [mscorlib]System.String
0x9725  stloc.0
0x9726  ldloc.0
0x9727  brfalse.s loc_9746
0x9729  ldarg.0
0x972a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x972f  ldstr    aPresentationxm// "presentationxml"
0x9734  ldarg.0
0x9735  ldloc.0
0x9736  ldarg.0
0x9737  ldflda   string Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::_presentationHtml
0x973c  call     instance string Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::PresentationXMLToHTML(string xml, string& html)
0x9741  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9746  ret
```
