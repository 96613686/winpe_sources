# Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeTemplateHandlers

- ea: `0x7f600`
- end: `0x7f77f`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeTemplateHandlers`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x784a0`

## callees

- `0x17a10`
- `0x77cd0`
- `0x7cc50`
- `0x7f600`
- `0x7f780`
- `0x7f8c0`

## string_xrefs

- `0x7f60b`: `Templates`
- `0x7f6ec`: `EmailTemplates/emailtemplate`
- `0x7f708`: `EmailTemplates/emailtemplate`
- `0x7f6f1`: `templateid`
- `0x7f70d`: `templateid`
- `0x7f750`: `MailMergeTemplates/mailmergetemplate`
- `0x7f76c`: `MailMergeTemplates/mailmergetemplate`
- `0x7f755`: `mailmergetemplateid`
- `0x7f771`: `mailmergetemplateid`
- `0x7f61b`: `KBArticleTemplates/kbarticletemplate`
- `0x7f643`: `kbarticletemplateid`
- `0x7f669`: `ImportArticleTemplateHandler`
- `0x7f723`: `contracttemplateid`
- `0x7f73f`: `contracttemplateid`
- `0x7f71e`: `ContractTemplates/contracttemplate`
- `0x7f73a`: `ContractTemplates/contracttemplate`

## pseudocode

```c

```

## disassembly

```asm
0x7f600  ldarg.0
0x7f601  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7f606  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x7f60b  ldstr    aTemplates// "Templates"
0x7f610  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x7f615  stloc.0
0x7f616  ldloc.0
0x7f617  brtrue.s loc_7F61A
0x7f619  ret
0x7f61a  ldloc.0
0x7f61b  ldstr    aKbarticletempl// "KBArticleTemplates/kbarticletemplate"
0x7f620  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x7f625  stloc.s  4
0x7f627  ldloc.s  4
0x7f629  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x7f62e  stloc.s  5
0x7f630  br.s     loc_7F68B
0x7f632  ldloc.s  5
0x7f634  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7f639  castclass [System.Xml]System.Xml.XmlNode
0x7f63e  stloc.s  6
0x7f640  ldarg.0
0x7f641  ldloc.s  6
0x7f643  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0x7f648  call     instance string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RetrieveTemplateId(class [System.Xml]System.Xml.XmlNode node, string idNodeName)
0x7f64d  stloc.s  7
0x7f64f  ldarg.0
0x7f650  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7f655  ldloc.s  7
0x7f657  ldarg.0
0x7f658  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7f65d  ldarg.0
0x7f65e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importHelper
0x7f663  ldarg.0
0x7f664  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x7f669  ldstr    aImportarticlet// "ImportArticleTemplateHandler"
0x7f66e  ldarg.0
0x7f66f  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x7f674  ldc.i4.0
0x7f675  ldnull
0x7f676  call     class Microsoft.Crm.Tools.ImportExportPublish.ImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportExportHandlerFactory::CreateImportHandlerInstance(class [System.Xml]System.Xml.XmlDocument importDocument, string templateId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper helper, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, string typeName, [opt] class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent, [opt] bool importItem, [opt] string langFilter)
0x7f67b  stloc.s  8
0x7f67d  ldarg.0
0x7f67e  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x7f683  ldloc.s  8
0x7f685  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7f68a  pop
0x7f68b  ldloc.s  5
0x7f68d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7f692  brtrue.s loc_7F632
0x7f694  leave.s  loc_7F6B7
0x7f696  ldloc.s  5
0x7f698  isinst   [mscorlib]System.IDisposable
0x7f69d  stloc.s  9
0x7f69f  ldloc.s  9
0x7f6a1  brfalse.s loc_7F6AA
0x7f6a3  ldloc.s  9
0x7f6a5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7f6aa  endfinally
0x7f6ab  ldloc.s  4
0x7f6ad  brfalse.s loc_7F6B6
0x7f6af  ldloc.s  4
0x7f6b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7f6b6  endfinally
0x7f6b7  ldarg.0
0x7f6b8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7f6bd  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OrganizationBaseLanguage::GetOrganizationBaseLanguage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f6c2  stloc.1
0x7f6c3  ldarg.0
0x7f6c4  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x7f6c9  brtrue.s loc_7F6D2
0x7f6cb  ldsfld   string [mscorlib]System.String::Empty
0x7f6d0  br.s     loc_7F6E7
0x7f6d2  ldstr    aLanguagecode_3// "[languagecode = '"
0x7f6d7  ldloc.1
0x7f6d8  box      [mscorlib]System.Int32
0x7f6dd  ldstr    asc_A2596// "']"
0x7f6e2  call     string [mscorlib]System.String::Concat(object, object, object)
0x7f6e7  stloc.2
0x7f6e8  ldarg.0
0x7f6e9  ldloc.0
0x7f6ea  ldc.i4.s 0x24
0x7f6ec  ldstr    aEmailtemplates// "EmailTemplates/emailtemplate"
0x7f6f1  ldstr    aTemplateid// "templateid"
0x7f6f6  ldloc.2
0x7f6f7  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::AddTemplatesForLcid(class [System.Xml]System.Xml.XmlNode templatesNode, int32 templateComponentType, string templatesNodeSelector, string templateIdNode, string templateLangFilter)
0x7f6fc  stloc.3
0x7f6fd  ldarg.0
0x7f6fe  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x7f703  brfalse.s loc_7F71A
0x7f705  ldarg.0
0x7f706  ldloc.0
0x7f707  ldloc.3
0x7f708  ldstr    aEmailtemplates// "EmailTemplates/emailtemplate"
0x7f70d  ldstr    aTemplateid// "templateid"
0x7f712  ldc.i4.s 0x24
0x7f714  ldloc.1
0x7f715  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RemoveTemplatesForOtherLcids(class [System.Xml]System.Xml.XmlNode templatesnode, class [mscorlib]System.Collections.Generic.IList`1<string> excludedTemplateIds, string nodeSelector, string idNode, int32 componentType, int32 langCodeToKeep)
0x7f71a  ldarg.0
0x7f71b  ldloc.0
0x7f71c  ldc.i4.s 0x25
0x7f71e  ldstr    aContracttempla_5// "ContractTemplates/contracttemplate"
0x7f723  ldstr    aContracttempla_0// "contracttemplateid"
0x7f728  ldloc.2
0x7f729  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::AddTemplatesForLcid(class [System.Xml]System.Xml.XmlNode templatesNode, int32 templateComponentType, string templatesNodeSelector, string templateIdNode, string templateLangFilter)
0x7f72e  stloc.3
0x7f72f  ldarg.0
0x7f730  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x7f735  brfalse.s loc_7F74C
0x7f737  ldarg.0
0x7f738  ldloc.0
0x7f739  ldloc.3
0x7f73a  ldstr    aContracttempla_5// "ContractTemplates/contracttemplate"
0x7f73f  ldstr    aContracttempla_0// "contracttemplateid"
0x7f744  ldc.i4.s 0x25
0x7f746  ldloc.1
0x7f747  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RemoveTemplatesForOtherLcids(class [System.Xml]System.Xml.XmlNode templatesnode, class [mscorlib]System.Collections.Generic.IList`1<string> excludedTemplateIds, string nodeSelector, string idNode, int32 componentType, int32 langCodeToKeep)
0x7f74c  ldarg.0
0x7f74d  ldloc.0
0x7f74e  ldc.i4.s 0x27
0x7f750  ldstr    aMailmergetempl// "MailMergeTemplates/mailmergetemplate"
0x7f755  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x7f75a  ldloc.2
0x7f75b  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::AddTemplatesForLcid(class [System.Xml]System.Xml.XmlNode templatesNode, int32 templateComponentType, string templatesNodeSelector, string templateIdNode, string templateLangFilter)
0x7f760  stloc.3
0x7f761  ldarg.0
0x7f762  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x7f767  brfalse.s loc_7F77E
0x7f769  ldarg.0
0x7f76a  ldloc.0
0x7f76b  ldloc.3
0x7f76c  ldstr    aMailmergetempl// "MailMergeTemplates/mailmergetemplate"
0x7f771  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x7f776  ldc.i4.s 0x27
0x7f778  ldloc.1
0x7f779  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RemoveTemplatesForOtherLcids(class [System.Xml]System.Xml.XmlNode templatesnode, class [mscorlib]System.Collections.Generic.IList`1<string> excludedTemplateIds, string nodeSelector, string idNode, int32 componentType, int32 langCodeToKeep)
0x7f77e  ret
```
