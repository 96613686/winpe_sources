# Microsoft.Crm.Tools.ImportExportPublish.TransformXml::TransformTemplateNodes

- ea: `0x497e0`
- end: `0x49832`
- name: `Microsoft.Crm.Tools.ImportExportPublish.TransformXml::TransformTemplateNodes`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x4a1b0`

## callees

- `0x49510`

## string_xrefs

- `0x497e1`: `Templates`
- `0x49822`: `KBArticleTemplates`
- `0x49810`: `contracttemplate`
- `0x497ef`: `dmUpdateEmailTemplate`
- `0x497f4`: `EmailTemplates`
- `0x497f9`: `emailtemplate`
- `0x49806`: `dmUpdateContractTemplate`
- `0x4980b`: `ContractTemplates`
- `0x4981d`: `dmUpdateKbArticleTemplate`
- `0x49827`: `kbarticletemplate`

## pseudocode

```c

```

## disassembly

```asm
0x497e0  ldarg.2
0x497e1  ldstr    aTemplates// "Templates"
0x497e6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x497eb  pop
0x497ec  ldarg.0
0x497ed  ldarg.1
0x497ee  ldarg.2
0x497ef  ldstr    aDmupdateemailt// "dmUpdateEmailTemplate"
0x497f4  ldstr    aEmailtemplates_0// "EmailTemplates"
0x497f9  ldstr    aEmailtemplate_1// "emailtemplate"
0x497fe  call     instance void Microsoft.Crm.Tools.ImportExportPublish.TransformXml::TransformTemplateNode(class [System.Xml]System.Xml.XmlDocument oldDoc, class [System.Xml]System.Xml.XmlDocument newDoc, string oldTemplateName, string newTemplateName, string newNodeName)
0x49803  ldarg.0
0x49804  ldarg.1
0x49805  ldarg.2
0x49806  ldstr    aDmupdatecontra// "dmUpdateContractTemplate"
0x4980b  ldstr    aContracttempla_4// "ContractTemplates"
0x49810  ldstr    aContracttempla_3// "contracttemplate"
0x49815  call     instance void Microsoft.Crm.Tools.ImportExportPublish.TransformXml::TransformTemplateNode(class [System.Xml]System.Xml.XmlDocument oldDoc, class [System.Xml]System.Xml.XmlDocument newDoc, string oldTemplateName, string newTemplateName, string newNodeName)
0x4981a  ldarg.0
0x4981b  ldarg.1
0x4981c  ldarg.2
0x4981d  ldstr    aDmupdatekbarti// "dmUpdateKbArticleTemplate"
0x49822  ldstr    aKbarticletempl_0// "KBArticleTemplates"
0x49827  ldstr    aKbarticletempl_5// "kbarticletemplate"
0x4982c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.TransformXml::TransformTemplateNode(class [System.Xml]System.Xml.XmlDocument oldDoc, class [System.Xml]System.Xml.XmlDocument newDoc, string oldTemplateName, string newTemplateName, string newNodeName)
0x49831  ret
```
