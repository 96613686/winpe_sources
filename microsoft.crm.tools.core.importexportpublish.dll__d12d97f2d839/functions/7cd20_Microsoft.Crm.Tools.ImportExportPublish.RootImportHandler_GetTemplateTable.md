# Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetTemplateTable

- ea: `0x7cd20`
- end: `0x7cf09`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetTemplateTable`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x66e00`

## callees

- `0x7cc50`
- `0x7cc90`
- `0x7cd20`

## string_xrefs

- `0x7cdca`: `templateid`
- `0x7cebc`: `mailmergetemplateid`
- `0x7cd52`: `kbarticletemplateid`
- `0x7ce43`: `contracttemplateid`
- `0x7cd31`: `Templates/KBArticleTemplates/kbarticletemplate`
- `0x7cda7`: `Templates/EmailTemplates/emailtemplate`
- `0x7ce20`: `Templates/ContractTemplates/contracttemplate`
- `0x7ce99`: `Templates/MailMergeTemplates/mailmergetemplate`

## pseudocode

```c

```

## disassembly

```asm
0x7cd20  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription>>::.ctor()
0x7cd25  stloc.0
0x7cd26  ldarg.0
0x7cd27  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7cd2c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x7cd31  ldstr    aTemplatesKbart// "Templates/KBArticleTemplates/kbarticlet"...
0x7cd36  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x7cd3b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x7cd40  stloc.1
0x7cd41  br.s     loc_7CD81
0x7cd43  ldloc.1
0x7cd44  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7cd49  castclass [System.Xml]System.Xml.XmlNode
0x7cd4e  stloc.2
0x7cd4f  ldloc.0
0x7cd50  ldarg.0
0x7cd51  ldloc.2
0x7cd52  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0x7cd57  call     instance string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RetrieveTemplateId(class [System.Xml]System.Xml.XmlNode node, string idNodeName)
0x7cd5c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7cd61  ldarg.0
0x7cd62  ldloc.2
0x7cd63  ldstr    aTitle// "title"
0x7cd68  ldstr    aDescription// "description"
0x7cd6d  ldc.i4   0x3F8
0x7cd72  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetTemplateDescription(class [System.Xml]System.Xml.XmlNode node, string nameNodeName, string descriptionNodeName, int32 type)
0x7cd77  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription>::.ctor(var<u1>, !!T0)
0x7cd7c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription>>::Add(var<u1>)
0x7cd81  ldloc.1
0x7cd82  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7cd87  brtrue.s loc_7CD43
0x7cd89  leave.s  loc_7CD9C
0x7cd8b  ldloc.1
0x7cd8c  isinst   [mscorlib]System.IDisposable
0x7cd91  stloc.3
0x7cd92  ldloc.3
0x7cd93  brfalse.s loc_7CD9B
0x7cd95  ldloc.3
0x7cd96  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7cd9b  endfinally
0x7cd9c  ldarg.0
0x7cd9d  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7cda2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x7cda7  ldstr    aTemplatesEmail// "Templates/EmailTemplates/emailtemplate"
0x7cdac  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x7cdb1  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x7cdb6  stloc.1
0x7cdb7  br.s     loc_7CDFA
0x7cdb9  ldloc.1
0x7cdba  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7cdbf  castclass [System.Xml]System.Xml.XmlNode
0x7cdc4  stloc.s  4
0x7cdc6  ldloc.0
0x7cdc7  ldarg.0
0x7cdc8  ldloc.s  4
0x7cdca  ldstr    aTemplateid// "templateid"
0x7cdcf  call     instance string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RetrieveTemplateId(class [System.Xml]System.Xml.XmlNode node, string idNodeName)
0x7cdd4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7cdd9  ldarg.0
0x7cdda  ldloc.s  4
0x7cddc  ldstr    aTitle// "title"
0x7cde1  ldstr    aDescription// "description"
0x7cde6  ldc.i4   0x7DA
0x7cdeb  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetTemplateDescription(class [System.Xml]System.Xml.XmlNode node, string nameNodeName, string descriptionNodeName, int32 type)
0x7cdf0  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription>::.ctor(var<u1>, !!T0)
0x7cdf5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription>>::Add(var<u1>)
0x7cdfa  ldloc.1
0x7cdfb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7ce00  brtrue.s loc_7CDB9
0x7ce02  leave.s  loc_7CE15
0x7ce04  ldloc.1
0x7ce05  isinst   [mscorlib]System.IDisposable
0x7ce0a  stloc.3
0x7ce0b  ldloc.3
0x7ce0c  brfalse.s loc_7CE14
0x7ce0e  ldloc.3
0x7ce0f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7ce14  endfinally
0x7ce15  ldarg.0
0x7ce16  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7ce1b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x7ce20  ldstr    aTemplatesContr// "Templates/ContractTemplates/contracttem"...
0x7ce25  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x7ce2a  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x7ce2f  stloc.1
0x7ce30  br.s     loc_7CE73
0x7ce32  ldloc.1
0x7ce33  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7ce38  castclass [System.Xml]System.Xml.XmlNode
0x7ce3d  stloc.s  5
0x7ce3f  ldloc.0
0x7ce40  ldarg.0
0x7ce41  ldloc.s  5
0x7ce43  ldstr    aContracttempla_0// "contracttemplateid"
0x7ce48  call     instance string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RetrieveTemplateId(class [System.Xml]System.Xml.XmlNode node, string idNodeName)
0x7ce4d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7ce52  ldarg.0
0x7ce53  ldloc.s  5
0x7ce55  ldstr    aName// "name"
0x7ce5a  ldstr    aDescription// "description"
0x7ce5f  ldc.i4   0x7DB
0x7ce64  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetTemplateDescription(class [System.Xml]System.Xml.XmlNode node, string nameNodeName, string descriptionNodeName, int32 type)
0x7ce69  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription>::.ctor(var<u1>, !!T0)
0x7ce6e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription>>::Add(var<u1>)
0x7ce73  ldloc.1
0x7ce74  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7ce79  brtrue.s loc_7CE32
0x7ce7b  leave.s  loc_7CE8E
0x7ce7d  ldloc.1
0x7ce7e  isinst   [mscorlib]System.IDisposable
0x7ce83  stloc.3
0x7ce84  ldloc.3
0x7ce85  brfalse.s loc_7CE8D
0x7ce87  ldloc.3
0x7ce88  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7ce8d  endfinally
0x7ce8e  ldarg.0
0x7ce8f  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7ce94  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x7ce99  ldstr    aTemplatesMailm// "Templates/MailMergeTemplates/mailmerget"...
0x7ce9e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x7cea3  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x7cea8  stloc.1
0x7cea9  br.s     loc_7CEEC
0x7ceab  ldloc.1
0x7ceac  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7ceb1  castclass [System.Xml]System.Xml.XmlNode
0x7ceb6  stloc.s  6
0x7ceb8  ldloc.0
0x7ceb9  ldarg.0
0x7ceba  ldloc.s  6
0x7cebc  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x7cec1  call     instance string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RetrieveTemplateId(class [System.Xml]System.Xml.XmlNode node, string idNodeName)
0x7cec6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7cecb  ldarg.0
0x7cecc  ldloc.s  6
0x7cece  ldstr    aName// "name"
0x7ced3  ldstr    aDescription// "description"
0x7ced8  ldc.i4   0x2392
0x7cedd  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetTemplateDescription(class [System.Xml]System.Xml.XmlNode node, string nameNodeName, string descriptionNodeName, int32 type)
0x7cee2  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription>::.ctor(var<u1>, !!T0)
0x7cee7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateDescription>>::Add(var<u1>)
0x7ceec  ldloc.1
0x7ceed  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7cef2  brtrue.s loc_7CEAB
0x7cef4  leave.s  loc_7CF07
0x7cef6  ldloc.1
0x7cef7  isinst   [mscorlib]System.IDisposable
0x7cefc  stloc.3
0x7cefd  ldloc.3
0x7cefe  brfalse.s loc_7CF06
0x7cf00  ldloc.3
0x7cf01  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7cf06  endfinally
0x7cf07  ldloc.0
0x7cf08  ret
```
