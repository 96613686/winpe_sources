# Microsoft.Crm.Web.Tools.Views.FormEditorPage::ConfigurePage

- ea: `0x7f0c0`
- end: `0x7f829`
- name: `Microsoft.Crm.Web.Tools.Views.FormEditorPage::ConfigurePage`
- size: `1897`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7f0c0`
- `0x7f830`
- `0x7f8d0`
- `0x7fa70`
- `0x7fb70`
- `0x7fe70`
- `0x80100`
- `0x802e0`

## string_xrefs

- `0x7f670`: `/fieldxml`
- `0x7f0cc`: `FormEditorWebService`
- `0x7f13f`: `Forms.Recommended.AltTag`
- `0x7f5a1`: `cancreateforms`

## pseudocode

```c

```

## disassembly

```asm
0x7f0c0  ldarg.0
0x7f0c1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::ConfigurePage()
0x7f0c6  ldarg.0
0x7f0c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7f0cc  ldstr    aFormeditorwebs// "FormEditorWebService"
0x7f0d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x7f0d6  ldarg.0
0x7f0d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7f0dc  ldstr    aControlsNotifi// "/_controls/Notifications/notifications."...
0x7f0e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7f0e6  ldstr    asc_13CDBE// "/"
0x7f0eb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7f0f0  call     class [System]System.Uri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAbsoluteUrl(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f0f5  stloc.0
0x7f0f6  ldarg.0
0x7f0f7  ldloc.0
0x7f0f8  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x7f0fd  ldstr    aWebresources// "/WebResources/"
0x7f102  call     string [mscorlib]System.String::Concat(string, string)
0x7f107  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::webResourceRootUrl
0x7f10c  ldarg.0
0x7f10d  ldarg.0
0x7f10e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7f113  ldstr    aFormeditorLock// "FormEditor_Locked_Field"
0x7f118  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7f11d  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::lockedField
0x7f122  ldarg.0
0x7f123  ldarg.0
0x7f124  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7f129  ldstr    aFormsRequiredA// "Forms.Required.AltTag"
0x7f12e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7f133  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::businessRequired
0x7f138  ldarg.0
0x7f139  ldarg.0
0x7f13a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7f13f  ldstr    aFormsRecommend// "Forms.Recommended.AltTag"
0x7f144  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7f149  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::businessRecommended
0x7f14e  ldarg.0
0x7f14f  ldarg.0
0x7f150  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7f155  ldstr    aFormsSecuredAl// "Forms.Secured.AltTag"
0x7f15a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7f15f  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::securedField
0x7f164  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadCustomization()
0x7f169  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7f16e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f173  brfalse.s loc_7F186
0x7f175  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0x7f17a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7f17f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f184  brtrue.s loc_7F197
0x7f186  ldc.i4   0x80040277
0x7f18b  ldc.i4.0
0x7f18c  newarr   [mscorlib]System.Object
0x7f191  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x7f196  throw
0x7f197  ldarg.0
0x7f198  ldarg.0
0x7f199  call     instance valuetype FormAction Microsoft.Crm.Web.Tools.Views.FormEditorPage::GetAction()
0x7f19e  stfld    valuetype FormAction Microsoft.Crm.Web.Tools.Views.FormEditorPage::_action
0x7f1a3  ldarg.0
0x7f1a4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7f1a9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x7f1ae  ldstr    aFormid_0// "formId"
0x7f1b3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7f1b8  stloc.1
0x7f1b9  ldarg.0
0x7f1ba  ldloc.1
0x7f1bb  brfalse.s loc_7F1CD
0x7f1bd  ldloc.1
0x7f1be  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7f1c3  brfalse.s loc_7F1CD
0x7f1c5  ldloc.1
0x7f1c6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7f1cb  br.s     loc_7F1D2
0x7f1cd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7f1d2  stfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formId
0x7f1d7  ldarg.0
0x7f1d8  ldfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formId
0x7f1dd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7f1e2  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7f1e7  brfalse  loc_7F277
0x7f1ec  ldarg.0
0x7f1ed  ldarg.0
0x7f1ee  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7f1f3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x7f1f8  ldstr    aObjecttypecode_0// "objectTypeCode"
0x7f1fd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7f202  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7f207  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x7f20c  stfld    int32 Microsoft.Crm.Web.Tools.Views.FormEditorPage::_objectTypeCode
0x7f211  ldarg.0
0x7f212  ldarg.0
0x7f213  ldfld    int32 Microsoft.Crm.Web.Tools.Views.FormEditorPage::_objectTypeCode
0x7f218  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7f21d  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f222  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x7f227  ldarg.0
0x7f228  ldarg.0
0x7f229  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7f22e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x7f233  ldstr    aObjecttypecode_0// "objectTypeCode"
0x7f238  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7f23d  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::objectCode
0x7f242  ldarg.0
0x7f243  ldarg.0
0x7f244  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x7f249  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x7f24e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x7f253  stloc.s  4
0x7f255  ldloca.s 4
0x7f257  ldstr    aB// "B"
0x7f25c  call     instance string [mscorlib]System.Guid::ToString(string)
0x7f261  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::currentEntityId
0x7f266  ldarg.0
0x7f267  ldarg.0
0x7f268  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::SaveForm()
0x7f26d  stfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formId
0x7f272  br       loc_7F3DA
0x7f277  ldarg.0
0x7f278  ldarg.0
0x7f279  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7f27e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x7f283  ldstr    aObjecttypecode_0// "objectTypeCode"
0x7f288  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7f28d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7f292  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x7f297  stfld    int32 Microsoft.Crm.Web.Tools.Views.FormEditorPage::_objectTypeCode
0x7f29c  ldarg.0
0x7f29d  ldarg.0
0x7f29e  ldfld    int32 Microsoft.Crm.Web.Tools.Views.FormEditorPage::_objectTypeCode
0x7f2a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7f2a8  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f2ad  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x7f2b2  ldarg.0
0x7f2b3  ldarg.0
0x7f2b4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x7f2b9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x7f2be  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x7f2c3  stloc.s  4
0x7f2c5  ldloca.s 4
0x7f2c7  ldstr    aB// "B"
0x7f2cc  call     instance string [mscorlib]System.Guid::ToString(string)
0x7f2d1  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::currentEntityId
0x7f2d6  ldarg.0
0x7f2d7  ldarg.0
0x7f2d8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7f2dd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x7f2e2  ldstr    aObjecttypecode_0// "objectTypeCode"
0x7f2e7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7f2ec  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::objectCode
0x7f2f1  ldarg.0
0x7f2f2  ldarg.0
0x7f2f3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7f2f8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x7f2fd  ldstr    aFormtype// "formtype"
0x7f302  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7f307  stfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formTypeName
0x7f30c  ldarg.0
0x7f30d  ldarg.0
0x7f30e  ldfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formTypeName
0x7f313  brfalse.s loc_7F331
0x7f315  ldtoken  [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase/FormType
0x7f31a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7f31f  ldarg.0
0x7f320  ldfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formTypeName
0x7f325  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x7f32a  unbox.any [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase/FormType
0x7f32f  br.s     loc_7F332
0x7f331  ldc.i4.4
0x7f332  stfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase/FormType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formTypeCode
0x7f337  ldarg.0
0x7f338  ldfld    valuetype FormAction Microsoft.Crm.Web.Tools.Views.FormEditorPage::_action
0x7f33d  brfalse  loc_7F3DA
0x7f342  ldarg.0
0x7f343  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7f348  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x7f34d  ldstr    aFormid_0// "formId"
0x7f352  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7f357  stloc.1
0x7f358  ldloc.1
0x7f359  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7f35e  brfalse.s loc_7F388
0x7f360  ldarg.0
0x7f361  ldfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::objectCode
0x7f366  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7f36b  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x7f370  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7f375  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Forms.FormDescriptorCache::GetFormDescriptor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f37a  stloc.s  5
0x7f37c  ldloc.s  5
0x7f37e  brfalse.s loc_7F388
0x7f380  ldloc.s  5
0x7f382  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_ID()
0x7f387  stloc.1
0x7f388  ldarg.0
0x7f389  ldloc.1
0x7f38a  brfalse.s loc_7F39C
0x7f38c  ldloc.1
0x7f38d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7f392  brfalse.s loc_7F39C
0x7f394  ldloc.1
0x7f395  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7f39a  br.s     loc_7F3A1
0x7f39c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7f3a1  stfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formId
0x7f3a6  ldc.i4.4
0x7f3a7  ldarg.0
0x7f3a8  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase/FormType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formTypeCode
0x7f3ad  bne.un.s loc_7F3C8
0x7f3af  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7f3b4  ldarg.0
0x7f3b5  ldfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formId
0x7f3ba  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7f3bf  brfalse.s loc_7F3C8
0x7f3c1  ldarg.0
0x7f3c2  ldc.i4.0
0x7f3c3  stfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase/FormType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formTypeCode
0x7f3c8  ldarg.0
0x7f3c9  ldarg.0
0x7f3ca  ldarg.0
0x7f3cb  ldfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formId
0x7f3d0  call     instance string Microsoft.Crm.Web.Tools.Views.FormEditorPage::GetFormXmlstring(valuetype [mscorlib]System.Guid id)
0x7f3d5  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::_formXmlString
0x7f3da  ldarg.0
0x7f3db  call     instance void Microsoft.Crm.Web.Tools.Views.FormEditorPage::UpdateFormMergeInformation()
0x7f3e0  ldarg.0
0x7f3e1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.Views.FormEditorPage::PreviewFormOtc
0x7f3e6  ldarg.0
0x7f3e7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x7f3ec  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x7f3f1  stloc.s  6
0x7f3f3  ldloca.s 6
0x7f3f5  ldstr    aD// "D"
0x7f3fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7f3ff  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x7f404  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x7f409  ldarg.0
0x7f40a  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.Views.FormEditorPage::SubmitterFormOtc
0x7f40f  ldarg.0
0x7f410  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x7f415  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x7f41a  stloc.s  6
0x7f41c  ldloca.s 6
0x7f41e  ldstr    aD// "D"
0x7f423  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7f428  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x7f42d  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x7f432  ldarg.0
0x7f433  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.Views.FormEditorPage::PreviewFormOtc
0x7f438  ldstr    aObjecttypecode_0// "objectTypeCode"
0x7f43d  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x7f442  ldarg.0
0x7f443  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.Views.FormEditorPage::SubmitterFormOtc
0x7f448  ldstr    aObjecttypecode_0// "objectTypeCode"
0x7f44d  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x7f452  ldarg.0
0x7f453  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.Views.FormEditorPage::IsRefreshEnabled
0x7f458  ldstr    aIsrefreshenabl// "IsRefreshEnabled"
0x7f45d  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x7f462  ldarg.0
0x7f463  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x7f468  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x7f46d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_UpgradeFormMerge()
0x7f472  ldarg.0
0x7f473  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x7f478  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x7f47d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x7f482  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f487  stloc.s  7
0x7f489  ldloca.s 7
0x7f48b  call     instance string [mscorlib]System.Boolean::ToString()
0x7f490  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::isFormMergeFcbEnabled
0x7f495  ldarg.0
0x7f496  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x7f49b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x7f4a0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ActivityInsights()
0x7f4a5  ldarg.0
0x7f4a6  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x7f4ab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x7f4b0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x7f4b5  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f4ba  stfld    bool Microsoft.Crm.Web.Tools.Views.FormEditorPage::supportACIControl
0x7f4bf  ldarg.0
0x7f4c0  ldarg.0
0x7f4c1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x7f4c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x7f4cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x7f4d0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsRelationshipAssistanceFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f4d5  stfld    bool Microsoft.Crm.Web.Tools.Views.FormEditorPage::supportRAControl
0x7f4da  ldarg.0
0x7f4db  ldarg.0
0x7f4dc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x7f4e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7f4e6  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveEntityXml(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f4eb  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x7f4f0  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Web.Tools.Views.FormEditorPage::_fieldXml
0x7f4f5  ldarg.0
0x7f4f6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
  ... truncated ...
```
