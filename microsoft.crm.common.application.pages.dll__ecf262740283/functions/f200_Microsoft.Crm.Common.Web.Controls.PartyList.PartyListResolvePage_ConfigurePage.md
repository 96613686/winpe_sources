# Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::ConfigurePage

- ea: `0xf200`
- end: `0xf2eb`
- name: `Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::ConfigurePage`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xf2f0`

## string_xrefs

- `0xf206`: `/_common/styles/select.css.aspx`
- `0xf216`: `LOCID_CREATE_RECORD_FIRST`

## pseudocode

```c

```

## disassembly

```asm
0xf200  ldarg.0
0xf201  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf206  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0xf20b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf210  ldarg.0
0xf211  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf216  ldstr    aLocidCreateRec// "LOCID_CREATE_RECORD_FIRST"
0xf21b  ldarg.0
0xf21c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf221  ldstr    aWebActivitiesE_0// "Web.Activities.email.resolve.aspx_36"
0xf226  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf22b  ldc.i4.0
0xf22c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf231  ldarg.0
0xf232  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf237  ldstr    aLocidSelectExi// "LOCID_SELECT_EXISTING_RECORD"
0xf23c  ldarg.0
0xf23d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf242  ldstr    aWebActivitiesE_1// "Web.Activities.email.resolve.aspx_52"
0xf247  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf24c  ldc.i4.0
0xf24d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf252  ldarg.0
0xf253  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf258  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0xf25d  ldarg.0
0xf25e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf263  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0xf268  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf26d  ldc.i4.0
0xf26e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf273  ldarg.0
0xf274  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::btnQuickCreate
0xf279  ldarg.0
0xf27a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf27f  ldstr    aWebActivitiesE_2// "Web.Activities.email.resolve.aspx_178_0"
0xf284  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf289  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0xf28e  ldarg.0
0xf28f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::txtName
0xf294  ldarg.0
0xf295  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf29a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf29f  ldstr    aAddress// "address"
0xf2a4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf2a9  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0xf2ae  ldarg.0
0xf2af  call     instance void Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::InitializeResolveToControls()
0xf2b4  ldarg.0
0xf2b5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xf2ba  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xf2bf  dup
0xf2c0  ldarg.0
0xf2c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf2c6  ldstr    aEmailResolvead// "Email_ResolveAddress_Title"
0xf2cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf2d0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xf2d5  ldarg.0
0xf2d6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf2db  ldstr    aEmailResolvead_0// "Email_ResolveAddress_Description"
0xf2e0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf2e5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xf2ea  ret
```
