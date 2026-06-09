# Microsoft.Crm.Web.Tools.DocumentManagement.CreateDocumentLibrary::ConfigureHeader

- ea: `0x7a120`
- end: `0x7a2e6`
- name: `Microsoft.Crm.Web.Tools.DocumentManagement.CreateDocumentLibrary::ConfigureHeader`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x7a171`: `DocumentManagement.CreateFolder.GenericError`
- `0x7a187`: `LOCID_SHAREPOINT_ACCESS_DENIED`
- `0x7a192`: `DocumentManagement.AddLocation.AccessDenied`
- `0x7a279`: `DocumentManagement.Settings.AlternateAccessMappingError`
- `0x7a1b3`: `Web.Tools.DocumentManagement.SettingsPage.CreateDL.CancelConfirm`
- `0x7a1c9`: `LOCID_SP_CREATEDL_FAILED`
- `0x7a1ea`: `LOCID_SP_CREATEDL_SUCCEEDED`
- `0x7a20b`: `LOCID_SP_CREATEDL_ALREADYEXIST`
- `0x7a216`: `Web.Tools.DocumentManagement.SettingsPage.CreateDL.Status.AlreadyExist`
- `0x7a22c`: `LOCID_SP_CREATEDL_INPROGRESS`
- `0x7a237`: `Web.Tools.DocumentManagement.SettingsPage.CreateDL.Status.InProgress`
- `0x7a24d`: `LOCID_SP_CREATEDL_CANCELED`
- `0x7a258`: `Web.Tools.DocumentManagement.SettingsPage.CreateDL.Status.Canceled`
- `0x7a28f`: `LOCID_S2S_CREATEDL_CONFIRM_MSG0`
- `0x7a29a`: `DocumentManagement.CreateDocLib.ConfirmMessage_0`
- `0x7a2b0`: `LOCID_S2S_CREATEDL_CONFIRM_MSG1`
- `0x7a2bb`: `DocumentManagement.CreateDocLib.ConfirmMessage_1`

## pseudocode

```c

```

## disassembly

```asm
0x7a120  ldarg.0
0x7a121  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a126  ldstr    aStaticEntities_2// "/_static/Entities/DocumentManagement.js"
0x7a12b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a130  ldarg.0
0x7a131  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a136  ldstr    aStaticToolsDoc_4// "/_static/tools/documentmanagement/scrip"...
0x7a13b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a140  ldarg.0
0x7a141  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a146  ldstr    aStaticToolsDoc_3// "/_static/tools/documentmanagement/scrip"...
0x7a14b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a150  ldarg.0
0x7a151  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a156  ldstr    aToolsDocumentm_1// "/tools/documentmanagement/documentmanag"...
0x7a15b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7a160  ldarg.0
0x7a161  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a166  ldstr    aLocidGenericMe// "LOCID_GENERIC_MESSAGE"
0x7a16b  ldarg.0
0x7a16c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7a171  ldstr    aDocumentmanage_5// "DocumentManagement.CreateFolder.Generic"...
0x7a176  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a17b  ldc.i4.0
0x7a17c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a181  ldarg.0
0x7a182  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a187  ldstr    aLocidSharepoin// "LOCID_SHAREPOINT_ACCESS_DENIED"
0x7a18c  ldarg.0
0x7a18d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7a192  ldstr    aDocumentmanage_8// "DocumentManagement.AddLocation.AccessDe"...
0x7a197  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a19c  ldc.i4.0
0x7a19d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a1a2  ldarg.0
0x7a1a3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a1a8  ldstr    aLocidSpCancelc// "LOCID_SP_CANCELCONFIRM_MESSAGE"
0x7a1ad  ldarg.0
0x7a1ae  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7a1b3  ldstr    aWebToolsDocume_40// "Web.Tools.DocumentManagement.SettingsPa"...
0x7a1b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a1bd  ldc.i4.0
0x7a1be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a1c3  ldarg.0
0x7a1c4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a1c9  ldstr    aLocidSpCreated// "LOCID_SP_CREATEDL_FAILED"
0x7a1ce  ldarg.0
0x7a1cf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7a1d4  ldstr    aDialogSharepoi_4// "Dialog_SharePoint_Site_Validation_Failu"...
0x7a1d9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a1de  ldc.i4.0
0x7a1df  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a1e4  ldarg.0
0x7a1e5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a1ea  ldstr    aLocidSpCreated_0// "LOCID_SP_CREATEDL_SUCCEEDED"
0x7a1ef  ldarg.0
0x7a1f0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7a1f5  ldstr    aDialogSharepoi_3// "Dialog_SharePoint_Site_Validation_Succe"...
0x7a1fa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a1ff  ldc.i4.0
0x7a200  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a205  ldarg.0
0x7a206  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a20b  ldstr    aLocidSpCreated_1// "LOCID_SP_CREATEDL_ALREADYEXIST"
0x7a210  ldarg.0
0x7a211  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7a216  ldstr    aWebToolsDocume_41// "Web.Tools.DocumentManagement.SettingsPa"...
0x7a21b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a220  ldc.i4.0
0x7a221  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a226  ldarg.0
0x7a227  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a22c  ldstr    aLocidSpCreated_2// "LOCID_SP_CREATEDL_INPROGRESS"
0x7a231  ldarg.0
0x7a232  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7a237  ldstr    aWebToolsDocume_42// "Web.Tools.DocumentManagement.SettingsPa"...
0x7a23c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a241  ldc.i4.0
0x7a242  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a247  ldarg.0
0x7a248  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a24d  ldstr    aLocidSpCreated_3// "LOCID_SP_CREATEDL_CANCELED"
0x7a252  ldarg.0
0x7a253  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7a258  ldstr    aWebToolsDocume_43// "Web.Tools.DocumentManagement.SettingsPa"...
0x7a25d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a262  ldc.i4.0
0x7a263  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a268  ldarg.0
0x7a269  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a26e  ldstr    aLocidDocmAamEr// "LOCID_DOCM_AAM_ERROR"
0x7a273  ldarg.0
0x7a274  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7a279  ldstr    aDocumentmanage_9// "DocumentManagement.Settings.AlternateAc"...
0x7a27e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a283  ldc.i4.0
0x7a284  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a289  ldarg.0
0x7a28a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a28f  ldstr    aLocidS2sCreate// "LOCID_S2S_CREATEDL_CONFIRM_MSG0"
0x7a294  ldarg.0
0x7a295  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7a29a  ldstr    aDocumentmanage_18// "DocumentManagement.CreateDocLib.Confirm"...
0x7a29f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a2a4  ldc.i4.0
0x7a2a5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a2aa  ldarg.0
0x7a2ab  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a2b0  ldstr    aLocidS2sCreate_0// "LOCID_S2S_CREATEDL_CONFIRM_MSG1"
0x7a2b5  ldarg.0
0x7a2b6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7a2bb  ldstr    aDocumentmanage_19// "DocumentManagement.CreateDocLib.Confirm"...
0x7a2c0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a2c5  ldc.i4.0
0x7a2c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a2cb  ldarg.0
0x7a2cc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a2d1  ldstr    aLocidDocmLangi// "LOCID_DOCM_LANGID"
0x7a2d6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x7a2db  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x7a2e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7a2e5  ret
```
