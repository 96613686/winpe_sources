# Microsoft.Crm.Application.Components.PageHandlers.MailboxRecordPageHandler::ConfigureHeaderHandler

- ea: `0xd0eb0`
- end: `0xd10b7`
- name: `Microsoft.Crm.Application.Components.PageHandlers.MailboxRecordPageHandler::ConfigureHeaderHandler`
- size: `519`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xd0eb0`
- `0xd1fe0`
- `0xd2130`
- `0xd2160`
- `0xd2180`

## string_xrefs

- `0xd10ac`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xd1049`: `LOCID_TESTACCESS_ALREADYRUNNING`
- `0xd1054`: `EmailConnector.TestEmailAccess.Dialog.Message.TestAccessAlreadyRunning`
- `0xd1075`: `EmailConnector.TestEmailAccess.Dialog.Message.ExchangeSubscription`

## pseudocode

```c

```

## disassembly

```asm
0xd0eb0  ldarg.0
0xd0eb1  call     instance void Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureHeaderHandler()
0xd0eb6  ldc.i4.1
0xd0eb7  stloc.0
0xd0eb8  ldc.i4.0
0xd0eb9  stloc.1
0xd0eba  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xd0ebf  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xd0ec4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xd0ec9  ldstr    aId// "id"
0xd0ece  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd0ed3  brfalse  loc_D0F6D
0xd0ed8  ldloca.s 6
0xd0eda  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xd0edf  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xd0ee4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xd0ee9  ldstr    aId// "id"
0xd0eee  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd0ef3  call     instance void [mscorlib]System.Guid::.ctor(string)
0xd0ef8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache::Instance()
0xd0efd  ldloc.s  6
0xd0eff  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd0f04  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xd0f09  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xd0f0e  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData>::LookupEntry(void, var<u1>)
0xd0f13  stloc.s  7
0xd0f15  ldloc.s  7
0xd0f17  brfalse.s loc_D0F6D
0xd0f19  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerProfileCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerProfileCache::Instance()
0xd0f1e  ldloc.s  7
0xd0f20  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_EmailServerProfileId()
0xd0f25  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd0f2a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xd0f2f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xd0f34  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile>::LookupEntry(void, var<u1>)
0xd0f39  stloc.s  8
0xd0f3b  ldloc.s  8
0xd0f3d  brfalse.s loc_D0F53
0xd0f3f  ldloc.s  8
0xd0f41  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CredentialRetrievalMethod [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_IncomingCredentialRetrievalMethod()
0xd0f46  brfalse.s loc_D0F53
0xd0f48  ldloc.s  8
0xd0f4a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CredentialRetrievalMethod [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_OutgoingCredentialRetrievalMethod()
0xd0f4f  brfalse.s loc_D0F53
0xd0f51  ldc.i4.0
0xd0f52  stloc.0
0xd0f53  ldloc.s  8
0xd0f55  brfalse.s loc_D0F6D
0xd0f57  ldloc.s  8
0xd0f59  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_ServerType()
0xd0f5e  ldc.i4.2
0xd0f5f  beq.s    loc_D0F6B
0xd0f61  ldloc.s  8
0xd0f63  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_ServerType()
0xd0f68  ldc.i4.3
0xd0f69  bne.un.s loc_D0F6D
0xd0f6b  ldc.i4.1
0xd0f6c  stloc.1
0xd0f6d  ldc.i4.0
0xd0f6e  stloc.2
0xd0f6f  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xd0f74  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xd0f79  ldc.i4.2
0xd0f7a  ceq
0xd0f7c  stloc.3
0xd0f7d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xd0f82  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xd0f87  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SSSReliability()
0xd0f8c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd0f91  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd0f96  stloc.s  4
0xd0f98  ldarg.0
0xd0f99  call     instance class [System.Web]System.Web.HttpRequest Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0xd0f9e  brfalse.s loc_D0FB1
0xd0fa0  ldarg.0
0xd0fa1  call     instance class [System.Web]System.Web.HttpRequest Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0xd0fa6  callvirt instance bool [System.Web]System.Web.HttpRequest::get_IsSecureConnection()
0xd0fab  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AllowCredentialsEntry(bool)
0xd0fb0  stloc.2
0xd0fb1  ldarg.0
0xd0fb2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd0fb7  ldstr    aAllowEmailCred// "ALLOW_EMAIL_CREDENTIALS"
0xd0fbc  ldloc.2
0xd0fbd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xd0fc2  ldarg.0
0xd0fc3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd0fc8  ldstr    aCredentialUser// "CREDENTIAL_USERSPECIFIED"
0xd0fcd  ldloc.0
0xd0fce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xd0fd3  ldarg.0
0xd0fd4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd0fd9  ldstr    aBislivesku// "_bIsLiveSku"
0xd0fde  ldloc.3
0xd0fdf  brtrue.s loc_D0FE8
0xd0fe1  ldstr    aFalse// "false"
0xd0fe6  br.s     loc_D0FED
0xd0fe8  ldstr    aTrue_0// "true"
0xd0fed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xd0ff2  ldarg.0
0xd0ff3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd0ff8  ldstr    aIsSssreliabili// "IS_SSSRELIABILITY_FEATUREENABLED"
0xd0ffd  ldloc.s  4
0xd0fff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xd1004  ldloc.3
0xd1005  brfalse.s loc_D101D
0xd1007  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0xd100c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd1011  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xd1016  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0xd101b  br.s     loc_D101E
0xd101d  ldc.i4.0
0xd101e  stloc.s  5
0xd1020  ldarg.0
0xd1021  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd1026  ldstr    aIsLiveosdp// "IS_LIVEOSDP"
0xd102b  ldloc.s  5
0xd102d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xd1032  ldarg.0
0xd1033  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd1038  ldstr    aIsExchangeonpr// "IS_EXCHANGEONPREMONCRMONLINE"
0xd103d  ldloc.1
0xd103e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xd1043  ldarg.0
0xd1044  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd1049  ldstr    aLocidTestacces// "LOCID_TESTACCESS_ALREADYRUNNING"
0xd104e  ldarg.0
0xd104f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd1054  ldstr    aEmailconnector_72// "EmailConnector.TestEmailAccess.Dialog.M"...
0xd1059  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd105e  ldc.i4.0
0xd105f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd1064  ldarg.0
0xd1065  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd106a  ldstr    aLocidTestexonl_0// "LOCID_TESTEXONLINE_SUBSCRIPTION"
0xd106f  ldarg.0
0xd1070  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd1075  ldstr    aEmailconnector_73// "EmailConnector.TestEmailAccess.Dialog.M"...
0xd107a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd107f  ldc.i4.0
0xd1080  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd1085  ldarg.0
0xd1086  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd108b  ldstr    aLocidNoemailad// "LOCID_NOEMAILADDRESS_MAILBOX"
0xd1090  ldarg.0
0xd1091  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd1096  ldstr    aMailboxSendema// "Mailbox.SendEmailToTenantAdmins.Dialog."...
0xd109b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd10a0  ldc.i4.0
0xd10a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd10a6  ldarg.0
0xd10a7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd10ac  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0xd10b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xd10b6  ret
```
