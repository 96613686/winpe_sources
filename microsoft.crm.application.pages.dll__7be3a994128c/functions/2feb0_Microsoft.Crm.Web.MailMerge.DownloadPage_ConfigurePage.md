# Microsoft.Crm.Web.MailMerge.DownloadPage::ConfigurePage

- ea: `0x2feb0`
- end: `0x302e1`
- name: `Microsoft.Crm.Web.MailMerge.DownloadPage::ConfigurePage`
- size: `1073`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2feb0`

## string_xrefs

- `0x3028c`: `text/xml`
- `0x30027`: `layoutXml`
- `0x2ff48`: `templateid`
- `0x2ff66`: `templateid`
- `0x30010`: `gridxml`
- `0x300c7`: `mailmergetemplate`
- `0x3016b`: `BlankMailMerge.xml`

## pseudocode

```c

```

## disassembly

```asm
0x2feb0  ldc.i4.0
0x2feb1  stloc.0
0x2feb2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2feb7  stloc.1
0x2feb8  ldc.i4.0
0x2feb9  stloc.2
0x2feba  ldc.i4.0
0x2febb  stloc.3
0x2febc  ldsfld   string [mscorlib]System.String::Empty
0x2fec1  stloc.s  4
0x2fec3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2fec8  stloc.s  5
0x2feca  ldc.i4.0
0x2fecb  stloc.s  6
0x2fecd  ldsfld   string [mscorlib]System.String::Empty
0x2fed2  stloc.s  7
0x2fed4  ldsfld   string [mscorlib]System.String::Empty
0x2fed9  stloc.s  8
0x2fedb  ldc.i4.0
0x2fedc  stloc.s  9
0x2fede  ldarg.0
0x2fedf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2fee4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2fee9  ldstr    aOtc// "otc"
0x2feee  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2fef3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2fef8  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x2fefd  stloc.0
0x2fefe  ldarg.0
0x2feff  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2ff04  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2ff09  ldstr    aOid// "oid"
0x2ff0e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ff13  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2ff18  brtrue.s loc_2FF3D
0x2ff1a  ldloca.s 1
0x2ff1c  ldarg.0
0x2ff1d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2ff22  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2ff27  ldstr    aOid// "oid"
0x2ff2c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ff31  call     string [System]System.Uri::UnescapeDataString(string)
0x2ff36  call     instance void [mscorlib]System.Guid::.ctor(string)
0x2ff3b  ldc.i4.1
0x2ff3c  stloc.2
0x2ff3d  ldarg.0
0x2ff3e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2ff43  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2ff48  ldstr    aTemplateid_1// "templateid"
0x2ff4d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ff52  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2ff57  brtrue.s loc_2FF7A
0x2ff59  ldloca.s 5
0x2ff5b  ldarg.0
0x2ff5c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2ff61  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2ff66  ldstr    aTemplateid_1// "templateid"
0x2ff6b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ff70  call     string [System]System.Uri::UnescapeDataString(string)
0x2ff75  call     instance void [mscorlib]System.Guid::.ctor(string)
0x2ff7a  ldarg.0
0x2ff7b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2ff80  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2ff85  ldstr    aCurrentpage// "currentpage"
0x2ff8a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ff8f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2ff94  brtrue.s loc_2FFB2
0x2ff96  ldarg.0
0x2ff97  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2ff9c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2ffa1  ldstr    aCurrentpage// "currentpage"
0x2ffa6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ffab  call     bool [mscorlib]System.Boolean::Parse(string)
0x2ffb0  stloc.s  6
0x2ffb2  ldarg.0
0x2ffb3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2ffb8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2ffbd  ldstr    aLanguageid// "languageid"
0x2ffc2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ffc7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2ffcc  brtrue.s loc_2FFEE
0x2ffce  ldarg.0
0x2ffcf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2ffd4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2ffd9  ldstr    aLanguageid// "languageid"
0x2ffde  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ffe3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ffe8  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x2ffed  stloc.3
0x2ffee  ldarg.0
0x2ffef  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2fff4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x2fff9  ldstr    aIds// "ids"
0x2fffe  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x30003  stloc.s  4
0x30005  ldarg.0
0x30006  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3000b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x30010  ldstr    aGridxml_0// "gridxml"
0x30015  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3001a  stloc.s  7
0x3001c  ldarg.0
0x3001d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x30022  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x30027  ldstr    aLayoutxml// "layoutXml"
0x3002c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x30031  stloc.s  8
0x30033  ldarg.0
0x30034  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x30039  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3003e  ldstr    aMergetype// "mergetype"
0x30043  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x30048  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3004d  brtrue.s loc_30070
0x3004f  ldarg.0
0x30050  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x30055  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3005a  ldstr    aMergetype// "mergetype"
0x3005f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x30064  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30069  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3006e  stloc.s  9
0x30070  ldloc.s  4
0x30072  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x30077  brfalse.s loc_3009A
0x30079  ldloc.s  7
0x3007b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x30080  brfalse.s loc_3009A
0x30082  ldloc.1
0x30083  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x30088  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3008d  brfalse.s loc_3009A
0x3008f  ldstr    aNotAllInputWas// "Not all input was provided."
0x30094  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x30099  throw
0x3009a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3009f  stloc.s  0xA
0x300a1  ldloc.s  0xA
0x300a3  ldloc.s  8
0x300a5  call     class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::RetrieveColumns(string)
0x300aa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x300af  ldsfld   string [mscorlib]System.String::Empty
0x300b4  stloc.s  0xB
0x300b6  ldloc.s  5
0x300b8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x300bd  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x300c2  brfalse  loc_3015B
0x300c7  ldstr    aMailmergetempl// "mailmergetemplate"
0x300cc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x300d1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x300d6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x300db  ldloc.s  5
0x300dd  ldc.i4.4
0x300de  newarr   [mscorlib]System.String
0x300e3  dup
0x300e4  ldc.i4.0
0x300e5  ldstr    aFilename// "filename"
0x300ea  stelem.ref
0x300eb  dup
0x300ec  ldc.i4.1
0x300ed  ldstr    aBody_0// "body"
0x300f2  stelem.ref
0x300f3  dup
0x300f4  ldc.i4.2
0x300f5  ldstr    aDefaultfilter// "defaultfilter"
0x300fa  stelem.ref
0x300fb  dup
0x300fc  ldc.i4.3
0x300fd  ldstr    aMimetype// "mimetype"
0x30102  stelem.ref
0x30103  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x30108  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3010d  stloc.s  0xF
0x3010f  ldloc.s  0xF
0x30111  ldstr    aBody_0// "body"
0x30116  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3011b  brfalse.s loc_30135
0x3011d  ldloc.s  0xF
0x3011f  ldstr    aBody_0// "body"
0x30124  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x30129  isinst   [mscorlib]System.String
0x3012e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::DecodeFileContent(string)
0x30133  stloc.s  0xB
0x30135  ldloc.s  0xA
0x30137  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x3013c  brtrue.s loc_3015B
0x3013e  ldloc.s  0xA
0x30140  ldloc.s  0xF
0x30142  ldstr    aDefaultfilter// "defaultfilter"
0x30147  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3014c  isinst   [mscorlib]System.String
0x30151  call     class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::RetrieveColumns(string)
0x30156  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x3015b  ldloc.s  0xB
0x3015d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x30162  brfalse.s loc_3017C
0x30164  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInServerContext()
0x30169  brfalse.s loc_3017C
0x3016b  ldstr    aBlankmailmerge// "BlankMailMerge.xml"
0x30170  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath(string)
0x30175  call     string [mscorlib]System.IO.File::ReadAllText(string)
0x3017a  stloc.s  0xB
0x3017c  ldloc.3
0x3017d  ldc.i4.0
0x3017e  bgt.s    loc_3018B
0x30180  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x30185  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x3018a  stloc.3
0x3018b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::.ctor()
0x30190  stloc.s  0xC
0x30192  ldloc.s  0xC
0x30194  ldloc.s  5
0x30196  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::set_TemplateId(valuetype [mscorlib]System.Guid)
0x3019b  ldloc.2
0x3019c  brfalse.s loc_301AE
0x3019e  ldloc.s  0xC
0x301a0  ldloc.s  0xA
0x301a2  ldloc.0
0x301a3  ldloc.1
0x301a4  ldloc.3
0x301a5  ldloc.s  9
0x301a7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::PrepareObjectComment(class [mscorlib]System.Collections.Generic.List`1<string>, int32, valuetype [mscorlib]System.Guid, int32, int32)
0x301ac  br.s     loc_301C1
0x301ae  ldloc.s  0xC
0x301b0  ldloc.s  0xA
0x301b2  ldloc.0
0x301b3  ldloc.3
0x301b4  ldloc.s  6
0x301b6  ldloc.s  4
0x301b8  ldloc.s  7
0x301ba  ldloc.s  9
0x301bc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::PrepareComment(class [mscorlib]System.Collections.Generic.List`1<string>, int32, int32, bool, string, string, int32)
0x301c1  stloc.s  0xD
0x301c3  ldloc.s  0xD
0x301c5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x301ca  dup
0x301cb  ldstr    asc_14103E// "\r\n"
0x301d0  ldstr    aBr// "<br/>"
0x301d5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x301da  ldstr    asc_141050// "\n\r"
0x301df  ldstr    aBr// "<br/>"
0x301e4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x301e9  ldstr    asc_141056// "\r"
0x301ee  ldstr    aBr// "<br/>"
0x301f3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x301f8  ldstr    asc_14105A// "\n"
0x301fd  ldstr    aBr// "<br/>"
0x30202  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x30207  pop
0x30208  dup
0x30209  ldstr    asc_14105E// "\t"
0x3020e  ldstr    aNbspNbspNbspNb// "&nbsp;&nbsp;&nbsp;&nbsp;"
0x30213  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x30218  pop
0x30219  callvirt instance string [mscorlib]System.Object::ToString()
0x3021e  stloc.s  0xD
0x30220  ldloc.s  0xB
0x30222  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x30227  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeFileHandler::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3022c  ldloc.s  9
0x3022e  ldarg.0
0x3022f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x30234  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x30239  ldloc.s  0xD
0x3023b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeFileHandler::ProcessForWebDownload(int32, class [System]System.Uri, string)
0x30240  stloc.s  0xB
0x30242  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30247  ldarg.0
0x30248  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3024d  ldstr    aMailmergeDocum// "MailMerge_Document_Filename"
0x30252  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x30257  ldc.i4.1
0x30258  newarr   [mscorlib]System.Object
0x3025d  dup
0x3025e  ldc.i4.0
0x3025f  newobj   instance void [mscorlib]System.Random::.ctor()
0x30264  ldc.i4   0x1869F
0x30269  callvirt instance int32 [mscorlib]System.Random::Next(int32)
0x3026e  box      [mscorlib]System.Int32
0x30273  stelem.ref
0x30274  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x30279  stloc.s  0xE
0x3027b  ldarg.0
0x3027c  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x30281  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x30286  ldarg.0
0x30287  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x3028c  ldstr    aTextXml// "text/xml"
0x30291  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x30296  ldarg.0
0x30297  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x3029c  ldstr    aContentDisposi// "Content-Disposition"
0x302a1  ldarg.0
0x302a2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x302a7  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x302ac  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x302b1  ldloc.s  0xE
0x302b3  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetContentDispositionHeader(string, string)
0x302b8  callvirt instance void [System.Web]System.Web.HttpResponse::AppendHeader(string, string)
0x302bd  ldarg.0
  ... truncated ...
```
