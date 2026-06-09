# Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::ConfigureForm

- ea: `0x20d0`
- end: `0x2489`
- name: `Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::ConfigureForm`
- size: `953`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x20d0`

## string_xrefs

- `0x2297`: `XML loaded from the stream returned String.Empty.`
- `0x22a1`: `XML loaded from the stream returned String.Empty.`
- `0x225c`: `text/xml`
- `0x21f2`: `emailrouteraccessapproval`

## pseudocode

```c

```

## disassembly

```asm
0x20d0  ldarg.0
0x20d1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x20d6  ldarg.0
0x20d7  ldarg.0
0x20d8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x20dd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x20e2  ldstr    aItotal// "iTotal"
0x20e7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x20ec  ldc.i4.7
0x20ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20f2  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x20f7  stfld    int32 Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::Total
0x20fc  ldarg.0
0x20fd  ldarg.0
0x20fe  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2103  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2108  ldstr    aIobjtype// "iObjType"
0x210d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2112  ldc.i4.7
0x2113  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2118  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x211d  stfld    int32 Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::ObjType
0x2122  ldarg.0
0x2123  ldc.i4.1
0x2124  ldarg.0
0x2125  ldfld    int32 Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::Total
0x212a  beq.s    loc_213A
0x212c  ldarg.0
0x212d  ldfld    int32 Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::ObjType
0x2132  ldc.i4.2
0x2133  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x2138  br.s     loc_2146
0x213a  ldarg.0
0x213b  ldfld    int32 Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::ObjType
0x2140  ldc.i4.1
0x2141  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x2146  stfld    string Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::ObjName
0x214b  ldarg.0
0x214c  ldarg.0
0x214d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2152  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2157  ldstr    aCustomaction// "customAction"
0x215c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2161  stfld    string Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::CustomAction
0x2166  ldc.i4.1
0x2167  stloc.0
0x2168  ldarg.0
0x2169  ldfld    string Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::CustomAction
0x216e  ldstr    aApproveemail// "approveemail"
0x2173  ldc.i4.5
0x2174  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2179  brfalse.s loc_217F
0x217b  ldc.i4.1
0x217c  stloc.0
0x217d  br.s     loc_2181
0x217f  ldc.i4.0
0x2180  stloc.0
0x2181  ldarg.0
0x2182  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2187  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x218c  stloc.2
0x218d  ldloc.2
0x218e  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x2193  ldc.i4.0
0x2194  conv.i8
0x2195  ble      loc_22B9
0x219a  ldloc.2
0x219b  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x21a0  stloc.3
0x21a1  ldloc.3
0x21a2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x21a7  brfalse  loc_228E
0x21ac  ldarg.0
0x21ad  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x21b2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x21b7  ldstr    aIid// "iId"
0x21bc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x21c1  stloc.s  4
0x21c3  ldarg.0
0x21c4  ldfld    int32 Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::ObjType
0x21c9  stloc.s  5
0x21cb  ldloc.s  5
0x21cd  ldc.i4.8
0x21ce  beq.s    loc_221C
0x21d0  ldloc.s  5
0x21d2  ldc.i4   0x7E4
0x21d7  beq.s    loc_223A
0x21d9  ldloc.s  5
0x21db  ldc.i4   0x2586
0x21e0  bne.un.s loc_2256
0x21e2  ldstr    aMailbox// "mailbox"
0x21e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21f1  dup
0x21f2  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x21f7  ldloc.0
0x21f8  brtrue.s loc_21FD
0x21fa  ldc.i4.3
0x21fb  br.s     loc_21FE
0x21fd  ldc.i4.1
0x21fe  box      [mscorlib]System.Int32
0x2203  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2208  dup
0x2209  ldloc.s  4
0x220b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x2210  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2215  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x221a  br.s     loc_2256
0x221c  ldstr    aSystemuser// "systemuser"
0x2221  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2226  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x222b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SystemUser::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x2230  ldloc.s  4
0x2232  ldloc.0
0x2233  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SystemUser::ApproveOrReject(string, bool)
0x2238  br.s     loc_2256
0x223a  ldstr    aQueue// "queue"
0x223f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2244  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2249  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Queue::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x224e  ldloc.s  4
0x2250  ldloc.0
0x2251  callvirt instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Queue::ApproveOrReject(string, bool)
0x2256  ldarg.0
0x2257  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x225c  ldstr    aTextXml// "text/xml"
0x2261  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x2266  ldarg.0
0x2267  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x226c  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x2271  ldarg.0
0x2272  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2277  ldstr    aOk// "<ok/>"
0x227c  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2281  ldarg.0
0x2282  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2287  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x228c  br.s     loc_22B1
0x228e  ldloc.3
0x228f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2294  ldc.i4.0
0x2295  cgt.un
0x2297  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x229c  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x22a1  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x22a6  ldc.i4   0x80049002
0x22ab  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22b0  throw
0x22b1  leave.s  loc_22C5
0x22b3  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x22b8  throw
0x22b9  leave.s  loc_22C5
0x22bb  ldloc.2
0x22bc  brfalse.s loc_22C4
0x22be  ldloc.2
0x22bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22c4  endfinally
0x22c5  ldarg.0
0x22c6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x22cb  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x22d0  stloc.1
0x22d1  ldloc.0
0x22d2  brfalse  loc_2392
0x22d7  ldarg.0
0x22d8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::dialogTitle
0x22dd  ldstr    aWebGridCmdsDlg_0// "Web._grid.cmds.dlg_approve_title"
0x22e2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x22e7  ldloc.1
0x22e8  ldarg.0
0x22e9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x22ee  ldstr    aDialogApprovee// "Dialog_ApproveEmail_Title"
0x22f3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22f8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x22fd  ldloc.1
0x22fe  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x2303  ldarg.0
0x2304  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2309  ldstr    aDialogApprovee_0// "Dialog_ApproveEmail_Description"
0x230e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2313  ldc.i4.2
0x2314  newarr   [mscorlib]System.Object
0x2319  dup
0x231a  ldc.i4.0
0x231b  ldarg.0
0x231c  ldfld    int32 Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::Total
0x2321  box      [mscorlib]System.Int32
0x2326  stelem.ref
0x2327  dup
0x2328  ldc.i4.1
0x2329  ldarg.0
0x232a  ldfld    string Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::ObjName
0x232f  stelem.ref
0x2330  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2335  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x233a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x233f  ldstr    aUAHref0TargetB// "<u><a href=\"{0}\" target=\"_blank\">"
0x2344  ldc.i4.1
0x2345  newarr   [mscorlib]System.Object
0x234a  dup
0x234b  ldc.i4.0
0x234c  call     class [System]System.Uri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrievePrivacyLinkUrlAboutPage()
0x2351  stelem.ref
0x2352  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2357  stloc.s  6
0x2359  ldarg.0
0x235a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x235f  ldarg.0
0x2360  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2365  ldstr    aWebDlgApproveE// "Web.dlg_approve_emailaddress.PrivacyDis"...
0x236a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x236f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x2374  ldc.i4.2
0x2375  newarr   [mscorlib]System.Object
0x237a  dup
0x237b  ldc.i4.0
0x237c  ldloc.s  6
0x237e  stelem.ref
0x237f  dup
0x2380  ldc.i4.1
0x2381  ldstr    aAU// "</a></u>"
0x2386  stelem.ref
0x2387  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x238c  stfld    string Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::disclaimerText
0x2391  ret
0x2392  ldarg.0
0x2393  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::dialogTitle
0x2398  ldstr    aWebGridCmdsDlg_1// "Web._grid.cmds.dlg_reject_title"
0x239d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x23a2  ldloc.1
0x23a3  ldarg.0
0x23a4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23a9  ldstr    aDialogRejectem// "Dialog_RejectEmail_Title"
0x23ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23b3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x23b8  ldloc.1
0x23b9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x23be  ldarg.0
0x23bf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23c4  ldstr    aDialogRejectem_0// "Dialog_RejectEmail_Description"
0x23c9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23ce  ldc.i4.2
0x23cf  newarr   [mscorlib]System.Object
0x23d4  dup
0x23d5  ldc.i4.0
0x23d6  ldarg.0
0x23d7  ldfld    int32 Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::Total
0x23dc  box      [mscorlib]System.Int32
0x23e1  stelem.ref
0x23e2  dup
0x23e3  ldc.i4.1
0x23e4  ldarg.0
0x23e5  ldfld    string Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::ObjName
0x23ea  stelem.ref
0x23eb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x23f0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x23f5  ldarg.0
0x23f6  ldfld    int32 Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::ObjType
0x23fb  stloc.s  5
0x23fd  ldloc.s  5
0x23ff  ldc.i4.8
0x2400  beq.s    loc_243B
0x2402  ldloc.s  5
0x2404  ldc.i4   0x7E4
0x2409  beq.s    loc_2462
0x240b  ldloc.s  5
0x240d  ldc.i4   0x2586
0x2412  bne.un.s loc_2488
0x2414  ldarg.0
0x2415  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x241a  ldarg.0
0x241b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2420  ldstr    aWebGridCmdsDlg_2// "Web._grid.cmds.dlg_reject_mailbox.aspx_"...
0x2425  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x242a  ldc.i4.0
0x242b  newarr   [mscorlib]System.Object
0x2430  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2435  stfld    string Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::dialogBody
0x243a  ret
0x243b  ldarg.0
0x243c  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x2441  ldarg.0
0x2442  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2447  ldstr    aWebGridCmdsDlg_3// "Web._grid.cmds.dlg_reject_user.aspx_tex"...
0x244c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2451  ldc.i4.0
0x2452  newarr   [mscorlib]System.Object
0x2457  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x245c  stfld    string Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::dialogBody
0x2461  ret
0x2462  ldarg.0
0x2463  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x2468  ldarg.0
0x2469  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x246e  ldstr    aWebGridCmdsDlg_4// "Web._grid.cmds.dlg_reject_queue.aspx_te"...
0x2473  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2478  ldc.i4.0
0x2479  newarr   [mscorlib]System.Object
0x247e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2483  stfld    string Microsoft.Crm.Dialogs.ApproveEmailAddressDialogPage::dialogBody
0x2488  ret
  ... truncated ...
```
