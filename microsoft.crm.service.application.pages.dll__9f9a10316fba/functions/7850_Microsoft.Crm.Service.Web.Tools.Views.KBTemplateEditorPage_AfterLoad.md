# Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::AfterLoad

- ea: `0x7850`
- end: `0x78a3`
- name: `Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::AfterLoad`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7850`

## string_xrefs

- `0x787d`: `kbTemplateEditorDefaultXmlFormat.xsl`
- `0x7856`: `structurexml`

## pseudocode

```c

```

## disassembly

```asm
0x7850  ldarg.2
0x7851  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x7856  ldstr    aStructurexml// "structurexml"
0x785b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x7860  isinst   [mscorlib]System.String
0x7865  stloc.0
0x7866  ldarg.0
0x7867  ldloc.0
0x7868  brfalse.s loc_786D
0x786a  ldloc.0
0x786b  br.s     loc_7872
0x786d  ldsfld   string [mscorlib]System.String::Empty
0x7872  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x7877  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_structureXmlDoc
0x787c  ldarg.0
0x787d  ldstr    aKbtemplateedit_0// "kbTemplateEditorDefaultXmlFormat.xsl"
0x7882  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::LoadXmlDocumentFromFileId(string)
0x7887  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_formatXmlDoc
0x788c  ldarg.0
0x788d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_powerAppsNavBar
0x7892  ldarg.2
0x7893  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x7898  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Title()
0x789d  stfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar::ComponentName
0x78a2  ret
```
