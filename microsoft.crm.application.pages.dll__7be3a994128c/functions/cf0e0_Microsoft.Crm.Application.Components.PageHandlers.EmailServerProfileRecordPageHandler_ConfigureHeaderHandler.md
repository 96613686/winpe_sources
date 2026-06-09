# Microsoft.Crm.Application.Components.PageHandlers.EmailServerProfileRecordPageHandler::ConfigureHeaderHandler

- ea: `0xcf0e0`
- end: `0xcf463`
- name: `Microsoft.Crm.Application.Components.PageHandlers.EmailServerProfileRecordPageHandler::ConfigureHeaderHandler`
- size: `899`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xcf0e0`
- `0xd1fe0`
- `0xd2130`
- `0xd2160`
- `0xd2180`

## string_xrefs

- `0xcf458`: `MailboxService`
- `0xcf0ec`: `EmailServerProfileService`
- `0xcf20d`: `FILTER_EMAIL_PROFILE_DATA_FOR_DELEGATE_ACCESS`
- `0xcf263`: `EmailConnector.TestEmailAccess.Dialog.Message.NoActiveMailboxAssociated`
- `0xcf34b`: `Ribbon.emailserverprofile.TestExchangeServerProfile.TestExchangeAlreadyRunning`
- `0xcf36c`: `Ribbon.emailserverprofile.TestExchangeOnlineProfile.TestExchangeAlreadyRunning`
- `0xcf382`: `LOCID_INCOMING_HEADERSTRING`
- `0xcf38d`: `Emailserverprofile.TestExchangeServerProfile.HeaderForIncomingConnection`

## pseudocode

```c

```

## disassembly

```asm
0xcf0e0  ldarg.0
0xcf0e1  call     instance void Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureHeaderHandler()
0xcf0e6  ldarg.0
0xcf0e7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf0ec  ldstr    aEmailserverpro_5// "EmailServerProfileService"
0xcf0f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xcf0f6  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xcf0fb  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xcf100  ldc.i4.2
0xcf101  ceq
0xcf103  stloc.0
0xcf104  ldarg.0
0xcf105  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf10a  ldstr    aBislivesku// "_bIsLiveSku"
0xcf10f  ldloc.0
0xcf110  brtrue.s loc_CF119
0xcf112  ldstr    aFalse// "false"
0xcf117  br.s     loc_CF11E
0xcf119  ldstr    aTrue_0// "true"
0xcf11e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcf123  ldarg.0
0xcf124  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf129  ldstr    aSaveandnewenab// "_saveAndNewEnabled"
0xcf12e  ldc.i4.0
0xcf12f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xcf134  ldc.i4.0
0xcf135  stloc.1
0xcf136  ldarg.0
0xcf137  call     instance class [System.Web]System.Web.HttpRequest Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0xcf13c  brfalse.s loc_CF14F
0xcf13e  ldarg.0
0xcf13f  call     instance class [System.Web]System.Web.HttpRequest Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0xcf144  callvirt instance bool [System.Web]System.Web.HttpRequest::get_IsSecureConnection()
0xcf149  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AllowCredentialsEntry(bool)
0xcf14e  stloc.1
0xcf14f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xcf154  ldstr    aEcallownonssle// "ECAllowNonSSLEmail"
0xcf159  callvirt T0x2B00002E
0xcf15e  stloc.2
0xcf15f  ldloca.s 2
0xcf161  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xcf166  brfalse.s loc_CF174
0xcf168  ldloca.s 2
0xcf16a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xcf16f  ldc.i4.0
0xcf170  ceq
0xcf172  br.s     loc_CF175
0xcf174  ldc.i4.1
0xcf175  stloc.3
0xcf176  ldloc.0
0xcf177  brfalse.s loc_CF18F
0xcf179  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0xcf17e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcf183  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xcf188  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0xcf18d  br.s     loc_CF190
0xcf18f  ldc.i4.0
0xcf190  stloc.s  4
0xcf192  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0xcf197  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcf19c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xcf1a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcf1a6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xcf1ab  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xcf1b0  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0xcf1b5  stloc.s  5
0xcf1b7  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xcf1bc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xcf1c1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_HybridSSS()
0xcf1c6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcf1cb  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcf1d0  stloc.s  6
0xcf1d2  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xcf1d7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xcf1dc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ReverseHybridSSS()
0xcf1e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcf1e6  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcf1eb  stloc.s  7
0xcf1ed  ldarg.0
0xcf1ee  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf1f3  ldstr    aFilterEmailPro// "FILTER_EMAIL_PROFILE_DATA_FOR_OSDP_ORG"
0xcf1f8  ldloc.s  5
0xcf1fa  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsEmailServerProfileContentFilteringEnabled()
0xcf1ff  ldloc.s  4
0xcf201  and
0xcf202  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xcf207  ldarg.0
0xcf208  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf20d  ldstr    aFilterEmailPro_0// "FILTER_EMAIL_PROFILE_DATA_FOR_DELEGATE_"...
0xcf212  ldloc.s  5
0xcf214  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsDelegateAccessEnabled()
0xcf219  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xcf21e  ldarg.0
0xcf21f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf224  ldstr    aIsLiveosdp// "IS_LIVEOSDP"
0xcf229  ldloc.s  4
0xcf22b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xcf230  ldarg.0
0xcf231  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf236  ldstr    aAllowEmailCred// "ALLOW_EMAIL_CREDENTIALS"
0xcf23b  ldloc.1
0xcf23c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xcf241  ldarg.0
0xcf242  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf247  ldstr    aAllowSslProfil// "ALLOW_SSL_PROFILE_ONLY"
0xcf24c  ldloc.3
0xcf24d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xcf252  ldarg.0
0xcf253  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf258  ldstr    aLocidNoMailbox// "LOCID_NO_MAILBOX_ASSOCIATED"
0xcf25d  ldarg.0
0xcf25e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf263  ldstr    aEmailconnector_71// "EmailConnector.TestEmailAccess.Dialog.M"...
0xcf268  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf26d  ldc.i4.0
0xcf26e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf273  ldarg.0
0xcf274  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf279  ldstr    aEspOlddatemess// "ESP_OLDDATEMESSAGE"
0xcf27e  ldarg.0
0xcf27f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf284  ldstr    aEmailserverpro_6// "EmailServerProfile.ProcessEmailsFrom.Ol"...
0xcf289  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf28e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcf293  ldarg.0
0xcf294  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf299  ldstr    aEspOlddatetitl// "ESP_OLDDATETITLE"
0xcf29e  ldarg.0
0xcf29f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf2a4  ldstr    aEmailserverpro_7// "EmailServerProfile.ProcessEmailsFrom.Ol"...
0xcf2a9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf2ae  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcf2b3  ldarg.0
0xcf2b4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf2b9  ldstr    aIsHybridsssFea// "IS_HYBRIDSSS_FEATUREEENABLED"
0xcf2be  ldloc.s  6
0xcf2c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xcf2c5  ldarg.0
0xcf2c6  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf2cb  ldstr    aIsReversehybri// "IS_REVERSEHYBRIDSSS_FEATUREEENABLED"
0xcf2d0  ldloc.s  7
0xcf2d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xcf2d7  ldarg.0
0xcf2d8  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf2dd  ldstr    aLocidApplymlbo// "LOCID_APPLYMLBOX_MULTIPLEERRORS"
0xcf2e2  ldarg.0
0xcf2e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf2e8  ldstr    aEmailconnector// "EmailConnector.ApplyMailboxDefaults.Mul"...
0xcf2ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf2f2  ldc.i4.0
0xcf2f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf2f8  ldarg.0
0xcf2f9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf2fe  ldstr    aLocidUsernameT// "LOCID_USERNAME_TOOLTIP"
0xcf303  ldarg.0
0xcf304  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf309  ldstr    aEmailserverpro_8// "Emailserverprofile.TestExchangeServerPr"...
0xcf30e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf313  ldc.i4.0
0xcf314  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf319  ldarg.0
0xcf31a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf31f  ldstr    aLocidPasswordT// "LOCID_PASSWORD_TOOLTIP"
0xcf324  ldarg.0
0xcf325  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf32a  ldstr    aEmailserverpro_9// "Emailserverprofile.TestExchangeServerPr"...
0xcf32f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf334  ldc.i4.0
0xcf335  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf33a  ldarg.0
0xcf33b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf340  ldstr    aLocidTestexcha// "LOCID_TESTEXCHANGE_STILLRUNNING"
0xcf345  ldarg.0
0xcf346  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf34b  ldstr    aRibbonEmailser_0// "Ribbon.emailserverprofile.TestExchangeS"...
0xcf350  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf355  ldc.i4.0
0xcf356  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf35b  ldarg.0
0xcf35c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf361  ldstr    aLocidTestexonl// "LOCID_TESTEXONLINE_STILLRUNNING"
0xcf366  ldarg.0
0xcf367  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf36c  ldstr    aRibbonEmailser_1// "Ribbon.emailserverprofile.TestExchangeO"...
0xcf371  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf376  ldc.i4.0
0xcf377  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf37c  ldarg.0
0xcf37d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf382  ldstr    aLocidIncomingH// "LOCID_INCOMING_HEADERSTRING"
0xcf387  ldarg.0
0xcf388  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf38d  ldstr    aEmailserverpro_10// "Emailserverprofile.TestExchangeServerPr"...
0xcf392  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf397  ldc.i4.0
0xcf398  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf39d  ldarg.0
0xcf39e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf3a3  ldstr    aLocidProfileEx// "LOCID_PROFILE_EXCHONPREMHYBRID"
0xcf3a8  ldarg.0
0xcf3a9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf3ae  ldstr    aRibbonHomepage// "Ribbon.HomepageGrid.emailserverprofile."...
0xcf3b3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf3b8  ldc.i4.0
0xcf3b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf3be  ldarg.0
0xcf3bf  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf3c4  ldstr    aLocidProfileEx_0// "LOCID_PROFILE_EXCHONLINEHYBRID"
0xcf3c9  ldarg.0
0xcf3ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf3cf  ldstr    aRibbonHomepage_0// "Ribbon.HomepageGrid.emailserverprofile."...
0xcf3d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf3d9  ldc.i4.0
0xcf3da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf3df  ldarg.0
0xcf3e0  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf3e5  ldstr    aLocidProfileEx_1// "LOCID_PROFILE_EXCHANGEONLINE"
0xcf3ea  ldarg.0
0xcf3eb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf3f0  ldstr    aRibbonHomepage_1// "Ribbon.HomepageGrid.emailserverprofile."...
0xcf3f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf3fa  ldc.i4.0
0xcf3fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf400  ldarg.0
0xcf401  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf406  ldstr    aLocidProfileEx_2// "LOCID_PROFILE_EXCHANGEONPREM"
0xcf40b  ldarg.0
0xcf40c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf411  ldstr    aRibbonHomepage_2// "Ribbon.HomepageGrid.emailserverprofile."...
0xcf416  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf41b  ldc.i4.0
0xcf41c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf421  ldarg.0
0xcf422  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf427  ldstr    aLocidProfileOt// "LOCID_PROFILE_OTHER"
0xcf42c  ldarg.0
0xcf42d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcf432  ldstr    aRibbonHomepage_3// "Ribbon.HomepageGrid.emailserverprofile."...
0xcf437  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcf43c  ldc.i4.0
0xcf43d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf442  ldarg.0
0xcf443  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf448  ldstr    aStaticEntities// "/_static/entities/EmailConnector.js"
0xcf44d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xcf452  ldarg.0
0xcf453  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xcf458  ldstr    aMailboxservice// "MailboxService"
0xcf45d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xcf462  ret
```
