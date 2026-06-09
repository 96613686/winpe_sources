# Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessTemplates

- ea: `0x9840`
- end: `0x9a87`
- name: `Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessTemplates`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xdd40`

## callees

- `0x9840`
- `0xa300`
- `0xd370`
- `0xd460`
- `0x17a10`
- `0x17b50`
- `0x51160`
- `0x533f0`
- `0x53460`
- `0x63d80`

## string_xrefs

- `0x98ae`: `ImportExportXml`
- `0x984d`: `ProcessTemplates for {0}`
- `0x986c`: `ImportExportXml/Templates/EmailTemplates/emailtemplate/templateid`
- `0x9879`: `ImportExportXml/Templates/MailMergeTemplates/mailmergetemplate/mailmergetemplateid`
- `0x9886`: `ImportExportXml/Templates/KBArticleTemplates/kbarticletemplate/kbarticletemplateid`
- `0x9891`: `ImportExportXml/Templates`
- `0x98e9`: `EmailTemplates/emailtemplate`
- `0x9915`: `Emailtemplate`
- `0x991a`: `templateid`
- `0x992d`: `templateid`
- `0x9971`: `MailMergeTemplates/mailmergetemplate`
- `0x999d`: `Mailmergetemplate`
- `0x99a2`: `mailmergetemplateid`
- `0x99b5`: `mailmergetemplateid`
- `0x99fc`: `KBArticleTemplates/kbarticletemplate`
- `0x9a28`: `KBArticleTemplates`
- `0x9a2d`: `kbarticletemplateid`
- `0x9a40`: `kbarticletemplateid`
- `0x9a58`: `ImportArticleTemplateHandler`

## pseudocode

```c

```

## disassembly

```asm
0x9840  ldarg.0
0x9841  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x9846  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x984b  ldc.i4.s 0x18
0x984d  ldstr    aProcesstemplat// "ProcessTemplates for {0}"
0x9852  ldc.i4.1
0x9853  newarr   [mscorlib]System.Object
0x9858  dup
0x9859  ldc.i4.0
0x985a  ldarg.2
0x985b  box      [mscorlib]System.Int32
0x9860  stelem.ref
0x9861  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9866  ldarg.3
0x9867  brfalse.s loc_9890
0x9869  ldarg.0
0x986a  ldarg.1
0x986b  ldarg.2
0x986c  ldstr    aImportexportxm_18// "ImportExportXml/Templates/EmailTemplate"...
0x9871  call     instance void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ModifyTemplateIds(class [System.Xml]System.Xml.XmlDocument dom, int32 language, string path)
0x9876  ldarg.0
0x9877  ldarg.1
0x9878  ldarg.2
0x9879  ldstr    aImportexportxm_19// "ImportExportXml/Templates/MailMergeTemp"...
0x987e  call     instance void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ModifyTemplateIds(class [System.Xml]System.Xml.XmlDocument dom, int32 language, string path)
0x9883  ldarg.0
0x9884  ldarg.1
0x9885  ldarg.2
0x9886  ldstr    aImportexportxm_20// "ImportExportXml/Templates/KBArticleTemp"...
0x988b  call     instance void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ModifyTemplateIds(class [System.Xml]System.Xml.XmlDocument dom, int32 language, string path)
0x9890  ldarg.1
0x9891  ldstr    aImportexportxm_21// "ImportExportXml/Templates"
0x9896  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x989b  stloc.0
0x989c  ldloc.0
0x989d  brtrue.s loc_98A0
0x989f  ret
0x98a0  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::.ctor()
0x98a5  stloc.1
0x98a6  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument()
0x98ab  stloc.2
0x98ac  ldloc.2
0x98ad  ldc.i4.1
0x98ae  ldstr    aImportexportxm// "ImportExportXml"
0x98b3  ldsfld   string [mscorlib]System.String::Empty
0x98b8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x98bd  stloc.3
0x98be  ldloc.2
0x98bf  ldloc.3
0x98c0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x98c5  pop
0x98c6  ldloc.3
0x98c7  ldloc.0
0x98c8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x98cd  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x98d2  ldarg.3
0x98d3  ldarg.2
0x98d4  call     string Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::GetLangFilter(bool isSystemSolution, int32 languageCode)
0x98d9  stloc.s  4
0x98db  ldarg.0
0x98dc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x98e1  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x98e6  stloc.s  5
0x98e8  ldloc.0
0x98e9  ldstr    aEmailtemplates// "EmailTemplates/emailtemplate"
0x98ee  ldloc.s  4
0x98f0  call     string [mscorlib]System.String::Concat(string, string)
0x98f5  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x98fa  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x98ff  stloc.s  6
0x9901  br.s     loc_9950
0x9903  ldloc.s  6
0x9905  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x990a  castclass [System.Xml]System.Xml.XmlNode
0x990f  stloc.s  7
0x9911  ldloc.s  7
0x9913  ldarg.2
0x9914  ldarg.3
0x9915  ldstr    aEmailtemplate// "Emailtemplate"
0x991a  ldstr    aTemplateid// "templateid"
0x991f  ldarg.0
0x9920  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x9925  call     void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::LogTemplateTelemetryTrace(class [System.Xml]System.Xml.XmlNode templateNode, int32 languageCode, bool isSystemSolution, string templateType, string templateIdName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x992a  ldloc.2
0x992b  ldloc.s  7
0x992d  ldstr    aTemplateid// "templateid"
0x9932  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x9937  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x993c  ldarg.0
0x993d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x9942  ldloc.s  5
0x9944  ldloc.1
0x9945  ldnull
0x9946  ldnull
0x9947  ldc.i4.1
0x9948  ldloc.s  4
0x994a  call     class Microsoft.Crm.Tools.ImportExportPublish.ImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportExportHandlerFactory::CreateImportEmailTemplateHandlerInstance(class [System.Xml]System.Xml.XmlDocument importDocument, string templateId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper helper, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet filesToImport, [opt] class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent, [opt] bool importItem, [opt] string langFilter)
0x994f  pop
0x9950  ldloc.s  6
0x9952  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9957  brtrue.s loc_9903
0x9959  leave.s  loc_9970
0x995b  ldloc.s  6
0x995d  isinst   [mscorlib]System.IDisposable
0x9962  stloc.s  8
0x9964  ldloc.s  8
0x9966  brfalse.s loc_996F
0x9968  ldloc.s  8
0x996a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x996f  endfinally
0x9970  ldloc.0
0x9971  ldstr    aMailmergetempl// "MailMergeTemplates/mailmergetemplate"
0x9976  ldloc.s  4
0x9978  call     string [mscorlib]System.String::Concat(string, string)
0x997d  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x9982  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x9987  stloc.s  6
0x9989  br.s     loc_99DB
0x998b  ldloc.s  6
0x998d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9992  castclass [System.Xml]System.Xml.XmlNode
0x9997  stloc.s  9
0x9999  ldloc.s  9
0x999b  ldarg.2
0x999c  ldarg.3
0x999d  ldstr    aMailmergetempl_0// "Mailmergetemplate"
0x99a2  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x99a7  ldarg.0
0x99a8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x99ad  call     void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::LogTemplateTelemetryTrace(class [System.Xml]System.Xml.XmlNode templateNode, int32 languageCode, bool isSystemSolution, string templateType, string templateIdName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x99b2  ldloc.2
0x99b3  ldloc.s  9
0x99b5  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x99ba  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x99bf  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x99c4  ldarg.0
0x99c5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x99ca  ldloc.s  5
0x99cc  ldloc.1
0x99cd  ldnull
0x99ce  ldloc.s  4
0x99d0  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::.ctor(class [System.Xml]System.Xml.XmlDocument importDocument, string templateId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper helper, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, [opt] class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent, [opt] string langFilter)
0x99d5  ldc.i4.1
0x99d6  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::ImportItem(bool setup)
0x99db  ldloc.s  6
0x99dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x99e2  brtrue.s loc_998B
0x99e4  leave.s  loc_99FB
0x99e6  ldloc.s  6
0x99e8  isinst   [mscorlib]System.IDisposable
0x99ed  stloc.s  8
0x99ef  ldloc.s  8
0x99f1  brfalse.s loc_99FA
0x99f3  ldloc.s  8
0x99f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x99fa  endfinally
0x99fb  ldloc.0
0x99fc  ldstr    aKbarticletempl// "KBArticleTemplates/kbarticletemplate"
0x9a01  ldloc.s  4
0x9a03  call     string [mscorlib]System.String::Concat(string, string)
0x9a08  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x9a0d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x9a12  stloc.s  6
0x9a14  br.s     loc_9A66
0x9a16  ldloc.s  6
0x9a18  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9a1d  castclass [System.Xml]System.Xml.XmlNode
0x9a22  stloc.s  0xA
0x9a24  ldloc.s  0xA
0x9a26  ldarg.2
0x9a27  ldarg.3
0x9a28  ldstr    aKbarticletempl_0// "KBArticleTemplates"
0x9a2d  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0x9a32  ldarg.0
0x9a33  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x9a38  call     void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::LogTemplateTelemetryTrace(class [System.Xml]System.Xml.XmlNode templateNode, int32 languageCode, bool isSystemSolution, string templateType, string templateIdName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9a3d  ldloc.2
0x9a3e  ldloc.s  0xA
0x9a40  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0x9a45  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x9a4a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x9a4f  ldarg.0
0x9a50  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x9a55  ldloc.s  5
0x9a57  ldloc.1
0x9a58  ldstr    aImportarticlet// "ImportArticleTemplateHandler"
0x9a5d  ldnull
0x9a5e  ldc.i4.1
0x9a5f  ldnull
0x9a60  call     class Microsoft.Crm.Tools.ImportExportPublish.ImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportExportHandlerFactory::CreateImportHandlerInstance(class [System.Xml]System.Xml.XmlDocument importDocument, string templateId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper helper, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, string typeName, [opt] class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent, [opt] bool importItem, [opt] string langFilter)
0x9a65  pop
0x9a66  ldloc.s  6
0x9a68  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9a6d  brtrue.s loc_9A16
0x9a6f  leave.s  loc_9A86
0x9a71  ldloc.s  6
0x9a73  isinst   [mscorlib]System.IDisposable
0x9a78  stloc.s  8
0x9a7a  ldloc.s  8
0x9a7c  brfalse.s loc_9A85
0x9a7e  ldloc.s  8
0x9a80  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9a85  endfinally
0x9a86  ret
```
