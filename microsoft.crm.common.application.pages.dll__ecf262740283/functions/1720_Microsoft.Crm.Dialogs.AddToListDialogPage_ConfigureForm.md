# Microsoft.Crm.Dialogs.AddToListDialogPage::ConfigureForm

- ea: `0x1720`
- end: `0x1c7a`
- name: `Microsoft.Crm.Dialogs.AddToListDialogPage::ConfigureForm`
- size: `1370`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1720`
- `0x1c80`

## string_xrefs

- `0x188e`: `processXml`
- `0x1997`: `XML loaded from the stream returned String.Empty.`
- `0x19a1`: `XML loaded from the stream returned String.Empty.`

## pseudocode

```c

```

## disassembly

```asm
0x1720  ldarg.0
0x1721  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1726  ldarg.0
0x1727  ldnull
0x1728  ldstr    aChecknullHealt// "CheckNull Health Check OK - Ignore this"...
0x172d  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1732  ldarg.0
0x1733  ldarg.0
0x1734  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1739  ldstr    aRequest1// "Request 1"
0x173e  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1743  ldarg.0
0x1744  ldarg.0
0x1745  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x174a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x174f  ldstr    aRequestQueryst// "Request.QueryString 1"
0x1754  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1759  ldarg.0
0x175a  ldarg.0
0x175b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1760  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1765  ldstr    aItotal// "iTotal"
0x176a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x176f  ldstr    aRequestQueryst_0// "Request.QueryString[\"iTotal\"]"
0x1774  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1779  ldarg.0
0x177a  ldarg.0
0x177b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1780  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1785  ldstr    aIobjtype// "iObjType"
0x178a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x178f  ldstr    aRequestQueryst_1// "Request.QueryString[\"iObjType\"]"
0x1794  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1799  ldarg.0
0x179a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x179f  ldstr    aCultureinfoInv// "CultureInfo.InvariantCulture"
0x17a4  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x17a9  ldarg.0
0x17aa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17af  ldstr    aUserinformatio// "UserInformation.Current 1"
0x17b4  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x17b9  ldarg.0
0x17ba  ldarg.0
0x17bb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17c0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17c5  ldstr    aItotal// "iTotal"
0x17ca  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17cf  ldc.i4.7
0x17d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17d5  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x17da  stfld    int32 Microsoft.Crm.Dialogs.AddToListDialogPage::Total
0x17df  ldarg.0
0x17e0  ldarg.0
0x17e1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17e6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17eb  ldstr    aIobjtype// "iObjType"
0x17f0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17f5  ldc.i4.7
0x17f6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17fb  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1800  stfld    int32 Microsoft.Crm.Dialogs.AddToListDialogPage::ObjType
0x1805  ldarg.0
0x1806  ldfld    int32 Microsoft.Crm.Dialogs.AddToListDialogPage::Total
0x180b  ldc.i4.1
0x180c  beq.s    loc_1822
0x180e  ldarg.0
0x180f  ldarg.0
0x1810  ldfld    int32 Microsoft.Crm.Dialogs.AddToListDialogPage::ObjType
0x1815  ldc.i4.2
0x1816  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x181b  stfld    string Microsoft.Crm.Dialogs.AddToListDialogPage::ObjName
0x1820  br.s     loc_1834
0x1822  ldarg.0
0x1823  ldarg.0
0x1824  ldfld    int32 Microsoft.Crm.Dialogs.AddToListDialogPage::ObjType
0x1829  ldc.i4.1
0x182a  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x182f  stfld    string Microsoft.Crm.Dialogs.AddToListDialogPage::ObjName
0x1834  ldarg.0
0x1835  ldarg.0
0x1836  ldfld    string Microsoft.Crm.Dialogs.AddToListDialogPage::ObjName
0x183b  ldstr    aObjname// "ObjName"
0x1840  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1845  ldarg.0
0x1846  ldarg.0
0x1847  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x184c  ldstr    aRequest2// "Request 2"
0x1851  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1856  ldarg.0
0x1857  ldarg.0
0x1858  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x185d  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1862  ldstr    aRequestInputst// "Request.InputStream"
0x1867  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x186c  ldarg.0
0x186d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1872  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1877  stloc.0
0x1878  ldloc.0
0x1879  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x187e  ldc.i4.0
0x187f  conv.i8
0x1880  ble      loc_19B9
0x1885  ldloc.0
0x1886  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x188b  stloc.2
0x188c  ldarg.0
0x188d  ldloc.2
0x188e  ldstr    aProcessxml// "processXml"
0x1893  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1898  ldloc.2
0x1899  callvirt instance int32 [mscorlib]System.String::get_Length()
0x189e  brfalse  loc_198E
0x18a3  ldarg.0
0x18a4  ldarg.0
0x18a5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18aa  ldstr    aRequest3// "Request 3"
0x18af  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x18b4  ldarg.0
0x18b5  ldarg.0
0x18b6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18bb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18c0  ldstr    aRequestQueryst_2// "Request.QueryString 3"
0x18c5  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x18ca  ldarg.0
0x18cb  ldarg.0
0x18cc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18d1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18d6  ldstr    aIid// "iId"
0x18db  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18e0  ldstr    aRequestQueryst_3// "Request.QueryString[\"iId\"]"
0x18e5  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x18ea  ldarg.0
0x18eb  ldarg.0
0x18ec  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18f1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x18f6  ldstr    aItemobjectid// "itemObjectId"
0x18fb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1900  ldstr    aRequestQueryst_4// "Request.QueryString[\"itemObjectId\"]"
0x1905  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x190a  ldarg.0
0x190b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1910  ldstr    aUserinformatio_0// "UserInformation.Current 3"
0x1915  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x191a  ldarg.0
0x191b  ldarg.0
0x191c  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1921  ldstr    aPage// "Page"
0x1926  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x192b  ldarg.0
0x192c  ldarg.0
0x192d  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1932  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1937  ldstr    aPageResponse// "Page.Response"
0x193c  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1941  ldarg.0
0x1942  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1947  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x194c  ldstr    aIid// "iId"
0x1951  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1956  stloc.3
0x1957  ldarg.0
0x1958  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x195d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1962  ldstr    aItemobjectid// "itemObjectId"
0x1967  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x196c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1971  ldloc.3
0x1972  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1977  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x197c  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddMemberList(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1981  ldarg.0
0x1982  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1987  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x198c  br.s     loc_19B1
0x198e  ldloc.2
0x198f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1994  ldc.i4.0
0x1995  cgt.un
0x1997  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x199c  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x19a1  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x19a6  ldc.i4   0x80049002
0x19ab  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19b0  throw
0x19b1  leave.s  loc_19B9
0x19b3  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x19b8  throw
0x19b9  ldarg.0
0x19ba  ldarg.0
0x19bb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19c0  ldstr    aRequest4// "Request 4"
0x19c5  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x19ca  ldarg.0
0x19cb  ldarg.0
0x19cc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19d1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x19d6  ldstr    aRequestQueryst_5// "Request.QueryString 4"
0x19db  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x19e0  ldarg.0
0x19e1  ldarg.0
0x19e2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19e7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x19ec  ldstr    aAutotrigger// "autoTrigger"
0x19f1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19f6  ldstr    aRequestQueryst_6// "Request.QueryString[\"autoTrigger\"]"
0x19fb  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1a00  ldarg.0
0x1a01  ldarg.0
0x1a02  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1a07  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1a0c  ldstr    aConfirmmode// "confirmMode"
0x1a11  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a16  ldstr    aRequestQueryst_7// "Request.QueryString[\"confirmMode\"]"
0x1a1b  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1a20  ldarg.0
0x1a21  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1a26  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1a2b  ldstr    aAutotrigger// "autoTrigger"
0x1a30  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a35  dup
0x1a36  ldstr    a1// "1"
0x1a3b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a40  brfalse.s loc_1A4D
0x1a42  ldarg.0
0x1a43  ldstr    aApplychanges// "applychanges();"
0x1a48  stfld    string Microsoft.Crm.Dialogs.AddToListDialogPage::autoTrigger
0x1a4d  ldarg.0
0x1a4e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1a53  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1a58  ldstr    aConfirmmode// "confirmMode"
0x1a5d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a62  ldstr    a1// "1"
0x1a67  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a6c  brfalse.s loc_1A84
0x1a6e  ldarg.0
0x1a6f  ldstr    aConfirmmodeTru// "confirmMode(true)"
0x1a74  stfld    string Microsoft.Crm.Dialogs.AddToListDialogPage::dialogActionOk
0x1a79  ldarg.0
0x1a7a  ldstr    aConfirmmodeFal// "confirmMode(false)"
0x1a7f  stfld    string Microsoft.Crm.Dialogs.AddToListDialogPage::dialogActionCancel
0x1a84  ldarg.0
0x1a85  ldarg.0
0x1a86  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1a8b  ldstr    aCurrentheader// "CurrentHeader"
0x1a90  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1a95  ldarg.0
0x1a96  ldarg.0
0x1a97  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1a9c  ldstr    aCurrentresourc// "CurrentResourceManager"
0x1aa1  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1aa6  ldarg.0
0x1aa7  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1aac  ldstr    aCrmcultureinfo// "CrmCultureInfo.CurrentCulture"
0x1ab1  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1ab6  ldstr    a1// "1"
0x1abb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ac0  brfalse  loc_1B4A
0x1ac5  ldarg.0
0x1ac6  ldarg.0
0x1ac7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1acc  ldstr    aDialogAddtolis// "Dialog_AddToList_Title"
0x1ad1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ad6  ldstr    aCurrentresourc_0// "CurrentResourceManager.GetString(\"Dial"...
0x1adb  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1ae0  ldarg.0
0x1ae1  ldarg.0
0x1ae2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1ae7  ldstr    aDialogAddtolis_0// "Dialog_AddToList_Header"
0x1aec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1af1  ldstr    aCurrentresourc_1// "CurrentResourceManager.GetString(\"Dial"...
0x1af6  call     instance void Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull(object value, string name)
0x1afb  ldarg.0
0x1afc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1b01  ldarg.0
0x1b02  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b07  ldstr    aDialogAddtolis// "Dialog_AddToList_Title"
0x1b0c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x1b16  ldarg.0
0x1b17  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1b1c  ldarg.0
0x1b1d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b22  ldstr    aDialogAddtolis_0// "Dialog_AddToList_Header"
0x1b27  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b2c  ldc.i4.1
0x1b2d  newarr   [mscorlib]System.Object
0x1b32  dup
0x1b33  ldc.i4.0
0x1b34  ldarg.0
0x1b35  ldfld    string Microsoft.Crm.Dialogs.AddToListDialogPage::ObjName
0x1b3a  stelem.ref
0x1b3b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b40  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x1b45  br       loc_1BCA
0x1b4a  ldarg.0
0x1b4b  ldarg.0
0x1b4c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b51  ldstr    aDialogAddtolis_1// "Dialog_AddToListConfirm_Title"
0x1b56  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
  ... truncated ...
```
