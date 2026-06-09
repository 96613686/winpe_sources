# Microsoft.Crm.Service.Web.Viewer::ConfigureMenus

- ea: `0x4000`
- end: `0x410d`
- name: `Microsoft.Crm.Service.Web.Viewer::ConfigureMenus`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4000`

## pseudocode

```c

```

## disassembly

```asm
0x4000  ldarg.0
0x4001  ldfld    string Microsoft.Crm.Service.Web.Viewer::_contentId
0x4006  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x400b  brtrue   loc_410C
0x4010  ldarg.0
0x4011  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4016  ldc.i4.8
0x4017  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x401c  ldarg.0
0x401d  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0x4022  ldc.i4.2
0x4023  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType)
0x4028  ldstr    aKbarticle// "kbarticle"
0x402d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4032  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4037  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x403c  castclass [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Article
0x4041  stloc.0
0x4042  ldloc.0
0x4043  ldarg.0
0x4044  ldfld    string Microsoft.Crm.Service.Web.Viewer::_contentId
0x4049  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x404e  ldloc.0
0x404f  ldstr    aColumnsetColum_2// "<columnset><column>title</column></colu"...
0x4054  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x4059  ldarg.0
0x405a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0x405f  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppViewerMenuBar
0x4064  stloc.1
0x4065  ldloc.1
0x4066  ldarg.0
0x4067  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x406c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4071  ldstr    aIsrestrictedmo// "IsRestrictedMode"
0x4076  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x407b  ldstr    aTrue// "true"
0x4080  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4085  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppViewerMenuBar::set_IsRestrictedMode(bool)
0x408a  ldloc.1
0x408b  ldarg.0
0x408c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4091  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4096  ldstr    aHideemailbutto// "HideEmailButton"
0x409b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x40a0  ldstr    aTrue// "true"
0x40a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x40aa  ldc.i4.0
0x40ab  ceq
0x40ad  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppViewerMenuBar::set_ShowEmailButton(bool)
0x40b2  ldloc.1
0x40b3  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppViewerMenuBar::get_IsRestrictedMode()
0x40b8  brtrue.s loc_4106
0x40ba  ldarg.0
0x40bb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40c0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x40c5  ldarg.0
0x40c6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40cb  ldstr    aFormTitleMask// "Form_Title_Mask"
0x40d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40d5  ldc.i4.2
0x40d6  newarr   [mscorlib]System.Object
0x40db  dup
0x40dc  ldc.i4.0
0x40dd  ldarg.0
0x40de  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40e3  ldstr    aFormTitleArtic// "Form_Title_ArticleViewer"
0x40e8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40ed  stelem.ref
0x40ee  dup
0x40ef  ldc.i4.1
0x40f0  ldloc.0
0x40f1  ldstr    aTitle// "title"
0x40f6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x40fb  stelem.ref
0x40fc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4101  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x4106  ldloc.1
0x4107  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::Execute()
0x410c  ret
```
