# Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::New

- ea: `0x7820`
- end: `0x784c`
- name: `Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::New`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x7827`: `/Tools/KBTemplateEditor/DefaultXML/structure.xml`
- `0x783c`: `kbTemplateEditorDefaultXmlFormat.xsl`

## pseudocode

```c

```

## disassembly

```asm
0x7820  ldarg.0
0x7821  ldarg.0
0x7822  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x7827  ldstr    aToolsKbtemplat_1// "/Tools/KBTemplateEditor/DefaultXML/stru"...
0x782c  callvirt instance string [System.Web]System.Web.UI.Page::MapPath(string)
0x7831  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::LoadXmlDocumentFromFile(string)
0x7836  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_structureXmlDoc
0x783b  ldarg.0
0x783c  ldstr    aKbtemplateedit_0// "kbTemplateEditorDefaultXmlFormat.xsl"
0x7841  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::LoadXmlDocumentFromFileId(string)
0x7846  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_formatXmlDoc
0x784b  ret
```
