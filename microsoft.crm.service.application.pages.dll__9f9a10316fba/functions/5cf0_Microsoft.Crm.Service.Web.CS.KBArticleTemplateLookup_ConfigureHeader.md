# Microsoft.Crm.Service.Web.CS.KBArticleTemplateLookup::ConfigureHeader

- ea: `0x5cf0`
- end: `0x5d5d`
- name: `Microsoft.Crm.Service.Web.CS.KBArticleTemplateLookup::ConfigureHeader`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x5cf6`: `/_common/styles/dialogs.css.aspx`
- `0x5d17`: `/_static/_common/scripts/newdialog.js`
- `0x5d32`: `Web.CS.articles.lookup_template.aspx_21`
- `0x5d4d`: `Web.CS.articles.lookup_template.aspx_28`

## pseudocode

```c

```

## disassembly

```asm
0x5cf0  ldarg.0
0x5cf1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5cf6  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x5cfb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x5d00  ldarg.0
0x5d01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5d06  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x5d0b  ldnull
0x5d0c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x5d11  ldarg.0
0x5d12  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5d17  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/newdialog.js"
0x5d1c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5d21  ldarg.0
0x5d22  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5d27  ldstr    aLocidNoItemsMe// "LOCID_NO_ITEMS_MESSAGE"
0x5d2c  ldarg.0
0x5d2d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5d32  ldstr    aWebCsArticlesL// "Web.CS.articles.lookup_template.aspx_21"
0x5d37  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5d3c  ldc.i4.0
0x5d3d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5d42  ldarg.0
0x5d43  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5d48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5d4d  ldstr    aWebCsArticlesL_0// "Web.CS.articles.lookup_template.aspx_28"
0x5d52  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5d57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x5d5c  ret
```
