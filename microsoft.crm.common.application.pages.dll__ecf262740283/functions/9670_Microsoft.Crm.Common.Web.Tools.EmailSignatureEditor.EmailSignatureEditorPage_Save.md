# Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::Save

- ea: `0x9670`
- end: `0x96ba`
- name: `Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::Save`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9670`
- `0x97a0`

## string_xrefs

- `0x9682`: `crmFormSubmitXML`
- `0x96a4`: `presentationxml`

## pseudocode

```c

```

## disassembly

```asm
0x9670  ldarg.0
0x9671  ldarg.0
0x9672  ldarg.0
0x9673  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9678  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x967d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9682  ldstr    aCrmformsubmitx// "crmFormSubmitXML"
0x9687  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x968c  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::GetPresenationXml(string xml)
0x9691  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::presentationDoc
0x9696  ldarg.0
0x9697  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::presentationDoc
0x969c  brfalse.s loc_96B9
0x969e  ldarg.2
0x969f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x96a4  ldstr    aPresentationxm// "presentationxml"
0x96a9  ldarg.0
0x96aa  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::presentationDoc
0x96af  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x96b4  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x96b9  ret
```
