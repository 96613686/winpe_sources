# Microsoft.Crm.Service.Web.CS.ArticleCommentPage::ConfigurePage

- ea: `0x5940`
- end: `0x5b40`
- name: `Microsoft.Crm.Service.Web.CS.ArticleCommentPage::ConfigurePage`
- size: `512`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5940`

## string_xrefs

- `0x597d`: `CustomerService`
- `0x594c`: `LOCID_KBCOMMENT_TITLEREQUIRED`
- `0x5957`: `Web.CS.articles.Comment.edit.aspx_26`
- `0x5988`: `kbarticlecomment`
- `0x5a85`: `_CreateFromId`
- `0x5add`: `Article_Comment_Dlg_Title`
- `0x5af3`: `Article_Comment_Dlg_Desc`

## pseudocode

```c

```

## disassembly

```asm
0x5940  ldarg.0
0x5941  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0x5946  ldarg.0
0x5947  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x594c  ldstr    aLocidKbcomment// "LOCID_KBCOMMENT_TITLEREQUIRED"
0x5951  ldarg.0
0x5952  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5957  ldstr    aWebCsArticlesC// "Web.CS.articles.Comment.edit.aspx_26"
0x595c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5961  ldc.i4.0
0x5962  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5967  ldarg.0
0x5968  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x596d  ldstr    aStyleTypeTextC// "<style type=\"text/css\"> textarea\t{ h"...
0x5972  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetCustomResource(string)
0x5977  ldarg.0
0x5978  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x597d  ldstr    aCustomerservic// "CustomerService"
0x5982  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x5987  ldarg.0
0x5988  ldstr    aKbarticlecomme// "kbarticlecomment"
0x598d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5992  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5997  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x599c  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_comment
0x59a1  ldarg.0
0x59a2  ldarg.0
0x59a3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x59a8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x59ad  ldstr    aMode// "mode"
0x59b2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x59b7  ldstr    aReject// "reject"
0x59bc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x59c1  stfld    bool Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_rejectMode
0x59c6  ldarg.0
0x59c7  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_comment
0x59cc  ldarg.0
0x59cd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x59d2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x59d7  ldstr    aId// "id"
0x59dc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x59e1  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x59e6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x59eb  ldarg.0
0x59ec  ldarg.0
0x59ed  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_comment
0x59f2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x59f7  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x59fc  ldarg.0
0x59fd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5a02  ldstr    aBrejectmode// "_bRejectMode"
0x5a07  ldarg.0
0x5a08  ldfld    bool Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_rejectMode
0x5a0d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x5a12  ldarg.0
0x5a13  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_comment
0x5a18  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x5a1d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5a22  brfalse.s loc_5A4C
0x5a24  ldarg.0
0x5a25  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_comment
0x5a2a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve()
0x5a2f  ldarg.0
0x5a30  ldarg.0
0x5a31  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_comment
0x5a36  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x5a3b  ldstr    aKbarticleid// "kbarticleid"
0x5a40  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x5a45  stfld    string Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_parentId
0x5a4a  br.s     loc_5A99
0x5a4c  ldarg.0
0x5a4d  ldarg.0
0x5a4e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5a53  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5a58  ldstr    aParentid// "parentId"
0x5a5d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a62  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x5a67  stfld    string Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_parentId
0x5a6c  ldarg.0
0x5a6d  ldfld    string Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_parentId
0x5a72  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a77  brfalse.s loc_5A99
0x5a79  ldarg.0
0x5a7a  ldarg.0
0x5a7b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5a80  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5a85  ldstr    aCreatefromid// "_CreateFromId"
0x5a8a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a8f  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x5a94  stfld    string Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_parentId
0x5a99  ldarg.0
0x5a9a  ldc.i4.0
0x5a9b  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_ShowStatusBar(bool)
0x5aa0  ldarg.0
0x5aa1  ldfld    bool Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_rejectMode
0x5aa6  brfalse.s loc_5AD6
0x5aa8  ldarg.0
0x5aa9  ldarg.0
0x5aaa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5aaf  ldstr    aArticleRejectD// "Article_Reject_Dlg_Title"
0x5ab4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5ab9  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x5abe  ldarg.0
0x5abf  ldarg.0
0x5ac0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5ac5  ldstr    aArticleRejectD_0// "Article_Reject_Dlg_Desc"
0x5aca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5acf  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x5ad4  br.s     loc_5B02
0x5ad6  ldarg.0
0x5ad7  ldarg.0
0x5ad8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5add  ldstr    aArticleComment// "Article_Comment_Dlg_Title"
0x5ae2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5ae7  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x5aec  ldarg.0
0x5aed  ldarg.0
0x5aee  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5af3  ldstr    aArticleComment_0// "Article_Comment_Dlg_Desc"
0x5af8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5afd  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x5b02  ldarg.0
0x5b03  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_comment
0x5b08  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x5b0d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5b12  brfalse.s loc_5B25
0x5b14  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_PublishArticle()
0x5b19  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5b1e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5b23  brfalse.s loc_5B32
0x5b25  ldarg.0
0x5b26  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x5b2b  ldc.i4.3
0x5b2c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButtons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x5b31  ret
0x5b32  ldarg.0
0x5b33  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x5b38  ldc.i4.2
0x5b39  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x5b3e  pop
0x5b3f  ret
```
