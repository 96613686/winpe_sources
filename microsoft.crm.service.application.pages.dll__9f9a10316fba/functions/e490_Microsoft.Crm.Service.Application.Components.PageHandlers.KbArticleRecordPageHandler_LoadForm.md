# Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::LoadForm

- ea: `0xe490`
- end: `0xe798`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::LoadForm`
- size: `776`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xe130`
- `0xe490`

## string_xrefs

- `0xe516`: `kbarticletemplate`
- `0xe755`: `kbarticletemplate`
- `0xe564`: `structurexml`
- `0xe783`: `structurexml`
- `0xe50b`: `kbarticletemplateid`
- `0xe749`: `kbarticletemplateid`
- `0xe54d`: `Invalid Article Template Id`

## pseudocode

```c

```

## disassembly

```asm
0xe490  ldarg.0
0xe491  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe496  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0xe49b  ldstr    aStatecode// "statecode"
0xe4a0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xe4a5  isinst   [mscorlib]System.String
0xe4aa  stloc.0
0xe4ab  ldloc.0
0xe4ac  brfalse  loc_E797
0xe4b1  ldtoken  [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.KbArticleState
0xe4b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe4bb  ldloc.0
0xe4bc  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0xe4c1  unbox.any [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.KbArticleState
0xe4c6  stloc.1
0xe4c7  ldc.i4.3
0xe4c8  ldloc.1
0xe4c9  beq      loc_E72E
0xe4ce  ldsfld   string [mscorlib]System.String::Empty
0xe4d3  stloc.2
0xe4d4  ldarg.0
0xe4d5  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe4da  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0xe4df  ldc.i4.1
0xe4e0  bne.un.s loc_E505
0xe4e2  ldarg.0
0xe4e3  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0xe4e8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe4ed  ldstr    aTmplid// "_tmplid"
0xe4f2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe4f7  stloc.2
0xe4f8  ldarg.0
0xe4f9  ldstr    aArticledataArt// "<articledata></articledata>"
0xe4fe  stfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_articleXml
0xe503  br.s     loc_E516
0xe505  ldarg.0
0xe506  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe50b  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0xe510  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::GetDataValue(string)
0xe515  stloc.2
0xe516  ldstr    aKbarticletempl// "kbarticletemplate"
0xe51b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe520  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe525  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xe52a  stloc.3
0xe52b  ldloc.3
0xe52c  ldloc.2
0xe52d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xe532  ldloc.2
0xe533  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe538  brtrue.s loc_E54C
0xe53a  ldloc.2
0xe53b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xe540  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe545  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe54a  br.s     loc_E54D
0xe54c  ldc.i4.0
0xe54d  ldstr    aInvalidArticle// "Invalid Article Template Id"
0xe552  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xe557  ldloc.3
0xe558  ldsfld   string [mscorlib]System.String::Empty
0xe55d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0xe562  ldarg.0
0xe563  ldloc.3
0xe564  ldstr    aStructurexml// "structurexml"
0xe569  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xe56e  castclass [mscorlib]System.String
0xe573  stfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_templateXml
0xe578  ldarg.0
0xe579  ldfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_templateXml
0xe57e  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xe583  ldstr    aKbarticleSecti// "kbarticle/sections/section[@type='edit'"...
0xe588  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xe58d  stloc.s  4
0xe58f  ldarg.0
0xe590  call     instance string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::get_ArticleXml()
0xe595  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xe59a  stloc.s  5
0xe59c  ldloc.s  5
0xe59e  ldstr    aArticledataSec// "articledata/section"
0xe5a3  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xe5a8  stloc.s  6
0xe5aa  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xe5af  stloc.s  7
0xe5b1  ldsfld   string [mscorlib]System.String::Empty
0xe5b6  stloc.s  8
0xe5b8  ldnull
0xe5b9  stloc.s  9
0xe5bb  ldc.i4.0
0xe5bc  stloc.s  0xA
0xe5be  br       loc_E68D
0xe5c3  ldloc.s  4
0xe5c5  ldloc.s  0xA
0xe5c7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xe5cc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xe5d1  ldstr    aId// "id"
0xe5d6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0xe5db  castclass [System.Xml]System.Xml.XmlAttribute
0xe5e0  stloc.s  9
0xe5e2  ldloc.s  9
0xe5e4  brfalse  loc_E687
0xe5e9  ldloc.s  9
0xe5eb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xe5f0  stloc.s  8
0xe5f2  ldloc.s  7
0xe5f4  ldloc.s  8
0xe5f6  ldnull
0xe5f7  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xe5fc  ldloc.s  5
0xe5fe  ldstr    aArticledataSec_0// "articledata/section[@id='"
0xe603  ldloc.s  8
0xe605  ldstr    asc_2292C// "']"
0xe60a  call     string [mscorlib]System.String::Concat(string, string, string)
0xe60f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xe614  stloc.s  0xB
0xe616  ldloc.s  0xB
0xe618  brtrue.s loc_E687
0xe61a  ldloc.s  5
0xe61c  ldc.i4.1
0xe61d  ldstr    aSection// "section"
0xe622  ldsfld   string [mscorlib]System.String::Empty
0xe627  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0xe62c  stloc.s  0xB
0xe62e  ldloc.s  5
0xe630  ldstr    aId// "id"
0xe635  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xe63a  stloc.s  0xC
0xe63c  ldloc.s  0xC
0xe63e  ldloc.s  8
0xe640  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xe645  ldloc.s  0xB
0xe647  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xe64c  ldloc.s  0xC
0xe64e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xe653  pop
0xe654  ldloc.s  5
0xe656  ldstr    aContent// "content"
0xe65b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0xe660  stloc.s  0xD
0xe662  ldloc.s  0xD
0xe664  ldstr    aCdata// "<![CDATA[]]>"
0xe669  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xe66e  ldloc.s  0xB
0xe670  ldloc.s  0xD
0xe672  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xe677  pop
0xe678  ldloc.s  5
0xe67a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xe67f  ldloc.s  0xB
0xe681  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xe686  pop
0xe687  ldloc.s  0xA
0xe689  ldc.i4.1
0xe68a  add
0xe68b  stloc.s  0xA
0xe68d  ldloc.s  0xA
0xe68f  ldloc.s  4
0xe691  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xe696  blt      loc_E5C3
0xe69b  ldc.i4.0
0xe69c  stloc.s  0xE
0xe69e  br.s     loc_E6FA
0xe6a0  ldloc.s  6
0xe6a2  ldloc.s  0xE
0xe6a4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xe6a9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xe6ae  ldstr    aId// "id"
0xe6b3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0xe6b8  castclass [System.Xml]System.Xml.XmlAttribute
0xe6bd  stloc.s  9
0xe6bf  ldloc.s  9
0xe6c1  brfalse.s loc_E6F4
0xe6c3  ldloc.s  9
0xe6c5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xe6ca  stloc.s  8
0xe6cc  ldloc.s  7
0xe6ce  ldloc.s  8
0xe6d0  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0xe6d5  brtrue.s loc_E6F4
0xe6d7  ldloc.s  6
0xe6d9  ldloc.s  0xE
0xe6db  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xe6e0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0xe6e5  ldloc.s  6
0xe6e7  ldloc.s  0xE
0xe6e9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xe6ee  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0xe6f3  pop
0xe6f4  ldloc.s  0xE
0xe6f6  ldc.i4.1
0xe6f7  add
0xe6f8  stloc.s  0xE
0xe6fa  ldloc.s  0xE
0xe6fc  ldloc.s  6
0xe6fe  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xe703  blt.s    loc_E6A0
0xe705  leave.s  loc_E713
0xe707  ldloc.s  6
0xe709  brfalse.s loc_E712
0xe70b  ldloc.s  6
0xe70d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe712  endfinally
0xe713  ldarg.0
0xe714  ldloc.s  5
0xe716  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xe71b  stfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_articleXml
0xe720  leave.s  loc_E797
0xe722  ldloc.s  4
0xe724  brfalse.s loc_E72D
0xe726  ldloc.s  4
0xe728  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe72d  endfinally
0xe72e  ldsfld   string [mscorlib]System.String::Empty
0xe733  stloc.s  0xF
0xe735  ldarg.0
0xe736  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe73b  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0xe740  ldc.i4.1
0xe741  beq.s    loc_E797
0xe743  ldarg.0
0xe744  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe749  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0xe74e  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::GetDataValue(string)
0xe753  stloc.s  0xF
0xe755  ldstr    aKbarticletempl// "kbarticletemplate"
0xe75a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe75f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe764  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xe769  stloc.s  0x10
0xe76b  ldloc.s  0x10
0xe76d  ldloc.s  0xF
0xe76f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xe774  ldloc.s  0x10
0xe776  ldsfld   string [mscorlib]System.String::Empty
0xe77b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0xe780  ldarg.0
0xe781  ldloc.s  0x10
0xe783  ldstr    aStructurexml// "structurexml"
0xe788  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xe78d  castclass [mscorlib]System.String
0xe792  stfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_templateXml
0xe797  ret
```
