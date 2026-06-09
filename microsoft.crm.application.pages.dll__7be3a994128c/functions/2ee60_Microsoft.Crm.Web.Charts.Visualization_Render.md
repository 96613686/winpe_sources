# Microsoft.Crm.Web.Charts.Visualization::Render

- ea: `0x2ee60`
- end: `0x2f44e`
- name: `Microsoft.Crm.Web.Charts.Visualization::Render`
- size: `1518`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2e7c0`
- `0x2e7e0`
- `0x2e8c0`
- `0x2e9b0`
- `0x2ed70`
- `0x2ee60`

## string_xrefs

- `0x2f084`: `application/json`
- `0x2f3f2`: `application/json`
- `0x2eed9`: `isDashboardComponent`
- `0x2f1b0`: `DATA Uri used for generating chart image for visualization named : {0}`
- `0x2f25e`: `Response for the chart page created at: {0}\nTotal time taken; {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2ee60  ldc.i4.0
0x2ee61  stloc.0
0x2ee62  ldc.i4.0
0x2ee63  stloc.1
0x2ee64  ldc.i4.0
0x2ee65  stloc.2
0x2ee66  ldc.i4.0
0x2ee67  stloc.3
0x2ee68  ldc.i4.0
0x2ee69  stloc.s  4
0x2ee6b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x2ee70  stloc.s  5
0x2ee72  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2ee77  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2ee7c  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x2ee81  ldstr    aChartStartedLo// "Chart started loading at: {0}"
0x2ee86  ldc.i4.1
0x2ee87  newarr   [mscorlib]System.Object
0x2ee8c  dup
0x2ee8d  ldc.i4.0
0x2ee8e  ldloca.s 5
0x2ee90  call     instance string [mscorlib]System.DateTime::ToString()
0x2ee95  stelem.ref
0x2ee96  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2ee9b  ldarg.0
0x2ee9c  call     instance void Microsoft.Crm.Web.Charts.Visualization::ReadVisualizationParameters()
0x2eea1  ldarg.0
0x2eea2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2eea7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2eeac  ldstr    aImg// "img"
0x2eeb1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2eeb6  brfalse.s loc_2EED3
0x2eeb8  ldarg.0
0x2eeb9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2eebe  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2eec3  ldstr    aImg// "img"
0x2eec8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2eecd  call     bool [mscorlib]System.Boolean::Parse(string)
0x2eed2  stloc.2
0x2eed3  ldarg.0
0x2eed4  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Charts.Visualization::_parameters
0x2eed9  ldstr    aIsdashboardcom// "isDashboardComponent"
0x2eede  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2eee3  stloc.s  6
0x2eee5  ldloc.s  6
0x2eee7  brfalse.s loc_2EEF1
0x2eee9  ldloc.s  6
0x2eeeb  call     bool [mscorlib]System.Boolean::Parse(string)
0x2eef0  stloc.3
0x2eef1  ldarg.0
0x2eef2  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Charts.Visualization::_parameters
0x2eef7  ldstr    aIspreview// "isPreview"
0x2eefc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ef01  stloc.s  6
0x2ef03  ldloc.s  6
0x2ef05  brfalse.s loc_2EF0F
0x2ef07  ldloc.s  6
0x2ef09  call     bool [mscorlib]System.Boolean::Parse(string)
0x2ef0e  stloc.0
0x2ef0f  ldarg.0
0x2ef10  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Charts.Visualization::_parameters
0x2ef15  ldstr    aFetchpublished// "fetchPublishedForSystem"
0x2ef1a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ef1f  stloc.s  6
0x2ef21  ldloc.s  6
0x2ef23  brfalse.s loc_2EF2D
0x2ef25  ldloc.s  6
0x2ef27  call     bool [mscorlib]System.Boolean::Parse(string)
0x2ef2c  stloc.1
0x2ef2d  ldarg.0
0x2ef2e  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Charts.Visualization::_parameters
0x2ef33  ldstr    aIsios// "isIOS"
0x2ef38  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ef3d  stloc.s  6
0x2ef3f  ldloc.s  6
0x2ef41  brfalse.s loc_2EF4C
0x2ef43  ldloc.s  6
0x2ef45  call     bool [mscorlib]System.Boolean::Parse(string)
0x2ef4a  stloc.s  4
0x2ef4c  ldarg.0
0x2ef4d  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Charts.Visualization::_parameters
0x2ef52  ldstr    aVistype_0// "visType"
0x2ef57  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ef5c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ef61  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x2ef66  stloc.s  7
0x2ef68  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2ef6d  stloc.s  8
0x2ef6f  ldc.i4.0
0x2ef70  stloc.s  9
0x2ef72  ldloc.0
0x2ef73  brtrue.s loc_2EF8E
0x2ef75  ldloca.s 8
0x2ef77  ldarg.0
0x2ef78  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Charts.Visualization::_parameters
0x2ef7d  ldstr    aVisualizationi_0// "visualizationId"
0x2ef82  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ef87  call     instance void [mscorlib]System.Guid::.ctor(string)
0x2ef8c  br.s     loc_2EF9D
0x2ef8e  ldloc.s  7
0x2ef90  ldc.i4   0x457
0x2ef95  bne.un.s loc_2EF9D
0x2ef97  ldloc.1
0x2ef98  brtrue.s loc_2EF9D
0x2ef9a  ldc.i4.1
0x2ef9b  stloc.s  9
0x2ef9d  ldloca.s 8
0x2ef9f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2efa4  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x2efa9  ldc.i4.0
0x2efaa  ceq
0x2efac  ldloc.0
0x2efad  or
0x2efae  brfalse  loc_2F28A
0x2efb3  ldloc.s  9
0x2efb5  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationContextManager::.ctor(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationMode)
0x2efba  stloc.s  0xC
0x2efbc  ldarg.0
0x2efbd  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Web.Charts.Visualization::_parameters
0x2efc2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderFactory::GetDataProvider(class [System]System.Collections.Specialized.NameValueCollection)
0x2efc7  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider)
0x2efcc  stloc.s  0xD
0x2efce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2efd3  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x2efd8  stloc.s  0xE
0x2efda  ldloc.s  0xE
0x2efdc  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x2efe1  stloc.s  0xF
0x2efe3  ldloc.s  0xD
0x2efe5  ldloc.s  0xF
0x2efe7  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::RenderVisualization(class [System.Web]System.Web.UI.HtmlTextWriter)
0x2efec  stloc.s  0x10
0x2efee  ldloc.2
0x2efef  ldloc.3
0x2eff0  and
0x2eff1  brfalse  loc_2F0B9
0x2eff6  newobj   instance void Microsoft.Crm.Web.Charts.VisualizationData::.ctor()
0x2effb  stloc.s  0x11
0x2effd  ldloc.s  0x10
0x2efff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f004  brfalse.s loc_2F046
0x2f006  ldloc.s  0x11
0x2f008  ldc.i4.0
0x2f009  stfld    bool Microsoft.Crm.Web.Charts.VisualizationData::isValid
0x2f00e  ldloc.s  0x11
0x2f010  ldarg.0
0x2f011  ldc.i4   0x8004E011
0x2f016  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2f01b  ldsfld   string [mscorlib]System.String::Empty
0x2f020  ldloc.3
0x2f021  ldloc.s  4
0x2f023  ldloc.s  0xD
0x2f025  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_VisualizationName()
0x2f02a  ldloc.s  0xD
0x2f02c  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_EntityDisplayName()
0x2f031  ldloc.s  0xD
0x2f033  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_EntityPluralName()
0x2f038  ldloca.s 0x13
0x2f03a  call     instance string Microsoft.Crm.Web.Charts.Visualization::GetErrorMessageString(valuetype [mscorlib]System.Nullable`1<int32> crmErrorCode, string exceptionMessage, bool isDashboardComponent, bool isIos, string visualizationName, string entityName, string pluralEntityName, [out] bool& isError)
0x2f03f  stfld    string Microsoft.Crm.Web.Charts.VisualizationData::message
0x2f044  br.s     loc_2F073
0x2f046  ldloc.s  0x11
0x2f048  ldc.i4.1
0x2f049  stfld    bool Microsoft.Crm.Web.Charts.VisualizationData::isValid
0x2f04e  ldloc.s  0x11
0x2f050  ldloc.s  0x10
0x2f052  stfld    string Microsoft.Crm.Web.Charts.VisualizationData::imageData
0x2f057  ldloc.s  0x11
0x2f059  ldloc.s  0xD
0x2f05b  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_ChartWidth()
0x2f060  stfld    int32 Microsoft.Crm.Web.Charts.VisualizationData::imageWidth
0x2f065  ldloc.s  0x11
0x2f067  ldloc.s  0xD
0x2f069  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_ChartHeight()
0x2f06e  stfld    int32 Microsoft.Crm.Web.Charts.VisualizationData::imageHeight
0x2f073  ldarg.0
0x2f074  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f079  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x2f07e  ldarg.0
0x2f07f  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f084  ldstr    aApplicationJso// "application/json"
0x2f089  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x2f08e  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x2f093  stloc.s  0x12
0x2f095  ldarg.0
0x2f096  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f09b  ldloc.s  0x12
0x2f09d  ldloc.s  0x11
0x2f09f  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x2f0a4  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2f0a9  ldarg.0
0x2f0aa  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f0af  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x2f0b4  br       loc_2F22F
0x2f0b9  ldloc.s  0x10
0x2f0bb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f0c0  brfalse.s loc_2F0F8
0x2f0c2  ldarg.0
0x2f0c3  ldc.i4   0x8004E011
0x2f0c8  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2f0cd  ldsfld   string [mscorlib]System.String::Empty
0x2f0d2  ldloc.s  0xD
0x2f0d4  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_VisualizationName()
0x2f0d9  ldloc.s  0xD
0x2f0db  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_EntityDisplayName()
0x2f0e0  ldloc.s  0xD
0x2f0e2  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_EntityTypeCode()
0x2f0e7  ldloc.s  0xD
0x2f0e9  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_EntityPluralName()
0x2f0ee  call     instance void Microsoft.Crm.Web.Charts.Visualization::RenderErrorHtml(valuetype [mscorlib]System.Nullable`1<int32> crmErrorCode, string exceptionMessage, string visualizationName, string entityName, int32 entityTypeCode, string entityPluralName)
0x2f0f3  leave    loc_2F44D
0x2f0f8  ldarg.0
0x2f0f9  call     instance string Microsoft.Crm.Web.Charts.Visualization::BuildPageHtmlContent()
0x2f0fe  stloc.s  0x14
0x2f100  ldloc.s  0xD
0x2f102  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_IsDataUriUsed()
0x2f107  stloc.s  0x15
0x2f109  ldloc.s  0x15
0x2f10b  brfalse.s loc_2F11A
0x2f10d  ldloc.s  0x15
0x2f10f  ldc.i4.1
0x2f110  beq      loc_2F1A1
0x2f115  br       loc_2F22F
0x2f11a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2f11f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2f124  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x2f129  ldstr    aMhtmlUsedForGe// "MHTML used for generating chart image f"...
0x2f12e  ldc.i4.1
0x2f12f  newarr   [mscorlib]System.Object
0x2f134  dup
0x2f135  ldc.i4.0
0x2f136  ldloc.s  0xD
0x2f138  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_VisualizationName()
0x2f13d  stelem.ref
0x2f13e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f143  ldarg.0
0x2f144  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f149  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.MultipartResponse::.ctor(class [System.Web]System.Web.HttpResponse)
0x2f14e  dup
0x2f14f  ldstr    aTextHtml// "text/html"
0x2f154  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.MultipartResponse::StartNextPart(string)
0x2f159  dup
0x2f15a  ldloc.s  0xE
0x2f15c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.IO.StringWriter::GetStringBuilder()
0x2f161  ldstr    aHtml// "</html>"
0x2f166  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f16b  ldc.i4.0
0x2f16c  ldloc.s  0x14
0x2f16e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Insert(int32, string)
0x2f173  callvirt instance string [mscorlib]System.Object::ToString()
0x2f178  ldc.i4.1
0x2f179  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.MultipartResponse::WriteHtml(string, bool)
0x2f17e  dup
0x2f17f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.MultipartResponse::EndPart()
0x2f184  dup
0x2f185  ldstr    aImagePng// "image/png"
0x2f18a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.MultipartResponse::StartNextPart(string)
0x2f18f  dup
0x2f190  ldloc.s  0x10
0x2f192  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.MultipartResponse::WriteImageBase64(string)
0x2f197  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.MultipartResponse::EndLastPart()
0x2f19c  br       loc_2F22F
0x2f1a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2f1a6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2f1ab  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x2f1b0  ldstr    aDataUriUsedFor// "DATA Uri used for generating chart imag"...
0x2f1b5  ldc.i4.1
0x2f1b6  newarr   [mscorlib]System.Object
0x2f1bb  dup
0x2f1bc  ldc.i4.0
0x2f1bd  ldloc.s  0xD
0x2f1bf  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_VisualizationName()
0x2f1c4  stelem.ref
0x2f1c5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f1ca  ldarg.0
0x2f1cb  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f1d0  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x2f1d5  ldarg.0
0x2f1d6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f1db  callvirt instance void [System.Web]System.Web.HttpResponse::ClearContent()
0x2f1e0  ldarg.0
0x2f1e1  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f1e6  callvirt instance void [System.Web]System.Web.HttpResponse::ClearHeaders()
0x2f1eb  ldarg.0
0x2f1ec  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f1f1  ldstr    aTextHtml// "text/html"
0x2f1f6  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x2f1fb  ldarg.0
0x2f1fc  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f201  ldloc.s  0xE
0x2f203  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.IO.StringWriter::GetStringBuilder()
0x2f208  ldstr    aHtml// "</html>"
0x2f20d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2f212  ldc.i4.0
0x2f213  ldloc.s  0x14
0x2f215  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Insert(int32, string)
0x2f21a  callvirt instance string [mscorlib]System.Object::ToString()
0x2f21f  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2f224  ldarg.0
0x2f225  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
  ... truncated ...
```
