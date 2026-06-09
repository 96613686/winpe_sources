# Microsoft.Crm.Common.Application.Pages.MA.ListQualifyPage::ConfigureForm

- ea: `0x17020`
- end: `0x17376`
- name: `Microsoft.Crm.Common.Application.Pages.MA.ListQualifyPage::ConfigureForm`
- size: `854`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x17020`

## string_xrefs

- `0x17349`: `ListQualifyPage.ConfigureForm There was an error while trying to execute the list qualification code.\nError Message: {0}\nStack Trace:\n {1}`

## pseudocode

```c

```

## disassembly

```asm
0x17020  ldarg.0
0x17021  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17026  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1702b  ldsfld   string [mscorlib]System.String::Empty
0x17030  stloc.0
0x17031  ldsfld   string [mscorlib]System.String::Empty
0x17036  stloc.1
0x17037  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1703c  ldc.i4.0
0x1703d  conv.i8
0x1703e  ble      loc_17375
0x17043  ldarg.0
0x17044  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17049  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1704e  ldstr    aItemobjectid// "itemObjectId"
0x17053  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17058  ldnull
0x17059  cgt.un
0x1705b  ldstr    aInvalidList// "Invalid list"
0x17060  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x17065  ldarg.0
0x17066  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1706b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17070  ldstr    aIoption// "iOption"
0x17075  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1707a  ldnull
0x1707b  cgt.un
0x1707d  ldstr    aInvalidOptionC// "Invalid option chosen"
0x17082  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x17087  ldarg.0
0x17088  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1708d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17092  ldstr    aIsdirty// "isDirty"
0x17097  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1709c  ldnull
0x1709d  cgt.un
0x1709f  ldstr    aInvalidParamet// "Invalid parameter"
0x170a4  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x170a9  ldarg.0
0x170aa  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x170af  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x170b4  ldstr    aItotal// "iTotal"
0x170b9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x170be  ldnull
0x170bf  cgt.un
0x170c1  ldstr    aInvalidLength// "Invalid length"
0x170c6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x170cb  ldarg.0
0x170cc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x170d1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x170d6  ldstr    aSinvoketype// "sInvokeType"
0x170db  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x170e0  ldnull
0x170e1  cgt.un
0x170e3  ldstr    aInvalidParamet// "Invalid parameter"
0x170e8  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x170ed  ldarg.0
0x170ee  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x170f3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x170f8  ldstr    aSinvoketype// "sInvokeType"
0x170fd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17102  stloc.2
0x17103  ldstr    aList// "list"
0x17108  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1710d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17112  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.List::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x17117  stloc.3
0x17118  ldarg.0
0x17119  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1711e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17123  ldstr    aItemobjectid// "itemObjectId"
0x17128  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1712d  stloc.s  4
0x1712f  ldarg.0
0x17130  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17135  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1713a  ldstr    aIoption// "iOption"
0x1713f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17144  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17149  call     int16 [mscorlib]System.Int16::Parse(string, class [mscorlib]System.IFormatProvider)
0x1714e  stloc.s  5
0x17150  ldnull
0x17151  stloc.s  6
0x17153  ldnull
0x17154  stloc.s  7
0x17156  ldc.i4.0
0x17157  stloc.s  8
0x17159  ldarg.0
0x1715a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1715f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17164  ldstr    aItotal// "iTotal"
0x17169  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1716e  ldstr    a0// "0"
0x17173  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x17178  brfalse  loc_1720B
0x1717d  ldloc.s  5
0x1717f  ldc.i4.1
0x17180  bne.un   loc_1720B
0x17185  ldarg.0
0x17186  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1718b  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x17190  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(class [mscorlib]System.IO.Stream)
0x17195  stloc.s  6
0x17197  ldloc.s  6
0x17199  ldstr    aRootIdsId// "//root/Ids/Id"
0x1719e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x171a3  stloc.s  0xB
0x171a5  ldloc.s  0xB
0x171a7  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x171ac  newarr   [mscorlib]System.String
0x171b1  stloc.s  7
0x171b3  ldloc.s  0xB
0x171b5  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x171ba  stloc.s  0xC
0x171bc  br.s     loc_171DD
0x171be  ldloc.s  0xC
0x171c0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x171c5  castclass [System.Xml]System.Xml.XmlNode
0x171ca  stloc.s  0xD
0x171cc  ldloc.s  7
0x171ce  ldloc.s  8
0x171d0  dup
0x171d1  ldc.i4.1
0x171d2  add
0x171d3  stloc.s  8
0x171d5  ldloc.s  0xD
0x171d7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x171dc  stelem.ref
0x171dd  ldloc.s  0xC
0x171df  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x171e4  brtrue.s loc_171BE
0x171e6  leave.s  loc_171FD
0x171e8  ldloc.s  0xC
0x171ea  isinst   [mscorlib]System.IDisposable
0x171ef  stloc.s  0xE
0x171f1  ldloc.s  0xE
0x171f3  brfalse.s loc_171FC
0x171f5  ldloc.s  0xE
0x171f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x171fc  endfinally
0x171fd  leave.s  loc_1720B
0x171ff  ldloc.s  0xB
0x17201  brfalse.s loc_1720A
0x17203  ldloc.s  0xB
0x17205  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1720a  endfinally
0x1720b  ldstr    aFalse// "false"
0x17210  stloc.s  9
0x17212  ldarg.0
0x17213  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17218  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1721d  ldstr    aIsdirty// "isDirty"
0x17222  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17227  stloc.s  9
0x17229  ldloc.s  9
0x1722b  ldstr    aTrue// "true"
0x17230  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17235  brfalse.s loc_17261
0x17237  ldloc.s  6
0x17239  brtrue.s loc_1724D
0x1723b  ldarg.0
0x1723c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17241  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x17246  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(class [mscorlib]System.IO.Stream)
0x1724b  stloc.s  6
0x1724d  ldloc.s  6
0x1724f  ldstr    aRootFetch// "//root/fetch"
0x17254  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17259  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x1725e  stloc.0
0x1725f  br.s     loc_17277
0x17261  ldarg.0
0x17262  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17267  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1726c  ldstr    aSavedqueryid// "savedQueryId"
0x17271  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17276  stloc.1
0x17277  ldc.i4.0
0x17278  stloc.s  0xA
0x1727a  ldloc.2
0x1727b  ldstr    aLqkeep// "lqKeep"
0x17280  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17285  brfalse.s loc_1728A
0x17287  ldc.i4.1
0x17288  stloc.s  0xA
0x1728a  ldloc.s  5
0x1728c  ldc.i4.1
0x1728d  bne.un.s loc_172DA
0x1728f  ldc.i4.0
0x17290  stloc.s  0xF
0x17292  br.s     loc_172D0
0x17294  ldloc.s  7
0x17296  ldloc.s  0xF
0x17298  ldelem.ref
0x17299  callvirt instance string [mscorlib]System.Object::ToString()
0x1729e  ldc.i4.1
0x1729f  newarr   [mscorlib]System.Char
0x172a4  dup
0x172a5  ldc.i4.0
0x172a6  ldc.i4.s 0x2C
0x172a8  stelem.i2
0x172a9  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x172ae  call     valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ConvertStringArrayToGuidArray(string[])
0x172b3  stloc.s  0x10
0x172b5  ldloc.s  4
0x172b7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x172bc  ldloc.s  0x10
0x172be  ldloc.s  0xA
0x172c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x172c5  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QualifyMembersList(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid[], bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x172ca  ldloc.s  0xF
0x172cc  ldc.i4.1
0x172cd  add
0x172ce  stloc.s  0xF
0x172d0  ldloc.s  0xF
0x172d2  ldloc.s  7
0x172d4  ldlen
0x172d5  conv.i4
0x172d6  blt.s    loc_17294
0x172d8  br.s     loc_17329
0x172da  ldloc.s  5
0x172dc  ldc.i4.2
0x172dd  bne.un.s loc_17329
0x172df  ldloc.s  9
0x172e1  ldstr    aTrue// "true"
0x172e6  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x172eb  brfalse.s loc_1731E
0x172ed  ldloc.1
0x172ee  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x172f3  ldarg.0
0x172f4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x172f9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x172fe  ldstr    aSavedquerytype// "savedQueryType"
0x17303  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17308  ldc.i4.7
0x17309  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1730e  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x17313  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.ViewLoader::GetView(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x17318  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_FetchXml()
0x1731d  stloc.0
0x1731e  ldloc.3
0x1731f  ldloc.s  4
0x17321  ldloc.0
0x17322  ldloc.s  0xA
0x17324  callvirt instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.List::QualifyListByFetchXml(string, string, bool)
0x17329  ldarg.0
0x1732a  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1732f  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x17334  leave.s  loc_17375
0x17336  stloc.s  0x11
0x17338  ldloc.s  0x11
0x1733a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1733f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x17344  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x17349  ldstr    aListqualifypag// "ListQualifyPage.ConfigureForm There was"...
0x1734e  ldc.i4.2
0x1734f  newarr   [mscorlib]System.Object
0x17354  dup
0x17355  ldc.i4.0
0x17356  ldloc.s  0x11
0x17358  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1735d  stelem.ref
0x1735e  dup
0x1735f  ldc.i4.1
0x17360  ldloc.s  0x11
0x17362  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x17367  stelem.ref
0x17368  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1736d  ldloc.s  0x11
0x1736f  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x17374  throw
0x17375  ret
```
