# Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlViewer::ConfigurePage

- ea: `0x162f0`
- end: `0x16437`
- name: `Microsoft.Crm.Common.Application.Pages.Tools.Common.XmlViewer::ConfigurePage`
- size: `327`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x162f0`

## string_xrefs

- `0x16388`: `text/xml`
- `0x1642c`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x162f0  ldarg.0
0x162f1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x162f6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x162fb  ldstr    aXml// "xml"
0x16300  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16305  stloc.0
0x16306  ldc.i4.0
0x16307  stloc.1
0x16308  ldarg.0
0x16309  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1630e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16313  ldstr    aDownload// "download"
0x16318  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1631d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16322  brtrue.s loc_1633F
0x16324  ldarg.0
0x16325  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1632a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1632f  ldstr    aDownload// "download"
0x16334  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16339  call     bool [mscorlib]System.Boolean::Parse(string)
0x1633e  stloc.1
0x1633f  ldloc.1
0x16340  brfalse  loc_16426
0x16345  ldloc.0
0x16346  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1634b  brfalse.s loc_16355
0x1634d  ldstr    a0// "0"
0x16352  stloc.2
0x16353  br.s     loc_16377
0x16355  ldloc.0
0x16356  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x1635b  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAppHelper::GetFormattedOuterXml(class [System.Xml]System.Xml.XPath.IXPathNavigable)
0x16360  stloc.0
0x16361  ldloc.0
0x16362  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16367  stloc.s  4
0x16369  ldloca.s 4
0x1636b  ldstr    aD_0// "d"
0x16370  ldnull
0x16371  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x16376  stloc.2
0x16377  ldarg.0
0x16378  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1637d  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x16382  ldarg.0
0x16383  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x16388  ldstr    aTextXml// "text/xml"
0x1638d  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x16392  ldsfld   string [mscorlib]System.String::Empty
0x16397  stloc.3
0x16398  ldarg.0
0x16399  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1639e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x163a3  ldstr    aFilename_0// "fileName"
0x163a8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x163ad  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x163b2  brtrue.s loc_163CA
0x163b4  ldarg.0
0x163b5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x163ba  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x163bf  ldstr    aFilename_0// "fileName"
0x163c4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x163c9  stloc.3
0x163ca  ldloc.3
0x163cb  ldstr    aXml_0// ".xml"
0x163d0  ldc.i4.0
0x163d1  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GenerateEncodedExcelFileName(string, string, bool)
0x163d6  stloc.3
0x163d7  ldarg.0
0x163d8  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x163dd  ldstr    aContentDisposi// "Content-Disposition"
0x163e2  ldarg.0
0x163e3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x163e8  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x163ed  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x163f2  ldloc.3
0x163f3  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetContentDispositionHeaderForEncodedFileName(string, string)
0x163f8  callvirt instance void [System.Web]System.Web.HttpResponse::AppendHeader(string, string)
0x163fd  ldarg.0
0x163fe  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x16403  ldstr    aContentLength// "Content-Length"
0x16408  ldloc.2
0x16409  callvirt instance void [System.Web]System.Web.HttpResponse::AppendHeader(string, string)
0x1640e  ldarg.0
0x1640f  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x16414  ldloc.0
0x16415  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1641a  ldarg.0
0x1641b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x16420  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x16425  ret
0x16426  ldarg.0
0x16427  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1642c  ldstr    aTextXml// "text/xml"
0x16431  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x16436  ret
```
