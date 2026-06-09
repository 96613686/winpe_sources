# Microsoft.Crm.Dialogs.ConvertLeadDialogPage::ConfigureForm

- ea: `0x33b0`
- end: `0x367f`
- name: `Microsoft.Crm.Dialogs.ConvertLeadDialogPage::ConfigureForm`
- size: `719`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x33b0`
- `0x3680`
- `0x36d0`

## string_xrefs

- `0x35ad`: `XML loaded from the stream returned String.Empty.`
- `0x35b7`: `XML loaded from the stream returned String.Empty.`
- `0x354d`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x33b0  ldarg.0
0x33b1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x33b6  ldarg.0
0x33b7  ldarg.0
0x33b8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x33bd  ldstr    aDialogConvertl// "Dialog_ConvertLead_ActionStringConvertL"...
0x33c2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x33c7  stfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::actionString
0x33cc  ldarg.0
0x33cd  ldarg.0
0x33ce  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x33d3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x33d8  ldstr    aItotal// "iTotal"
0x33dd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x33e2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x33e7  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x33ec  stfld    int32 Microsoft.Crm.Dialogs.ConvertLeadDialogPage::Total
0x33f1  ldarg.0
0x33f2  ldarg.0
0x33f3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x33f8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x33fd  ldstr    aIobjtype// "iObjType"
0x3402  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3407  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x340c  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3411  stfld    int32 Microsoft.Crm.Dialogs.ConvertLeadDialogPage::ObjType
0x3416  ldarg.0
0x3417  ldarg.0
0x3418  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x341d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3422  ldstr    aQlshownew// "qlShowNew"
0x3427  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x342c  stfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::qualifyShowNew
0x3431  ldarg.0
0x3432  ldarg.0
0x3433  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3438  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x343d  ldstr    aUlnewstatus// "ulNewStatus"
0x3442  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3447  stfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::ulNewStatus
0x344c  ldarg.0
0x344d  ldarg.0
0x344e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3453  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3458  ldstr    aQualify// "qualify"
0x345d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3462  stfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::qualify
0x3467  ldarg.0
0x3468  ldfld    int32 Microsoft.Crm.Dialogs.ConvertLeadDialogPage::Total
0x346d  ldc.i4.1
0x346e  beq.s    loc_3484
0x3470  ldarg.0
0x3471  ldarg.0
0x3472  ldfld    int32 Microsoft.Crm.Dialogs.ConvertLeadDialogPage::ObjType
0x3477  ldc.i4.2
0x3478  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x347d  stfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::ObjName
0x3482  br.s     loc_3496
0x3484  ldarg.0
0x3485  ldarg.0
0x3486  ldfld    int32 Microsoft.Crm.Dialogs.ConvertLeadDialogPage::ObjType
0x348b  ldc.i4.1
0x348c  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x3491  stfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::ObjName
0x3496  ldarg.0
0x3497  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x349c  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x34a1  stloc.0
0x34a2  ldloc.0
0x34a3  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x34a8  ldc.i4.0
0x34a9  conv.i8
0x34aa  ble      loc_35CF
0x34af  ldloc.0
0x34b0  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x34b5  stloc.2
0x34b6  ldloc.2
0x34b7  brfalse  loc_35AC
0x34bc  ldloc.2
0x34bd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x34c2  brfalse  loc_35AC
0x34c7  ldarg.0
0x34c8  ldarg.0
0x34c9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x34ce  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x34d3  ldstr    aIid// "iId"
0x34d8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x34dd  stfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::leadId
0x34e2  ldnull
0x34e3  stloc.3
0x34e4  ldarg.0
0x34e5  ldfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::ulNewStatus
0x34ea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x34ef  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x34f4  stloc.s  4
0x34f6  ldarg.0
0x34f7  ldfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::qualify
0x34fc  ldstr    aTrue// "true"
0x3501  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3506  brfalse.s loc_3522
0x3508  ldarg.0
0x3509  ldfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::qualifyShowNew
0x350e  call     bool [mscorlib]System.Boolean::Parse(string)
0x3513  stloc.s  5
0x3515  ldarg.0
0x3516  ldloc.s  4
0x3518  ldloc.s  5
0x351a  call     instance string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::QualifyLead(int32 newStatus, bool showNew)
0x351f  stloc.3
0x3520  br.s     loc_353C
0x3522  ldarg.0
0x3523  ldfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::qualify
0x3528  ldstr    aFalse// "false"
0x352d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3532  brfalse.s loc_353C
0x3534  ldarg.0
0x3535  ldloc.s  4
0x3537  call     instance void Microsoft.Crm.Dialogs.ConvertLeadDialogPage::DisqualifyLead(int32 newStatus)
0x353c  ldarg.0
0x353d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x3542  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x3547  ldarg.0
0x3548  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x354d  ldstr    aTextXml// "text/xml"
0x3552  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x3557  ldarg.0
0x3558  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x355d  ldstr    aOk_0// "<ok>"
0x3562  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x3567  ldloc.3
0x3568  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x356d  brtrue.s loc_358F
0x356f  ldarg.0
0x3570  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x3575  ldstr    aShownew// "<ShowNew>"
0x357a  ldloc.3
0x357b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x3580  ldstr    aShownew_0// "</ShowNew>"
0x3585  call     string [mscorlib]System.String::Concat(string, string, string)
0x358a  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x358f  ldarg.0
0x3590  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x3595  ldstr    aOk_1// "</ok>"
0x359a  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x359f  ldarg.0
0x35a0  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x35a5  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x35aa  br.s     loc_35C7
0x35ac  ldc.i4.0
0x35ad  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x35b2  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x35b7  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x35bc  ldc.i4   0x80049002
0x35c1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x35c6  throw
0x35c7  leave.s  loc_35CF
0x35c9  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x35ce  throw
0x35cf  ldarg.0
0x35d0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x35d5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x35da  ldstr    aConfirmmode// "confirmMode"
0x35df  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x35e4  ldstr    a1// "1"
0x35e9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x35ee  brfalse.s loc_3606
0x35f0  ldarg.0
0x35f1  ldstr    aConfirmmodeTru// "confirmMode(true)"
0x35f6  stfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::dialogActionOk
0x35fb  ldarg.0
0x35fc  ldstr    aConfirmmodeFal// "confirmMode(false)"
0x3601  stfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::dialogActionCancel
0x3606  ldarg.0
0x3607  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x360c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x3611  stloc.1
0x3612  ldloc.1
0x3613  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x3618  ldarg.0
0x3619  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x361e  ldstr    aDialogConvertl_0// "Dialog_ConvertLead_Title"
0x3623  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3628  ldc.i4.1
0x3629  newarr   [mscorlib]System.Object
0x362e  dup
0x362f  ldc.i4.0
0x3630  ldarg.0
0x3631  ldfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::ObjName
0x3636  stelem.ref
0x3637  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x363c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x3641  ldloc.1
0x3642  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x3647  ldarg.0
0x3648  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x364d  ldstr    aDialogConvertl_1// "Dialog_ConvertLead_Description"
0x3652  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3657  ldc.i4.2
0x3658  newarr   [mscorlib]System.Object
0x365d  dup
0x365e  ldc.i4.0
0x365f  ldarg.0
0x3660  ldfld    int32 Microsoft.Crm.Dialogs.ConvertLeadDialogPage::Total
0x3665  box      [mscorlib]System.Int32
0x366a  stelem.ref
0x366b  dup
0x366c  ldc.i4.1
0x366d  ldarg.0
0x366e  ldfld    string Microsoft.Crm.Dialogs.ConvertLeadDialogPage::ObjName
0x3673  stelem.ref
0x3674  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3679  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x367e  ret
```
