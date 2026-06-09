# Microsoft.Crm.ObjectModel.SPCommands.CreateSubSiteUrl::execute

- ea: `0x204fc0`
- end: `0x2053c4`
- name: `Microsoft.Crm.ObjectModel.SPCommands.CreateSubSiteUrl::execute`
- size: `1028`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6d6e0`
- `0x6d810`
- `0x88510`
- `0x88530`
- `0x17c910`
- `0x188400`
- `0x204fc0`

## string_xrefs

- `0x2051de`: `template`
- `0x2051ea`: `template`
- `0x205204`: `template`
- `0x204fd6`: `sharePointUrlsXml`
- `0x205016`: `CreateSubSiteUrl`
- `0x20517a`: `CreateSubSiteUrl`
- `0x2053a7`: `CreateSubSiteUrl`

## pseudocode

```c

```

## disassembly

```asm
0x204fc0  ldarg.0
0x204fc1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.CreateSubSiteUrl::context
0x204fc6  ldstr    aContext// "context"
0x204fcb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x204fd0  ldarg.0
0x204fd1  ldfld    string Microsoft.Crm.ObjectModel.SPCommands.CreateSubSiteUrl::sharePointUrlsXml
0x204fd6  ldstr    aSharepointurls// "sharePointUrlsXml"
0x204fdb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x204fe0  ldc.i4.0
0x204fe1  stloc.0
0x204fe2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::.ctor()
0x204fe7  stloc.1
0x204fe8  ldarg.0
0x204fe9  ldfld    string Microsoft.Crm.ObjectModel.SPCommands.CreateSubSiteUrl::sharePointUrlsXml
0x204fee  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x204ff3  stloc.2
0x204ff4  ldloc.2
0x204ff5  ldstr    aSiteurl_2// "//siteUrl"
0x204ffa  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x204fff  stloc.3
0x205000  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x205005  stloc.s  4
0x205007  ldloc.3
0x205008  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x20500d  ldc.i4.1
0x20500e  bge.s    loc_205037
0x205010  ldarg.0
0x205011  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.CreateSubSiteUrl::context
0x205016  ldstr    aCreatesubsiteu// "CreateSubSiteUrl"
0x20501b  ldc.i4.0
0x20501c  ldstr    aSiteurlNodesNo// "siteurl Nodes not found"
0x205021  call     void Microsoft.Crm.ObjectModel.SharePointTelemetryHelper::LogError(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string ExceptionMessage)
0x205026  ldloc.3
0x205027  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x20502c  ldarg.0
0x20502d  ldfld    string Microsoft.Crm.ObjectModel.SPCommands.CreateSubSiteUrl::sharePointUrlsXml
0x205032  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0x205037  ldloc.3
0x205038  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x20503d  stloc.s  0xA
0x20503f  br       loc_2052B7
0x205044  ldloc.s  0xA
0x205046  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x20504b  castclass [System.Xml]System.Xml.XmlNode
0x205050  stloc.s  0xB
0x205052  ldloc.s  0xB
0x205054  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205059  brfalse.s loc_2050A6
0x20505b  ldloc.s  0xB
0x20505d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205062  callvirt instance int32 [System.Xml]System.Xml.XmlNamedNodeMap::get_Count()
0x205067  ldc.i4.3
0x205068  blt.s    loc_2050A6
0x20506a  ldloc.s  0xB
0x20506c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205071  ldstr    aUrl// "url"
0x205076  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x20507b  brfalse.s loc_2050A6
0x20507d  ldloc.s  0xB
0x20507f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205084  ldstr    aSubsite// "subsite"
0x205089  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x20508e  brfalse.s loc_2050A6
0x205090  ldloc.s  0xB
0x205092  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205097  ldstr    aTitle_0// "title"
0x20509c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2050a1  brtrue   loc_20518D
0x2050a6  ldstr    asc_24F76C// ""
0x2050ab  stloc.s  0xD
0x2050ad  ldloc.s  0xB
0x2050af  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2050b4  brfalse  loc_205173
0x2050b9  ldloc.s  0xD
0x2050bb  ldstr    aUrl_2// "url:"
0x2050c0  ldloc.s  0xB
0x2050c2  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2050c7  ldstr    aUrl// "url"
0x2050cc  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2050d1  call     string [mscorlib]System.String::Concat(object, object, object)
0x2050d6  brtrue.s loc_2050DF
0x2050d8  ldstr    aNull// "null"
0x2050dd  br.s     loc_2050F5
0x2050df  ldloc.s  0xB
0x2050e1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2050e6  ldstr    aUrl// "url"
0x2050eb  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2050f0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2050f5  stloc.s  0xD
0x2050f7  ldloc.s  0xD
0x2050f9  ldstr    aSubsite_0// "subsite:"
0x2050fe  ldloc.s  0xB
0x205100  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205105  ldstr    aSubsite// "subsite"
0x20510a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x20510f  call     string [mscorlib]System.String::Concat(object, object, object)
0x205114  brtrue.s loc_20511D
0x205116  ldstr    aNull// "null"
0x20511b  br.s     loc_205133
0x20511d  ldloc.s  0xB
0x20511f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205124  ldstr    aSubsite// "subsite"
0x205129  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x20512e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x205133  stloc.s  0xD
0x205135  ldloc.s  0xD
0x205137  ldstr    aTitle_2// "title:"
0x20513c  ldloc.s  0xB
0x20513e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205143  ldstr    aTitle_0// "title"
0x205148  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x20514d  call     string [mscorlib]System.String::Concat(object, object, object)
0x205152  brtrue.s loc_20515B
0x205154  ldstr    aNull// "null"
0x205159  br.s     loc_205171
0x20515b  ldloc.s  0xB
0x20515d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205162  ldstr    aTitle_0// "title"
0x205167  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x20516c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x205171  stloc.s  0xD
0x205173  ldc.i4.0
0x205174  ldarg.0
0x205175  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.CreateSubSiteUrl::context
0x20517a  ldstr    aCreatesubsiteu// "CreateSubSiteUrl"
0x20517f  ldc.i4   0x80060763
0x205184  ldloc.s  0xD
0x205186  ldnull
0x205187  call     class [mscorlib]System.Exception Microsoft.Crm.ObjectModel.SharePointErrorHandler::LogTelemetryAndThrowException(valuetype ErrorTelemetryEventType errorEventType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string exceptionMessage, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x20518c  throw
0x20518d  ldloc.0
0x20518e  ldc.i4.1
0x20518f  add
0x205190  stloc.0
0x205191  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x205196  stloc.s  0xC
0x205198  ldloc.s  0xC
0x20519a  ldstr    aSubsite// "subsite"
0x20519f  ldloc.s  0xB
0x2051a1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2051a6  ldstr    aSubsite// "subsite"
0x2051ab  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2051b0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2051b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2051ba  ldloc.s  0xC
0x2051bc  ldstr    aTitle_0// "title"
0x2051c1  ldloc.s  0xB
0x2051c3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2051c8  ldstr    aTitle_0// "title"
0x2051cd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2051d2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2051d7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2051dc  ldloc.s  0xC
0x2051de  ldstr    aTemplate// "template"
0x2051e3  ldloc.s  0xB
0x2051e5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2051ea  ldstr    aTemplate// "template"
0x2051ef  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2051f4  brtrue.s loc_2051FD
0x2051f6  ldstr    aSts0// "STS#0"
0x2051fb  br.s     loc_205213
0x2051fd  ldloc.s  0xB
0x2051ff  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205204  ldstr    aTemplate// "template"
0x205209  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x20520e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x205213  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x205218  ldloc.s  0xC
0x20521a  ldstr    aDescription// "description"
0x20521f  ldloc.s  0xB
0x205221  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205226  ldstr    aDescription// "description"
0x20522b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x205230  brtrue.s loc_205239
0x205232  ldsfld   string [mscorlib]System.String::Empty
0x205237  br.s     loc_20524F
0x205239  ldloc.s  0xB
0x20523b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x205240  ldstr    aDescription// "description"
0x205245  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x20524a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x20524f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x205254  ldloc.1
0x205255  ldloc.s  0xB
0x205257  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x20525c  ldstr    aUrl// "url"
0x205261  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x205266  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x20526b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::ContainsKey(var<u1>)
0x205270  brtrue.s loc_205293
0x205272  ldloc.1
0x205273  ldloc.s  0xB
0x205275  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x20527a  ldstr    aUrl// "url"
0x20527f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x205284  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x205289  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x20528e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::Add(var<u1>, !!T0)
0x205293  ldloc.1
0x205294  ldloc.s  0xB
0x205296  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x20529b  ldstr    aUrl// "url"
0x2052a0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2052a5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2052aa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::get_Item(void)
0x2052af  ldloc.s  0xC
0x2052b1  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x2052b6  pop
0x2052b7  ldloc.s  0xA
0x2052b9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2052be  brtrue   loc_205044
0x2052c3  leave.s  loc_2052DA
0x2052c5  ldloc.s  0xA
0x2052c7  isinst   [mscorlib]System.IDisposable
0x2052cc  stloc.s  0xE
0x2052ce  ldloc.s  0xE
0x2052d0  brfalse.s loc_2052D9
0x2052d2  ldloc.s  0xE
0x2052d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2052d9  endfinally
0x2052da  ldloc.0
0x2052db  newarr   [mscorlib]System.Boolean
0x2052e0  stloc.s  5
0x2052e2  ldsfld   string [mscorlib]System.String::Empty
0x2052e7  stloc.s  6
0x2052e9  ldloc.2
0x2052ea  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2052ef  stloc.s  7
0x2052f1  ldloc.2
0x2052f2  ldstr    aErrorlog// "errorlog"
0x2052f7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2052fc  stloc.s  8
0x2052fe  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x205303  pop
0x205304  ldloc.0
0x205305  ldc.i4.0
0x205306  ble.s    loc_205349
0x205308  newobj   instance void Microsoft.Crm.ObjectModel.SharePointDataProcessorFactory::.ctor()
0x20530d  ldc.i4.0
0x20530e  call     instance class Microsoft.Crm.ObjectModel.SharePointDataProcessor Microsoft.Crm.ObjectModel.SharePointDataProcessorFactory::GetDataProcessor(valuetype Microsoft.Crm.ObjectModel.DataProcessorType type)
0x205313  stloc.s  0xF
0x205315  ldloc.s  0xF
0x205317  ldloc.1
0x205318  ldloc.0
0x205319  ldarg.0
0x20531a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.CreateSubSiteUrl::context
0x20531f  ldloca.s 6
0x205321  callvirt instance bool[] Microsoft.Crm.ObjectModel.SharePointDataProcessor::CreateSharePointSubSite(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList> sharePointUrls, int32 noOfSubSites, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& creationLog)
0x205326  stloc.s  5
0x205328  leave.s  loc_205336
0x20532a  ldloc.s  0xF
0x20532c  brfalse.s loc_205335
0x20532e  ldloc.s  0xF
0x205330  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x205335  endfinally
0x205336  ldloc.s  8
0x205338  ldloc.s  6
0x20533a  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x20533f  ldloc.s  7
0x205341  ldloc.s  8
0x205343  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x205348  pop
0x205349  ldc.i4.0
0x20534a  stloc.s  9
0x20534c  ldloc.3
0x20534d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x205352  stloc.s  0xA
0x205354  br.s     loc_20537A
0x205356  ldloc.s  0xA
0x205358  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x20535d  castclass [System.Xml]System.Xml.XmlNode
0x205362  ldloc.s  5
0x205364  ldloc.s  9
0x205366  dup
0x205367  ldc.i4.1
0x205368  add
0x205369  stloc.s  9
0x20536b  ldelema  [mscorlib]System.Boolean
0x205370  call     instance string [mscorlib]System.Boolean::ToString()
0x205375  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x20537a  ldloc.s  0xA
0x20537c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x205381  brtrue.s loc_205356
0x205383  leave.s  loc_20539A
0x205385  ldloc.s  0xA
0x205387  isinst   [mscorlib]System.IDisposable
0x20538c  stloc.s  0xE
0x20538e  ldloc.s  0xE
0x205390  brfalse.s loc_205399
0x205392  ldloc.s  0xE
0x205394  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x205399  endfinally
0x20539a  ldloc.s  4
0x20539c  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x2053a1  ldarg.0
0x2053a2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.CreateSubSiteUrl::context
0x2053a7  ldstr    aCreatesubsiteu// "CreateSubSiteUrl"
0x2053ac  ldstr    aTotaltimetaken// "TotalTimeTaken"
0x2053b1  ldloc.s  4
0x2053b3  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
  ... truncated ...
```
