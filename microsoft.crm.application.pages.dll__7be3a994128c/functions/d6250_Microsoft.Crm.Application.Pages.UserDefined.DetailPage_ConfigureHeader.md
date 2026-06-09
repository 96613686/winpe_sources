# Microsoft.Crm.Application.Pages.UserDefined.DetailPage::ConfigureHeader

- ea: `0xd6250`
- end: `0xd6507`
- name: `Microsoft.Crm.Application.Pages.UserDefined.DetailPage::ConfigureHeader`
- size: `695`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0xcaf40`
- `0xcb3f0`
- `0xd6250`
- `0xd6580`
- `0xd65e0`

## string_xrefs

- `0xd64d6`: `Sys.Application.findComponent('crmPageManager').applicationLoadHandler();`
- `0xd62ca`: `SystemCustomization.EntityUtil.Messages.ConfirmEntityDelete`
- `0xd6267`: `SystemCustomization.EntityUtil.Messages.CannotUpdateSystemEntityIcons`
- `0xd6288`: `SystemCustomization.EntityUtil.Messages.CannotDeleteSystemEntity`
- `0xd64ec`: `/_static/_common/scripts/CrmServiceProxyFramework.js`
- `0xd64fc`: `/_static/_common/scripts/CrmServiceProxy.js`

## pseudocode

```c

```

## disassembly

```asm
0xd6250  ldarg.0
0xd6251  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigureHeader()
0xd6256  ldarg.0
0xd6257  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd625c  ldstr    aLocidEntutlCan// "LOCID_ENTUTL_CANTUPDSYSENTICN"
0xd6261  ldarg.0
0xd6262  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd6267  ldstr    aSystemcustomiz_4// "SystemCustomization.EntityUtil.Messages"...
0xd626c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6271  ldc.i4.0
0xd6272  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd6277  ldarg.0
0xd6278  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd627d  ldstr    aLocidEntutlCan_0// "LOCID_ENTUTL_CANTDELSYSENT"
0xd6282  ldarg.0
0xd6283  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd6288  ldstr    aSystemcustomiz_5// "SystemCustomization.EntityUtil.Messages"...
0xd628d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6292  ldc.i4.0
0xd6293  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd6298  ldarg.0
0xd6299  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd629e  ldstr    aLocidEntutlCan_1// "LOCID_ENTUTL_CANTPUBLISHENT"
0xd62a3  ldarg.0
0xd62a4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd62a9  ldstr    aSystemcustomiz_6// "SystemCustomization.EntityUtil.Messages"...
0xd62ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd62b3  ldc.i4.0
0xd62b4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd62b9  ldarg.0
0xd62ba  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd62bf  ldstr    aLocidEntutlCon// "LOCID_ENTUTL_CONFIRMDEL"
0xd62c4  ldarg.0
0xd62c5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd62ca  ldstr    aSystemcustomiz_0// "SystemCustomization.EntityUtil.Messages"...
0xd62cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd62d4  ldc.i4.0
0xd62d5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd62da  ldarg.0
0xd62db  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd62e0  ldstr    aLocidEntutlCre// "LOCID_ENTUTL_CREATINGENT"
0xd62e5  ldarg.0
0xd62e6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd62eb  ldstr    aSystemcustomiz_7// "SystemCustomization.EntityUtil.Messages"...
0xd62f0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd62f5  ldc.i4.0
0xd62f6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd62fb  ldarg.0
0xd62fc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd6301  ldstr    aLocidEntutlUpd// "LOCID_ENTUTL_UPDATINGENT"
0xd6306  ldarg.0
0xd6307  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd630c  ldstr    aSystemcustomiz_8// "SystemCustomization.EntityUtil.Messages"...
0xd6311  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6316  ldc.i4.0
0xd6317  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd631c  ldarg.0
0xd631d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd6322  ldstr    aLocidEntutlDel// "LOCID_ENTUTL_DELETINGENT"
0xd6327  ldarg.0
0xd6328  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd632d  ldstr    aSystemcustomiz_9// "SystemCustomization.EntityUtil.Messages"...
0xd6332  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6337  ldc.i4.0
0xd6338  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd633d  ldarg.0
0xd633e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd6343  ldstr    aLocidEntutlPub// "LOCID_ENTUTL_PUBLISHINGENT"
0xd6348  ldarg.0
0xd6349  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd634e  ldstr    aSystemcustomiz_10// "SystemCustomization.EntityUtil.Messages"...
0xd6353  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6358  ldc.i4.0
0xd6359  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd635e  ldarg.0
0xd635f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd6364  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0xd6369  ldarg.0
0xd636a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd636f  ldstr    aSystemcustomiz_11// "SystemCustomization.Validation.Errors.C"...
0xd6374  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6379  ldc.i4.0
0xd637a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd637f  ldarg.0
0xd6380  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd6385  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0xd638a  ldarg.0
0xd638b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd6390  ldstr    aSystemcustomiz_12// "SystemCustomization.Validation.Errors.C"...
0xd6395  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd639a  ldc.i4.0
0xd639b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd63a0  ldarg.0
0xd63a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd63a6  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0xd63ab  ldarg.0
0xd63ac  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd63b1  ldstr    aSystemcustomiz_13// "SystemCustomization.Validation.Errors.C"...
0xd63b6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd63bb  ldc.i4.0
0xd63bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd63c1  ldarg.0
0xd63c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd63c7  ldstr    aSystemcustomiz_14// "SystemCustomization"
0xd63cc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xd63d1  ldarg.0
0xd63d2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd63d7  ldstr    aSystemcustomiz_14// "SystemCustomization"
0xd63dc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathAshxWebService(string)
0xd63e1  ldarg.0
0xd63e2  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0xd63e7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::RenderYammerGlobalVariables()
0xd63ec  ldarg.0
0xd63ed  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0xd63f2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::RenderActionHubGlobalVariables()
0xd63f7  ldarg.0
0xd63f8  call     instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::get_HandlerEntityTypeCode()
0xd63fd  ldc.i4.8
0xd63fe  bne.un.s loc_D6406
0xd6400  ldarg.0
0xd6401  call     instance void Microsoft.Crm.Application.Pages.UserDefined.DetailPage::AddHcVariableIsYammerEnabledForTargetUser()
0xd6406  ldarg.0
0xd6407  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Pages.UserDefined.DetailPage::get_CurrentEntity()
0xd640c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xd6411  stloc.0
0xd6412  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0xd6417  brfalse.s loc_D648F
0xd6419  ldloc.0
0xd641a  ldstr    aAppointment// "appointment"
0xd641f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6424  brtrue.s loc_D645A
0xd6426  ldloc.0
0xd6427  ldstr    aRecurringappoi// "recurringappointmentmaster"
0xd642c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6431  brtrue.s loc_D645A
0xd6433  ldloc.0
0xd6434  ldstr    aEmail// "email"
0xd6439  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd643e  brtrue.s loc_D645A
0xd6440  ldloc.0
0xd6441  ldstr    aTask// "task"
0xd6446  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd644b  brtrue.s loc_D645A
0xd644d  ldloc.0
0xd644e  ldstr    aContact// "contact"
0xd6453  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6458  brfalse.s loc_D648F
0xd645a  ldarg.0
0xd645b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Pages.UserDefined.DetailPage::get_CurrentEntity()
0xd6460  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xd6465  call     class Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderFactory::GetConfigHeader(int32 typeCode)
0xd646a  ldarg.0
0xd646b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xd6470  ldarg.0
0xd6471  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Pages.UserDefined.DetailPage::get_CurrentEntity()
0xd6476  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xd647b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd6480  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd6485  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xd648a  callvirt instance void Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader::ConfigHeader(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager header, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0xd648f  ldarg.0
0xd6490  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::crmHeader
0xd6495  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header
0xd649a  ldc.i4.1
0xd649b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header::set_DeferAllScripts(bool)
0xd64a0  ldarg.0
0xd64a1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::crmFooter
0xd64a6  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Footer
0xd64ab  dup
0xd64ac  ldc.i4.1
0xd64ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Footer::set_ChunkScripts(bool)
0xd64b2  ldc.i4.1
0xd64b3  newarr   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock
0xd64b8  dup
0xd64b9  ldc.i4.0
0xd64ba  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0xd64bf  dup
0xd64c0  ldstr    aInitpagemanage// "InitPageManager"
0xd64c5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string)
0xd64ca  dup
0xd64cb  ldc.i4   0x12C
0xd64d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32)
0xd64d5  dup
0xd64d6  ldstr    aSysApplication// "Sys.Application.findComponent('crmPageM"...
0xd64db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string)
0xd64e0  stelem.ref
0xd64e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock[])
0xd64e6  ldarg.0
0xd64e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd64ec  ldstr    aStaticCommonSc_34// "/_static/_common/scripts/CrmServiceProx"...
0xd64f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xd64f6  ldarg.0
0xd64f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd64fc  ldstr    aStaticCommonSc_39// "/_static/_common/scripts/CrmServiceProx"...
0xd6501  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xd6506  ret
```
