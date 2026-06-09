# Microsoft.Crm.Service.Web.Entitlements.EntitlementsTemplateLookup::ConfigureHeader

- ea: `0x6880`
- end: `0x68f3`
- name: `Microsoft.Crm.Service.Web.Entitlements.EntitlementsTemplateLookup::ConfigureHeader`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x688c`: `/_common/styles/dialogs.css.aspx`
- `0x68ad`: `/_static/_common/scripts/newdialog.js`
- `0x68c8`: `Web.entitlements.lookup_template.aspx_125`
- `0x68e3`: `Web.entitlements.lookup_template.aspx_28`

## pseudocode

```c

```

## disassembly

```asm
0x6880  ldarg.0
0x6881  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x6886  ldarg.0
0x6887  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x688c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x6891  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x6896  ldarg.0
0x6897  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x689c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x68a1  ldnull
0x68a2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x68a7  ldarg.0
0x68a8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x68ad  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/newdialog.js"
0x68b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x68b7  ldarg.0
0x68b8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x68bd  ldstr    aLocidNoItemsMe// "LOCID_NO_ITEMS_MESSAGE"
0x68c2  ldarg.0
0x68c3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x68c8  ldstr    aWebEntitlement// "Web.entitlements.lookup_template.aspx_1"...
0x68cd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x68d2  ldc.i4.0
0x68d3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x68d8  ldarg.0
0x68d9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x68de  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x68e3  ldstr    aWebEntitlement_0// "Web.entitlements.lookup_template.aspx_2"...
0x68e8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x68ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x68f2  ret
```
