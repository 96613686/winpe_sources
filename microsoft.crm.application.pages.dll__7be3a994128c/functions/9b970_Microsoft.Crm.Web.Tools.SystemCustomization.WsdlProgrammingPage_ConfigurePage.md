# Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::ConfigurePage

- ea: `0x9b970`
- end: `0x9bcb3`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::ConfigurePage`
- size: `835`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x9b970`

## string_xrefs

- `0x9ba08`: `SystemCustomization.WsdlProgramming.CrmDiscoveryServiceTitle`
- `0x9ba1e`: `SystemCustomization.WsdlProgramming.CrmDiscoveryServiceWebAPITitle`
- `0x9ba34`: `SystemCustomization.WsdlProgramming.CrmServiceTitle`
- `0x9ba4a`: `SystemCustomization.WsdlProgramming.OpenDataServiceTitle`
- `0x9ba60`: `SystemCustomization.WsdlProgramming.ODataV4ServiceTitle`
- `0x9ba76`: `SystemCustomization.WsdlProgramming.ServiceRootUrl`
- `0x9bace`: `SystemCustomization.WsdlProgramming.ODataV4EndpointDescriptionSeeMoreLink`
- `0x9bae4`: `SystemCustomization.WsdlProgramming.OrganizationServiceEndpointDescriptionSeeMoreLink`
- `0x9bafa`: `SystemCustomization.WsdlProgramming.InstanceReferenceInformationDescriptionSeeMoreLink`
- `0x9bb10`: `SystemCustomization.WsdlProgramming.DiscoveryServiceDescriptionSeeMoreLink`
- `0x9bb26`: `SystemCustomization.WsdlProgramming.DiscoveryServiceWebAPIDescriptionSeeMoreLink`
- `0x9bb3c`: `SystemCustomization.WsdlProgramming.ODataV4EndpointDescriptionSeeMoreLinkText`
- `0x9bb52`: `SystemCustomization.WsdlProgramming.OrganizationServiceEndpointDescriptionSeeMoreLinkText`
- `0x9bb68`: `SystemCustomization.WsdlProgramming.InstanceReferenceInformationDescriptionSeeMoreLinkText`
- `0x9bb7e`: `SystemCustomization.WsdlProgramming.DiscoveryServiceDescriptionSeeMoreLinkText`
- `0x9bb94`: `SystemCustomization.WsdlProgramming.DiscoveryServiceWebAPIDescriptionSeeMoreLinkText`
- `0x9bbaa`: `SystemCustomization.WsdlProgramming.DeveloperOverviewLink`
- `0x9bbc0`: `SystemCustomization.WsdlProgramming.DeveloperCenterLink`
- `0x9bbd6`: `SystemCustomization.WsdlProgramming.DeveloperForumsLink`
- `0x9bbec`: `SystemCustomization.WsdlProgramming.SDKNugetPackagesLink`
- `0x9bc02`: `SystemCustomization.WsdlProgramming.SDKDownloadLink`
- `0x9bc18`: `SystemCustomization.WsdlProgramming.SampleCodeLink`
- `0x9bc2e`: `SystemCustomization.WsdlProgramming.DeveloperOverviewLinkTitle`
- `0x9bc44`: `SystemCustomization.WsdlProgramming.DeveloperCenterLinkTitle`
- `0x9bc5a`: `SystemCustomization.WsdlProgramming.DeveloperForumsLinkTitle`
- `0x9bc70`: `SystemCustomization.WsdlProgramming.SDKNugetPackagesLinkTitle`
- `0x9bc86`: `SystemCustomization.WsdlProgramming.SDKDownloadLinkTitle`
- `0x9bc9c`: `SystemCustomization.WsdlProgramming.SampleCodeLinkTitle`

## pseudocode

```c

```

## disassembly

```asm
0x9b970  ldarg.0
0x9b971  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9b976  ldstr    aToolsSystemcus_4// "/Tools/SystemCustomization/Styles/showu"...
0x9b97b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9b980  ldarg.0
0x9b981  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9b986  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x9b98b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9b990  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9b995  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckCustomizationPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9b99a  brtrue.s loc_9B9AD
0x9b99c  ldc.i4   0x80040277
0x9b9a1  ldc.i4.0
0x9b9a2  newarr   [mscorlib]System.Object
0x9b9a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x9b9ac  throw
0x9b9ad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9b9b2  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_AuthenticationType()
0x9b9b7  stloc.0
0x9b9b8  ldarg.0
0x9b9b9  ldloc.0
0x9b9ba  ldc.i4.1
0x9b9bb  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::Create(int32, bool)
0x9b9c0  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::_endpointProvider
0x9b9c5  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x9b9ca  ldarg.0
0x9b9cb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x9b9d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x9b9d5  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationName(valuetype [mscorlib]System.Guid)
0x9b9da  stloc.1
0x9b9db  ldarg.0
0x9b9dc  ldloc.1
0x9b9dd  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::organizationUniqueName
0x9b9e2  ldarg.0
0x9b9e3  ldarg.0
0x9b9e4  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x9b9e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x9b9ee  stloc.2
0x9b9ef  ldloca.s 2
0x9b9f1  constrained. [mscorlib]System.Guid
0x9b9f7  callvirt instance string [mscorlib]System.Object::ToString()
0x9b9fc  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::organizationId
0x9ba01  ldarg.0
0x9ba02  ldarg.0
0x9ba03  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ba08  ldstr    aSystemcustomiz_258// "SystemCustomization.WsdlProgramming.Crm"...
0x9ba0d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ba12  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::discoveryServiceName
0x9ba17  ldarg.0
0x9ba18  ldarg.0
0x9ba19  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ba1e  ldstr    aSystemcustomiz_259// "SystemCustomization.WsdlProgramming.Crm"...
0x9ba23  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ba28  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::discoveryServiceWebAPIName
0x9ba2d  ldarg.0
0x9ba2e  ldarg.0
0x9ba2f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ba34  ldstr    aSystemcustomiz_260// "SystemCustomization.WsdlProgramming.Crm"...
0x9ba39  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ba3e  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::organizationServiceName
0x9ba43  ldarg.0
0x9ba44  ldarg.0
0x9ba45  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ba4a  ldstr    aSystemcustomiz_261// "SystemCustomization.WsdlProgramming.Ope"...
0x9ba4f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ba54  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::organizationDataServiceName
0x9ba59  ldarg.0
0x9ba5a  ldarg.0
0x9ba5b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ba60  ldstr    aSystemcustomiz_262// "SystemCustomization.WsdlProgramming.ODa"...
0x9ba65  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ba6a  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::odataV4ServiceName
0x9ba6f  ldarg.0
0x9ba70  ldarg.0
0x9ba71  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ba76  ldstr    aSystemcustomiz_263// "SystemCustomization.WsdlProgramming.Ser"...
0x9ba7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ba80  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::odataV4ServiceRootUrl
0x9ba85  ldarg.0
0x9ba86  ldarg.0
0x9ba87  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ba8c  ldstr    aSystemcustomiz_264// "SystemCustomization.WsdlProgramming.Dow"...
0x9ba91  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ba96  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::downloadWsdl
0x9ba9b  ldarg.0
0x9ba9c  ldarg.0
0x9ba9d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9baa2  ldstr    aSystemcustomiz_265// "SystemCustomization.WsdlProgramming.Dow"...
0x9baa7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9baac  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::downloadCsdl
0x9bab1  ldarg.0
0x9bab2  ldarg.0
0x9bab3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bab8  ldstr    aSystemcustomiz_266// "SystemCustomization.WsdlProgramming.Dow"...
0x9babd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bac2  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::downloadODataV4Metadata
0x9bac7  ldarg.0
0x9bac8  ldarg.0
0x9bac9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bace  ldstr    aSystemcustomiz_267// "SystemCustomization.WsdlProgramming.ODa"...
0x9bad3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bad8  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::oDataV4EndpointDescriptionSeeMoreLink
0x9badd  ldarg.0
0x9bade  ldarg.0
0x9badf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bae4  ldstr    aSystemcustomiz_268// "SystemCustomization.WsdlProgramming.Org"...
0x9bae9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9baee  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::organizationServiceEndpointDescriptionSeeMoreLink
0x9baf3  ldarg.0
0x9baf4  ldarg.0
0x9baf5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bafa  ldstr    aSystemcustomiz_269// "SystemCustomization.WsdlProgramming.Ins"...
0x9baff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bb04  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::instanceReferenceInformationSeeMoreLink
0x9bb09  ldarg.0
0x9bb0a  ldarg.0
0x9bb0b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bb10  ldstr    aSystemcustomiz_270// "SystemCustomization.WsdlProgramming.Dis"...
0x9bb15  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bb1a  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::discoveryServiceSeeMoreLink
0x9bb1f  ldarg.0
0x9bb20  ldarg.0
0x9bb21  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bb26  ldstr    aSystemcustomiz_271// "SystemCustomization.WsdlProgramming.Dis"...
0x9bb2b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bb30  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::discoveryServiceWebAPISeeMoreLink
0x9bb35  ldarg.0
0x9bb36  ldarg.0
0x9bb37  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bb3c  ldstr    aSystemcustomiz_272// "SystemCustomization.WsdlProgramming.ODa"...
0x9bb41  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bb46  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::oDataV4EndpointDescriptionSeeMoreLinkText
0x9bb4b  ldarg.0
0x9bb4c  ldarg.0
0x9bb4d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bb52  ldstr    aSystemcustomiz_273// "SystemCustomization.WsdlProgramming.Org"...
0x9bb57  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bb5c  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::organizationServiceEndpointDescriptionSeeMoreLinkText
0x9bb61  ldarg.0
0x9bb62  ldarg.0
0x9bb63  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bb68  ldstr    aSystemcustomiz_274// "SystemCustomization.WsdlProgramming.Ins"...
0x9bb6d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bb72  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::instanceReferenceInformationSeeMoreLinkText
0x9bb77  ldarg.0
0x9bb78  ldarg.0
0x9bb79  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bb7e  ldstr    aSystemcustomiz_275// "SystemCustomization.WsdlProgramming.Dis"...
0x9bb83  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bb88  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::discoveryServiceSeeMoreLinkText
0x9bb8d  ldarg.0
0x9bb8e  ldarg.0
0x9bb8f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bb94  ldstr    aSystemcustomiz_276// "SystemCustomization.WsdlProgramming.Dis"...
0x9bb99  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bb9e  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::discoveryServiceWebAPISeeMoreLinkText
0x9bba3  ldarg.0
0x9bba4  ldarg.0
0x9bba5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bbaa  ldstr    aSystemcustomiz_277// "SystemCustomization.WsdlProgramming.Dev"...
0x9bbaf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bbb4  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::developerOverviewLink
0x9bbb9  ldarg.0
0x9bbba  ldarg.0
0x9bbbb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bbc0  ldstr    aSystemcustomiz_278// "SystemCustomization.WsdlProgramming.Dev"...
0x9bbc5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bbca  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::developerCenterLink
0x9bbcf  ldarg.0
0x9bbd0  ldarg.0
0x9bbd1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bbd6  ldstr    aSystemcustomiz_279// "SystemCustomization.WsdlProgramming.Dev"...
0x9bbdb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bbe0  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::developerForumsLink
0x9bbe5  ldarg.0
0x9bbe6  ldarg.0
0x9bbe7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bbec  ldstr    aSystemcustomiz_280// "SystemCustomization.WsdlProgramming.SDK"...
0x9bbf1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bbf6  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::sdkNugetPackagesLink
0x9bbfb  ldarg.0
0x9bbfc  ldarg.0
0x9bbfd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bc02  ldstr    aSystemcustomiz_281// "SystemCustomization.WsdlProgramming.SDK"...
0x9bc07  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bc0c  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::sdkDownloadLink
0x9bc11  ldarg.0
0x9bc12  ldarg.0
0x9bc13  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bc18  ldstr    aSystemcustomiz_282// "SystemCustomization.WsdlProgramming.Sam"...
0x9bc1d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bc22  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::sampleCodeLink
0x9bc27  ldarg.0
0x9bc28  ldarg.0
0x9bc29  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bc2e  ldstr    aSystemcustomiz_283// "SystemCustomization.WsdlProgramming.Dev"...
0x9bc33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bc38  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::developerOverviewLinkTitle
0x9bc3d  ldarg.0
0x9bc3e  ldarg.0
0x9bc3f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bc44  ldstr    aSystemcustomiz_284// "SystemCustomization.WsdlProgramming.Dev"...
0x9bc49  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bc4e  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::developerCenterLinkTitle
0x9bc53  ldarg.0
0x9bc54  ldarg.0
0x9bc55  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bc5a  ldstr    aSystemcustomiz_285// "SystemCustomization.WsdlProgramming.Dev"...
0x9bc5f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bc64  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::developerForumsLinkTitle
0x9bc69  ldarg.0
0x9bc6a  ldarg.0
0x9bc6b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bc70  ldstr    aSystemcustomiz_286// "SystemCustomization.WsdlProgramming.SDK"...
0x9bc75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bc7a  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::sdkNugetPackagesLinkTitle
0x9bc7f  ldarg.0
0x9bc80  ldarg.0
0x9bc81  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bc86  ldstr    aSystemcustomiz_287// "SystemCustomization.WsdlProgramming.SDK"...
0x9bc8b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bc90  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::sdkDownloadLinkTitle
0x9bc95  ldarg.0
0x9bc96  ldarg.0
0x9bc97  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9bc9c  ldstr    aSystemcustomiz_288// "SystemCustomization.WsdlProgramming.Sam"...
0x9bca1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9bca6  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::sampleCodeLinkTitle
0x9bcab  ldarg.0
0x9bcac  ldc.i4.0
0x9bcad  stfld    bool Microsoft.Crm.Web.Tools.SystemCustomization.WsdlProgrammingPage::showAppFabricIssuer
0x9bcb2  ret
```
