# Microsoft.Crm.Application.Pages.Dialogs.CreateOpportunity::ConfigureForm

- ea: `0xf5ac0`
- end: `0xf5dac`
- name: `Microsoft.Crm.Application.Pages.Dialogs.CreateOpportunity::ConfigureForm`
- size: `748`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xf59f0`
- `0xf5ac0`

## string_xrefs

- `0xf5add`: `Dialog_CreateOpportunityForList_Title`
- `0xf5af3`: `Dialog_CreateOpportunityForList_Header`
- `0xf5b09`: `Dialog_CreateOpportunityForList_Description`
- `0xf5b31`: `Button_Label_ListOpportunityCreate`
- `0xf5cc9`: `Opportunities can be created only for Accounts or Contacts.`
- `0xf5cd3`: `Opportunities can be created only for Accounts or Contacts.`

## pseudocode

```c

```

## disassembly

```asm
0xf5ac0  ldarg.0
0xf5ac1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xf5ac6  ldarg.0
0xf5ac7  ldc.i4   0x2F1
0xf5acc  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_Width(int32)
0xf5ad1  ldarg.0
0xf5ad2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf5ad7  ldarg.0
0xf5ad8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf5add  ldstr    aDialogCreateop// "Dialog_CreateOpportunityForList_Title"
0xf5ae2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf5ae7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xf5aec  ldarg.0
0xf5aed  ldarg.0
0xf5aee  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf5af3  ldstr    aDialogCreateop_0// "Dialog_CreateOpportunityForList_Header"
0xf5af8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf5afd  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0xf5b02  ldarg.0
0xf5b03  ldarg.0
0xf5b04  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf5b09  ldstr    aDialogCreateop_1// "Dialog_CreateOpportunityForList_Descrip"...
0xf5b0e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf5b13  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0xf5b18  ldarg.0
0xf5b19  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xf5b1e  ldc.i4.s 0x10
0xf5b20  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0xf5b25  pop
0xf5b26  ldarg.0
0xf5b27  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xf5b2c  ldstr    aButbegin// "butBegin"
0xf5b31  ldstr    aButtonLabelLis// "Button_Label_ListOpportunityCreate"
0xf5b36  ldstr    aApplychanges// "applychanges();"
0xf5b3b  ldc.i4.0
0xf5b3c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0xf5b41  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0xf5b46  pop
0xf5b47  ldarg.0
0xf5b48  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xf5b4d  ldc.i4.2
0xf5b4e  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0xf5b53  pop
0xf5b54  ldarg.0
0xf5b55  ldarg.0
0xf5b56  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf5b5b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf5b60  ldstr    aSparentid// "sParentId"
0xf5b65  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf5b6a  call     instance void Microsoft.Crm.Application.Pages.Dialogs.CreateOpportunity::set_ParentId(string value)
0xf5b6f  ldarg.0
0xf5b70  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf5b75  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0xf5b7a  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0xf5b7f  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0xf5b84  stloc.0
0xf5b85  ldarg.0
0xf5b86  ldc.i4.3
0xf5b87  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf5b8c  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf5b91  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xf5b96  ldloc.0
0xf5b97  callvirt instance int32 [mscorlib]System.String::get_Length()
0xf5b9c  ldc.i4.0
0xf5b9d  ble      loc_F5CFB
0xf5ba2  ldarg.0
0xf5ba3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf5ba8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf5bad  ldstr    aIid// "iId"
0xf5bb2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf5bb7  stloc.1
0xf5bb8  ldarg.0
0xf5bb9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf5bbe  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf5bc3  ldstr    aSparentid// "sParentId"
0xf5bc8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf5bcd  stloc.2
0xf5bce  ldc.i4.0
0xf5bcf  stloc.3
0xf5bd0  ldc.i4.0
0xf5bd1  stloc.s  4
0xf5bd3  ldc.i4.0
0xf5bd4  stloc.s  5
0xf5bd6  ldloc.2
0xf5bd7  brfalse.s loc_F5BFA
0xf5bd9  ldloc.2
0xf5bda  callvirt instance int32 [mscorlib]System.String::get_Length()
0xf5bdf  ldc.i4.0
0xf5be0  ble.s    loc_F5BFA
0xf5be2  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::.ctor()
0xf5be7  ldloc.2
0xf5be8  ldloca.s 3
0xf5bea  ldloca.s 4
0xf5bec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf5bf1  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::RetrieveListMemberTypeAndStatus(string, bool&, bool&, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf5bf6  stloc.s  5
0xf5bf8  br.s     loc_F5C18
0xf5bfa  ldloc.2
0xf5bfb  callvirt instance int32 [mscorlib]System.String::get_Length()
0xf5c00  brtrue.s loc_F5C18
0xf5c02  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::.ctor()
0xf5c07  ldloc.1
0xf5c08  ldloca.s 3
0xf5c0a  ldloca.s 4
0xf5c0c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf5c11  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::RetrieveListMemberTypeAndStatus(string, bool&, bool&, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf5c16  stloc.s  5
0xf5c18  ldloc.s  4
0xf5c1a  brfalse  loc_F5CE5
0xf5c1f  ldloc.2
0xf5c20  brfalse  loc_F5CE5
0xf5c25  ldloc.2
0xf5c26  callvirt instance int32 [mscorlib]System.String::get_Length()
0xf5c2b  ldc.i4.0
0xf5c2c  ble      loc_F5CE5
0xf5c31  ldstr    aOpportunity// "opportunity"
0xf5c36  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf5c3b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf5c40  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xf5c45  stloc.s  6
0xf5c47  ldloc.s  6
0xf5c49  ldloc.0
0xf5c4a  ldstr    aOwneridType8// "<ownerid type=\"8\">"
0xf5c4f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xf5c54  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0xf5c59  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0xf5c5e  ldstr    aOwnerid_1// "</ownerid>"
0xf5c63  call     string [mscorlib]System.String::Concat(string, string, string)
0xf5c68  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendInnerXml(string, string)
0xf5c6d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0xf5c72  ldloc.s  5
0xf5c74  ldc.i4.1
0xf5c75  beq.s    loc_F5C7E
0xf5c77  ldloc.s  5
0xf5c79  ldc.i4.2
0xf5c7a  beq.s    loc_F5CA3
0xf5c7c  br.s     loc_F5CC8
0xf5c7e  ldloc.s  6
0xf5c80  ldloc.s  6
0xf5c82  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0xf5c87  ldstr    aCustomeridType// "<customerid type=\"1\">"
0xf5c8c  ldloc.1
0xf5c8d  ldstr    aCustomerid// "</customerid>"
0xf5c92  call     string [mscorlib]System.String::Concat(string, string, string)
0xf5c97  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendInnerXml(string, string)
0xf5c9c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0xf5ca1  br.s     loc_F5CDE
0xf5ca3  ldloc.s  6
0xf5ca5  ldloc.s  6
0xf5ca7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0xf5cac  ldstr    aCustomeridType_0// "<customerid type=\"2\">"
0xf5cb1  ldloc.1
0xf5cb2  ldstr    aCustomerid// "</customerid>"
0xf5cb7  call     string [mscorlib]System.String::Concat(string, string, string)
0xf5cbc  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendInnerXml(string, string)
0xf5cc1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0xf5cc6  br.s     loc_F5CDE
0xf5cc8  ldc.i4.0
0xf5cc9  ldstr    aOpportunitiesC// "Opportunities can be created only for A"...
0xf5cce  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xf5cd3  ldstr    aOpportunitiesC// "Opportunities can be created only for A"...
0xf5cd8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xf5cdd  throw
0xf5cde  ldloc.s  6
0xf5ce0  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Create()
0xf5ce5  ldarg.0
0xf5ce6  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xf5ceb  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0xf5cf0  leave    loc_F5DAB
0xf5cf5  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0xf5cfa  throw
0xf5cfb  ldarg.0
0xf5cfc  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xf5d01  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm
0xf5d06  ldstr    aOpportunity// "opportunity"
0xf5d0b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf5d10  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf5d15  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xf5d1a  stloc.s  7
0xf5d1c  dup
0xf5d1d  ldarg.0
0xf5d1e  ldftn    instance void Microsoft.Crm.Application.Pages.Dialogs.CreateOpportunity::OpportunityForList_ObjectModelReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0xf5d24  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler::.ctor(object, native int)
0xf5d29  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::add_DataBound(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler)
0xf5d2e  ldloc.s  7
0xf5d30  ldc.i4.s 9
0xf5d32  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm::ExecuteForFormType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType)
0xf5d37  ldarg.0
0xf5d38  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xf5d3d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrudForm
0xf5d42  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormBody [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_FormBody()
0xf5d47  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xf5d4c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0xf5d51  stloc.s  8
0xf5d53  br.s     loc_F5D8B
0xf5d55  ldloc.s  8
0xf5d57  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xf5d5c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormTab
0xf5d61  stloc.s  9
0xf5d63  ldloc.s  9
0xf5d65  brfalse.s loc_F5D8B
0xf5d67  ldloc.s  9
0xf5d69  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xf5d6e  ldstr    a25a511f64cf04c// "{25A511F6-4CF0-4c5e-838F-1AEB9BC07ED9}"
0xf5d73  ldc.i4.5
0xf5d74  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xf5d79  brtrue.s loc_F5D8B
0xf5d7b  ldloc.s  9
0xf5d7d  ldc.i4.1
0xf5d7e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xf5d83  ldloc.s  9
0xf5d85  ldc.i4.0
0xf5d86  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0xf5d8b  ldloc.s  8
0xf5d8d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf5d92  brtrue.s loc_F5D55
0xf5d94  leave.s  loc_F5DAB
0xf5d96  ldloc.s  8
0xf5d98  isinst   [mscorlib]System.IDisposable
0xf5d9d  stloc.s  0xA
0xf5d9f  ldloc.s  0xA
0xf5da1  brfalse.s loc_F5DAA
0xf5da3  ldloc.s  0xA
0xf5da5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf5daa  endfinally
0xf5dab  ret
```
