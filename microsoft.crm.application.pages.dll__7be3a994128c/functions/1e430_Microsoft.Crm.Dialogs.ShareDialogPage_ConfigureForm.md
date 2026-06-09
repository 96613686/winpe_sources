# Microsoft.Crm.Dialogs.ShareDialogPage::ConfigureForm

- ea: `0x1e430`
- end: `0x1eb95`
- name: `Microsoft.Crm.Dialogs.ShareDialogPage::ConfigureForm`
- size: `1893`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1e410`
- `0x1e430`
- `0x1eba0`
- `0x1ebe0`
- `0x1ecd0`

## string_xrefs

- `0x1e6c0`: `text/xml`
- `0x1e9f7`: `XML loaded from the stream returned String.Empty.`
- `0x1ea01`: `XML loaded from the stream returned String.Empty.`
- `0x1e89d`: `accessrights`
- `0x1eacc`: `Dialog_Share_TaskBox_Add`
- `0x1eae6`: `Dialog_Share_TaskBox_Add_ToolTip`
- `0x1eb01`: `Dialog_Share_TaskBox_Remove`
- `0x1eb0b`: `<img alt='' src='/_imgs/ico/16_l_remove.gif'>`
- `0x1eb10`: `RemoveUsersFromShare()`
- `0x1eb1b`: `Dialog_Share_TaskBox_Remove_ToolTip`
- `0x1eb36`: `Dialog_Share_TaskBox_Toggle`
- `0x1eb50`: `Dialog_Share_TaskBox_Toggle_ToolTip`
- `0x1eb6b`: `Dialog_Share_TaskBox_Reset`
- `0x1eb85`: `Dialog_Share_TaskBox_Reset_ToolTip`

## pseudocode

```c

```

## disassembly

```asm
0x1e430  ldarg.0
0x1e431  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1e436  ldarg.0
0x1e437  ldarg.0
0x1e438  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1e43d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1e442  ldstr    aItotal// "iTotal"
0x1e447  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1e44c  call     instance void Microsoft.Crm.Dialogs.ShareDialogPage::set_Total(string value)
0x1e451  ldarg.0
0x1e452  ldarg.0
0x1e453  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1e458  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1e45d  ldstr    aIobjtype// "iObjType"
0x1e462  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1e467  ldc.i4.7
0x1e468  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e46d  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1e472  stfld    int32 Microsoft.Crm.Dialogs.ShareDialogPage::ObjType
0x1e477  ldarg.0
0x1e478  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1e47d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1e482  stloc.0
0x1e483  ldloc.0
0x1e484  ldc.i4   0x28A
0x1e489  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_Width(int32)
0x1e48e  ldloc.0
0x1e48f  ldc.i4   0x1E0
0x1e494  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_Height(int32)
0x1e499  ldloc.0
0x1e49a  ldc.i4.0
0x1e49b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x1e4a0  ldloc.0
0x1e4a1  ldc.i4.1
0x1e4a2  ldstr    aWebGridCmdsDlg_99// "Web._grid.cmds.dlg_share.aspx_454"
0x1e4a7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x1e4ac  ldloc.0
0x1e4ad  ldc.i4.2
0x1e4ae  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x1e4b3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x1e4b8  ldarg.0
0x1e4b9  ldarg.0
0x1e4ba  ldfld    int32 Microsoft.Crm.Dialogs.ShareDialogPage::ObjType
0x1e4bf  ldc.i4.1
0x1e4c0  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1e4c5  stfld    string Microsoft.Crm.Dialogs.ShareDialogPage::ObjName
0x1e4ca  ldarg.0
0x1e4cb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1e4d0  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1e4d5  stloc.1
0x1e4d6  ldloc.1
0x1e4d7  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1e4dc  ldc.i4.0
0x1e4dd  conv.i8
0x1e4de  ble      loc_1EA19
0x1e4e3  ldloc.1
0x1e4e4  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x1e4e9  stloc.s  6
0x1e4eb  ldloc.s  6
0x1e4ed  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1e4f2  brfalse  loc_1E9ED
0x1e4f7  ldarg.0
0x1e4f8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1e4fd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1e502  ldstr    aAction// "action"
0x1e507  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1e50c  ldstr    aRetrieve// "retrieve"
0x1e511  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e516  brfalse  loc_1E810
0x1e51b  ldarg.0
0x1e51c  ldloc.s  6
0x1e51e  ldstr    aIds// "ids"
0x1e523  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x1e528  stfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e52d  ldarg.0
0x1e52e  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e533  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1e538  ldc.i4.2
0x1e539  ble      loc_1E5F5
0x1e53e  ldarg.0
0x1e53f  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e544  ldarg.0
0x1e545  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e54a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1e54f  ldc.i4.1
0x1e550  sub
0x1e551  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1e556  ldc.i4.s 0x3B
0x1e558  bne.un.s loc_1E579
0x1e55a  ldarg.0
0x1e55b  ldarg.0
0x1e55c  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e561  ldc.i4.0
0x1e562  ldarg.0
0x1e563  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e568  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1e56d  ldc.i4.1
0x1e56e  sub
0x1e56f  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1e574  stfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e579  ldarg.0
0x1e57a  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e57f  ldc.i4.1
0x1e580  newarr   [mscorlib]System.Char
0x1e585  dup
0x1e586  ldc.i4.0
0x1e587  ldc.i4.s 0x3B
0x1e589  stelem.i2
0x1e58a  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1e58f  stloc.s  7
0x1e591  ldc.i4.0
0x1e592  stloc.s  8
0x1e594  br.s     loc_1E5D0
0x1e596  ldarg.0
0x1e597  ldarg.0
0x1e598  ldarg.0
0x1e599  ldfld    int32 Microsoft.Crm.Dialogs.ShareDialogPage::ObjType
0x1e59e  ldloc.s  7
0x1e5a0  ldloc.s  8
0x1e5a2  ldelem.ref
0x1e5a3  call     instance string Microsoft.Crm.Dialogs.ShareDialogPage::GetAccessCheck(int32 objectType, string id)
0x1e5a8  call     instance bool Microsoft.Crm.Dialogs.ShareDialogPage::SetUserRights(string rightXml)
0x1e5ad  brtrue.s loc_1E5CA
0x1e5af  ldarg.0
0x1e5b0  ldarg.0
0x1e5b1  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e5b6  ldloc.s  7
0x1e5b8  ldloc.s  8
0x1e5ba  ldelem.ref
0x1e5bb  ldsfld   string [mscorlib]System.String::Empty
0x1e5c0  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1e5c5  stfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e5ca  ldloc.s  8
0x1e5cc  ldc.i4.1
0x1e5cd  add
0x1e5ce  stloc.s  8
0x1e5d0  ldloc.s  8
0x1e5d2  ldloc.s  7
0x1e5d4  ldlen
0x1e5d5  conv.i4
0x1e5d6  blt.s    loc_1E596
0x1e5d8  br.s     loc_1E5F5
0x1e5da  ldarg.0
0x1e5db  ldarg.0
0x1e5dc  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e5e1  ldstr    asc_12F882// ";;"
0x1e5e6  ldstr    asc_113A60// ";"
0x1e5eb  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1e5f0  stfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e5f5  ldarg.0
0x1e5f6  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e5fb  ldstr    asc_12F882// ";;"
0x1e600  ldc.i4.4
0x1e601  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1e606  ldc.i4.0
0x1e607  bge.s    loc_1E5DA
0x1e609  ldarg.0
0x1e60a  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e60f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1e614  brfalse.s loc_1E638
0x1e616  ldarg.0
0x1e617  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e61c  ldc.i4.0
0x1e61d  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1e622  ldc.i4.s 0x3B
0x1e624  bne.un.s loc_1E638
0x1e626  ldarg.0
0x1e627  ldarg.0
0x1e628  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e62d  ldc.i4.1
0x1e62e  callvirt instance string [mscorlib]System.String::Substring(int32)
0x1e633  stfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e638  ldarg.0
0x1e639  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e63e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1e643  brfalse.s loc_1E680
0x1e645  ldarg.0
0x1e646  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e64b  ldarg.0
0x1e64c  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e651  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1e656  ldc.i4.1
0x1e657  sub
0x1e658  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1e65d  ldc.i4.s 0x3B
0x1e65f  bne.un.s loc_1E680
0x1e661  ldarg.0
0x1e662  ldarg.0
0x1e663  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e668  ldc.i4.0
0x1e669  ldarg.0
0x1e66a  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e66f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1e674  ldc.i4.1
0x1e675  sub
0x1e676  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1e67b  stfld    string Microsoft.Crm.Dialogs.ShareDialogPage::sIds
0x1e680  ldarg.0
0x1e681  ldarg.0
0x1e682  ldflda   int32 Microsoft.Crm.Dialogs.ShareDialogPage::PermittedCount
0x1e687  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e68c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1e691  call     instance void Microsoft.Crm.Dialogs.ShareDialogPage::set_Total(string value)
0x1e696  ldarg.0
0x1e697  ldfld    string Microsoft.Crm.Dialogs.ShareDialogPage::ShareAny
0x1e69c  ldstr    a1// "1"
0x1e6a1  ldc.i4.4
0x1e6a2  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1e6a7  ldc.i4.0
0x1e6a8  blt.s    loc_1E6B3
0x1e6aa  ldarg.0
0x1e6ab  ldc.i4.1
0x1e6ac  stfld    bool Microsoft.Crm.Dialogs.ShareDialogPage::Share
0x1e6b1  br.s     loc_1E6BA
0x1e6b3  ldarg.0
0x1e6b4  ldc.i4.0
0x1e6b5  stfld    bool Microsoft.Crm.Dialogs.ShareDialogPage::Share
0x1e6ba  ldarg.0
0x1e6bb  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e6c0  ldstr    aTextXml// "text/xml"
0x1e6c5  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1e6ca  ldarg.0
0x1e6cb  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e6d0  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1e6d5  ldarg.0
0x1e6d6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e6db  ldstr    aRightsMask// "<rights><mask>"
0x1e6e0  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1e6e5  ldarg.0
0x1e6e6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e6eb  ldarg.0
0x1e6ec  ldfld    bool Microsoft.Crm.Dialogs.ShareDialogPage::Read
0x1e6f1  brtrue.s loc_1E6FA
0x1e6f3  ldstr    a0_1// "0"
0x1e6f8  br.s     loc_1E6FF
0x1e6fa  ldstr    a1// "1"
0x1e6ff  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1e704  ldarg.0
0x1e705  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e70a  ldarg.0
0x1e70b  ldfld    bool Microsoft.Crm.Dialogs.ShareDialogPage::Write
0x1e710  brtrue.s loc_1E719
0x1e712  ldstr    a0_1// "0"
0x1e717  br.s     loc_1E71E
0x1e719  ldstr    a1// "1"
0x1e71e  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1e723  ldarg.0
0x1e724  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e729  ldarg.0
0x1e72a  ldfld    bool Microsoft.Crm.Dialogs.ShareDialogPage::Delete
0x1e72f  brtrue.s loc_1E738
0x1e731  ldstr    a0_1// "0"
0x1e736  br.s     loc_1E73D
0x1e738  ldstr    a1// "1"
0x1e73d  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1e742  ldarg.0
0x1e743  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e748  ldarg.0
0x1e749  ldfld    bool Microsoft.Crm.Dialogs.ShareDialogPage::Append
0x1e74e  brtrue.s loc_1E757
0x1e750  ldstr    a0_1// "0"
0x1e755  br.s     loc_1E75C
0x1e757  ldstr    a1// "1"
0x1e75c  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1e761  ldarg.0
0x1e762  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e767  ldarg.0
0x1e768  ldfld    bool Microsoft.Crm.Dialogs.ShareDialogPage::Assign
0x1e76d  brtrue.s loc_1E776
0x1e76f  ldstr    a0_1// "0"
0x1e774  br.s     loc_1E77B
0x1e776  ldstr    a1// "1"
0x1e77b  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1e780  ldarg.0
0x1e781  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e786  ldarg.0
0x1e787  ldfld    bool Microsoft.Crm.Dialogs.ShareDialogPage::Share
0x1e78c  brtrue.s loc_1E795
0x1e78e  ldstr    a0_1// "0"
0x1e793  br.s     loc_1E79A
0x1e795  ldstr    a1// "1"
0x1e79a  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1e79f  ldarg.0
0x1e7a0  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e7a5  ldstr    aMaskCount// "</mask><count>"
0x1e7aa  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1e7af  ldarg.0
0x1e7b0  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e7b5  ldarg.0
0x1e7b6  ldflda   int32 Microsoft.Crm.Dialogs.ShareDialogPage::PermittedCount
0x1e7bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e7c0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1e7c5  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1e7ca  ldarg.0
0x1e7cb  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e7d0  ldstr    aCountIds// "</count><ids>"
0x1e7d5  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1e7da  ldarg.0
0x1e7db  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1e7e0  ldarg.0
  ... truncated ...
```
