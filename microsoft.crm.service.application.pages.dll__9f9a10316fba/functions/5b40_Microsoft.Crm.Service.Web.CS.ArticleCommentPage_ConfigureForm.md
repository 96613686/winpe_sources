# Microsoft.Crm.Service.Web.CS.ArticleCommentPage::ConfigureForm

- ea: `0x5b40`
- end: `0x5ba7`
- name: `Microsoft.Crm.Service.Web.CS.ArticleCommentPage::ConfigureForm`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5b40`

## string_xrefs

- `0x5b46`: `kbarticlecomment`
- `0x5b97`: `Web.CS.articles.Comment.edit.aspx_74`

## pseudocode

```c

```

## disassembly

```asm
0x5b40  ldarg.0
0x5b41  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x5b46  ldstr    aKbarticlecomme// "kbarticlecomment"
0x5b4b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5b50  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5b55  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x5b5a  stloc.0
0x5b5b  ldarg.0
0x5b5c  ldloc.0
0x5b5d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x5b62  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x5b67  ldarg.0
0x5b68  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x5b6d  ldloc.0
0x5b6e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x5b73  ldarg.0
0x5b74  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl Microsoft.Crm.Service.Web.CS.ArticleCommentPage::kbarticleid
0x5b79  ldarg.0
0x5b7a  ldfld    string Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_parentId
0x5b7f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x5b84  ldarg.0
0x5b85  ldfld    bool Microsoft.Crm.Service.Web.CS.ArticleCommentPage::_rejectMode
0x5b8a  brfalse.s loc_5BA6
0x5b8c  ldarg.0
0x5b8d  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Service.Web.CS.ArticleCommentPage::title
0x5b92  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5b97  ldstr    aWebCsArticlesC_0// "Web.CS.articles.Comment.edit.aspx_74"
0x5b9c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5ba1  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x5ba6  ret
```
