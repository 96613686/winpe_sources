# Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ConfigureForm

- ea: `0x1b700`
- end: `0x1ba25`
- name: `Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ConfigureForm`
- size: `805`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1b700`

## string_xrefs

- `0x1b91b`: `text/xml`
- `0x1b956`: `XML loaded from the stream returned String.Empty.`
- `0x1b960`: `XML loaded from the stream returned String.Empty.`
- `0x1ba0e`: `Button_Label_Remove`
- `0x1b990`: `Dialog_RemoveUser_Title`
- `0x1b9bf`: `Dialog_RemoveUsers_Description`
- `0x1b9eb`: `Dialog_RemoveUsers_Description_Casing`

## pseudocode

```c

```

## disassembly

```asm
0x1b700  ldarg.0
0x1b701  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1b706  ldarg.0
0x1b707  ldarg.0
0x1b708  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b70d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b712  ldstr    aItotal// "iTotal"
0x1b717  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b71c  ldc.i4.7
0x1b71d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b722  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1b727  stfld    int32 Microsoft.Crm.Dialogs.RemoveUsersDialogPage::iTotal
0x1b72c  ldarg.0
0x1b72d  ldarg.0
0x1b72e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b733  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b738  ldstr    aIobjtype// "iObjType"
0x1b73d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b742  ldc.i4.7
0x1b743  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b748  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1b74d  stfld    int32 Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ObjType
0x1b752  ldarg.0
0x1b753  ldfld    int32 Microsoft.Crm.Dialogs.RemoveUsersDialogPage::iTotal
0x1b758  ldc.i4.1
0x1b759  beq.s    loc_1B76F
0x1b75b  ldarg.0
0x1b75c  ldarg.0
0x1b75d  ldfld    int32 Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ObjType
0x1b762  ldc.i4.2
0x1b763  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1b768  stfld    string Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ObjName
0x1b76d  br.s     loc_1B781
0x1b76f  ldarg.0
0x1b770  ldarg.0
0x1b771  ldfld    int32 Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ObjType
0x1b776  ldc.i4.1
0x1b777  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1b77c  stfld    string Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ObjName
0x1b781  ldarg.0
0x1b782  ldfld    int32 Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ObjType
0x1b787  ldc.i4.8
0x1b788  bne.un.s loc_1B79A
0x1b78a  ldarg.0
0x1b78b  ldc.i4.s 9
0x1b78d  ldc.i4.1
0x1b78e  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1b793  stfld    string Microsoft.Crm.Dialogs.RemoveUsersDialogPage::TargetName
0x1b798  br.s     loc_1B7B8
0x1b79a  ldarg.0
0x1b79b  ldfld    int32 Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ObjType
0x1b7a0  ldc.i4   0x232B
0x1b7a5  bne.un.s loc_1B7B8
0x1b7a7  ldarg.0
0x1b7a8  ldc.i4   0x7DD
0x1b7ad  ldc.i4.1
0x1b7ae  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1b7b3  stfld    string Microsoft.Crm.Dialogs.RemoveUsersDialogPage::TargetName
0x1b7b8  ldarg.0
0x1b7b9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b7be  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1b7c3  stloc.0
0x1b7c4  ldloc.0
0x1b7c5  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1b7ca  ldc.i4.0
0x1b7cb  conv.i8
0x1b7cc  ble      loc_1B978
0x1b7d1  ldloc.0
0x1b7d2  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x1b7d7  stloc.2
0x1b7d8  ldloc.2
0x1b7d9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b7de  brfalse  loc_1B94D
0x1b7e3  ldc.i4.1
0x1b7e4  newarr   [mscorlib]System.String
0x1b7e9  stloc.3
0x1b7ea  ldloc.3
0x1b7eb  ldc.i4.0
0x1b7ec  ldarg.0
0x1b7ed  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b7f2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b7f7  ldstr    aIid// "iId"
0x1b7fc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b801  stelem.ref
0x1b802  ldarg.0
0x1b803  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b808  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b80d  ldstr    aTeamid// "teamid"
0x1b812  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b817  stloc.s  4
0x1b819  ldarg.0
0x1b81a  ldfld    int32 Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ObjType
0x1b81f  stloc.s  5
0x1b821  ldloc.s  5
0x1b823  ldc.i4.8
0x1b824  beq.s    loc_1B834
0x1b826  ldloc.s  5
0x1b828  ldc.i4   0x232B
0x1b82d  beq.s    loc_1B854
0x1b82f  br       loc_1B915
0x1b834  ldloc.3
0x1b835  call     valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ConvertStringArrayToGuidArray(string[])
0x1b83a  stloc.s  6
0x1b83c  ldloc.s  4
0x1b83e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1b843  ldloc.s  6
0x1b845  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b84a  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RemoveMembersTeam(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b84f  br       loc_1B915
0x1b854  ldstr    aTerritory// "territory"
0x1b859  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b85e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b863  stloc.s  7
0x1b865  ldstr    aTerritory// "territory"
0x1b86a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x1b86f  dup
0x1b870  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x1b875  ldstr    aTerritoryid// "territoryid"
0x1b87a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x1b87f  dup
0x1b880  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x1b885  ldstr    aManagerid// "managerid"
0x1b88a  ldc.i4.0
0x1b88b  ldloc.3
0x1b88c  ldc.i4.0
0x1b88d  ldelem.ref
0x1b88e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x1b893  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b898  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b89d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x1b8a2  stloc.s  8
0x1b8a4  br.s     loc_1B8D0
0x1b8a6  ldloc.s  8
0x1b8a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x1b8ad  stloc.s  9
0x1b8af  ldloc.s  7
0x1b8b1  ldloc.s  9
0x1b8b3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x1b8b8  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x1b8bd  ldloc.s  7
0x1b8bf  ldstr    aTerritoryManag// "<territory><managerid></managerid></ter"...
0x1b8c4  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x1b8c9  ldloc.s  7
0x1b8cb  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x1b8d0  ldloc.s  8
0x1b8d2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b8d7  brtrue.s loc_1B8A6
0x1b8d9  leave.s  loc_1B8E7
0x1b8db  ldloc.s  8
0x1b8dd  brfalse.s loc_1B8E6
0x1b8df  ldloc.s  8
0x1b8e1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b8e6  endfinally
0x1b8e7  ldstr    aSystemuser// "systemuser"
0x1b8ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b8f1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b8f6  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SystemUser::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1b8fb  dup
0x1b8fc  ldloc.3
0x1b8fd  ldc.i4.0
0x1b8fe  ldelem.ref
0x1b8ff  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x1b904  dup
0x1b905  ldstr    aTerritoryid// "territoryid"
0x1b90a  ldnull
0x1b90b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1b910  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x1b915  ldarg.0
0x1b916  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b91b  ldstr    aTextXml// "text/xml"
0x1b920  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1b925  ldarg.0
0x1b926  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b92b  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1b930  ldarg.0
0x1b931  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b936  ldstr    aOk// "<ok/>"
0x1b93b  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1b940  ldarg.0
0x1b941  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b946  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1b94b  br.s     loc_1B970
0x1b94d  ldloc.2
0x1b94e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b953  ldc.i4.0
0x1b954  cgt.un
0x1b956  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1b95b  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x1b960  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1b965  ldc.i4   0x80049002
0x1b96a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1b96f  throw
0x1b970  leave.s  loc_1B978
0x1b972  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x1b977  throw
0x1b978  ldarg.0
0x1b979  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1b97e  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1b983  stloc.1
0x1b984  ldloc.1
0x1b985  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1b98a  ldarg.0
0x1b98b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b990  ldstr    aDialogRemoveus// "Dialog_RemoveUser_Title"
0x1b995  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b99a  ldc.i4.1
0x1b99b  newarr   [mscorlib]System.Object
0x1b9a0  dup
0x1b9a1  ldc.i4.0
0x1b9a2  ldarg.0
0x1b9a3  ldfld    string Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ObjName
0x1b9a8  stelem.ref
0x1b9a9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b9ae  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1b9b3  ldloc.1
0x1b9b4  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1b9b9  ldarg.0
0x1b9ba  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b9bf  ldstr    aDialogRemoveus_0// "Dialog_RemoveUsers_Description"
0x1b9c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b9c9  ldc.i4.2
0x1b9ca  newarr   [mscorlib]System.Object
0x1b9cf  dup
0x1b9d0  ldc.i4.0
0x1b9d1  ldarg.0
0x1b9d2  ldfld    int32 Microsoft.Crm.Dialogs.RemoveUsersDialogPage::iTotal
0x1b9d7  box      [mscorlib]System.Int32
0x1b9dc  stelem.ref
0x1b9dd  dup
0x1b9de  ldc.i4.1
0x1b9df  ldarg.0
0x1b9e0  ldfld    string Microsoft.Crm.Dialogs.RemoveUsersDialogPage::ObjName
0x1b9e5  ldarg.0
0x1b9e6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b9eb  ldstr    aDialogRemoveus_1// "Dialog_RemoveUsers_Description_Casing"
0x1b9f0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b9f5  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCasedDisplayText(string, string)
0x1b9fa  stelem.ref
0x1b9fb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1ba00  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x1ba05  ldloc.1
0x1ba06  ldc.i4.0
0x1ba07  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x1ba0c  ldloc.1
0x1ba0d  ldc.i4.1
0x1ba0e  ldstr    aButtonLabelRem// "Button_Label_Remove"
0x1ba13  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x1ba18  ldloc.1
0x1ba19  ldc.i4.2
0x1ba1a  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x1ba1f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x1ba24  ret
```
