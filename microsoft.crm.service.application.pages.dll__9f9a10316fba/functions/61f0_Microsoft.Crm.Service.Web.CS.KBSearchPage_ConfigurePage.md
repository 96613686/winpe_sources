# Microsoft.Crm.Service.Web.CS.KBSearchPage::ConfigurePage

- ea: `0x61f0`
- end: `0x63f6`
- name: `Microsoft.Crm.Service.Web.CS.KBSearchPage::ConfigurePage`
- size: `518`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x61f0`

## string_xrefs

- `0x61fc`: `/_common/styles/select.css.aspx`
- `0x63ce`: `btnRemove`
- `0x63d3`: `Button_Label_RemoveValue`
- `0x63d8`: `removeValue(event);`

## pseudocode

```c

```

## disassembly

```asm
0x61f0  ldarg.0
0x61f1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0x61f6  ldarg.0
0x61f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61fc  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x6201  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x6206  ldarg.0
0x6207  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x620c  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0x6211  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x6216  ldarg.0
0x6217  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x621c  ldstr    aStaticCsDialog// "/_static/cs/dialogs/kbsearch.js"
0x6221  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6226  ldarg.0
0x6227  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x622c  ldstr    aStaticControls_3// "/_static/_controls/lookup/lookup.js"
0x6231  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6236  ldarg.0
0x6237  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x623c  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x6241  ldarg.0
0x6242  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6247  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x624c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6251  ldc.i4.0
0x6252  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6257  ldarg.0
0x6258  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x625d  ldstr    aBhideemailbutt// "_bHideEmailButton"
0x6262  ldarg.0
0x6263  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6268  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x626d  ldstr    aHideemailbutto// "HideEmailButton"
0x6272  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6277  ldstr    aTrue// "true"
0x627c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6281  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x6286  ldarg.0
0x6287  ldarg.0
0x6288  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x628d  ldstr    aDialogKbsearch// "Dialog_KBSearch_Title"
0x6292  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6297  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x629c  ldarg.0
0x629d  ldarg.0
0x629e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x62a3  ldstr    aDialogKbsearch_0// "Dialog_KBSearch_Description"
0x62a8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x62ad  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x62b2  ldarg.0
0x62b3  ldstr    aKbarticle// "kbarticle"
0x62b8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x62bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x62c2  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x62c7  ldarg.0
0x62c8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Web.CS.KBSearchPage::crmGrid
0x62cd  ldstr    a7ad58fad40af4e// "{7AD58FAD-40AF-4E72-AC4E-DB8C82E1E62D}"
0x62d2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0x62d7  ldarg.0
0x62d8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Web.CS.KBSearchPage::crmGrid
0x62dd  ldstr    aCrmanswerRetri// "CRMAnswer.RetrieveBySubject"
0x62e2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_QueryApi(string)
0x62e7  ldarg.0
0x62e8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Web.CS.KBSearchPage::crmGrid
0x62ed  ldc.i4.0
0x62ee  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool)
0x62f3  ldarg.0
0x62f4  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Web.CS.KBSearchPage::crmGrid
0x62f9  ldc.i4.1
0x62fa  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_SuppressFetch(bool)
0x62ff  ldarg.0
0x6300  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Web.CS.KBSearchPage::crmGrid
0x6305  ldc.i4.1
0x6306  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_MaximumSelectableItems(int32)
0x630b  ldarg.0
0x630c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Web.CS.KBSearchPage::crmGrid
0x6311  ldstr    aDisabledblclic// "disableDblClick"
0x6316  ldstr    a1// "1"
0x631b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x6320  ldarg.0
0x6321  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Web.CS.KBSearchPage::crmGrid
0x6326  ldstr    aSubject// "subject"
0x632b  ldstr    asc_15D82// ""
0x6330  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x6335  ldarg.0
0x6336  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Web.CS.KBSearchPage::crmGrid
0x633b  ldstr    aStype// "stype"
0x6340  ldstr    asc_15D82// ""
0x6345  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x634a  ldarg.0
0x634b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Web.CS.KBSearchPage::crmGrid
0x6350  ldstr    aSvalue// "svalue"
0x6355  ldstr    asc_15D82// ""
0x635a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x635f  ldarg.0
0x6360  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Web.CS.KBSearchPage::crmGrid
0x6365  ldstr    aSsubject// "ssubject"
0x636a  ldstr    asc_15D82// ""
0x636f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x6374  ldarg.0
0x6375  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Web.CS.KBSearchPage::crmGrid
0x637a  ldstr    aSinflection// "sinflection"
0x637f  ldstr    asc_15D82// ""
0x6384  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x6389  ldarg.0
0x638a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x638f  ldc.i4.1
0x6390  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x6395  stloc.0
0x6396  ldarg.0
0x6397  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x639c  ldloc.0
0x639d  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::get_Item(int32)
0x63a2  ldstr    aButtonLabelAdd// "Button_Label_Add"
0x63a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string)
0x63ac  ldarg.0
0x63ad  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x63b2  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x63b7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x63bc  ldstr    aIslookup// "isLookup"
0x63c1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x63c6  brfalse.s loc_63E9
0x63c8  ldarg.0
0x63c9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x63ce  ldstr    aBtnremove// "btnRemove"
0x63d3  ldstr    aButtonLabelRem// "Button_Label_RemoveValue"
0x63d8  ldstr    aRemovevalueEve// "removeValue(event);"
0x63dd  ldc.i4.0
0x63de  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0x63e3  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0x63e8  pop
0x63e9  ldarg.0
0x63ea  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x63ef  ldc.i4.2
0x63f0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButtons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x63f5  ret
```
