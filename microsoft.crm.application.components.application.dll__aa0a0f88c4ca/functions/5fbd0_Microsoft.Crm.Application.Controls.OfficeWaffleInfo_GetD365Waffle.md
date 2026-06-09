# Microsoft.Crm.Application.Controls.OfficeWaffleInfo::GetD365Waffle

- ea: `0x5fbd0`
- end: `0x5ff2a`
- name: `Microsoft.Crm.Application.Controls.OfficeWaffleInfo::GetD365Waffle`
- size: `858`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x950`
- `0x9a0`
- `0x1b80`
- `0x1ba0`
- `0x1bc0`
- `0x1be0`
- `0x1c00`
- `0x1c20`
- `0x1c60`
- `0x1c80`
- `0x1cd0`
- `0x1d40`
- `0x1d80`
- `0x1dc0`
- `0x5fbd0`
- `0xa2780`

## string_xrefs

- `0x5fc9a`: `officeShellServiceTimeout`
- `0x5fce5`: `WSHttpBinding_IShellService`
- `0x5fdbd`: `Waffle certificate not configured`
- `0x5fddb`: `O365 waffle load failure - Unable to create shell service client: {0}`
- `0x5feb0`: `O365 waffle load failure - Unable to connect to the shell service: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5fbd0  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, string>::.ctor()
0x5fbd5  stloc.0
0x5fbd6  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x5fbdb  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x5fbe0  call     string [Microsoft.Crm.Core]IdentityExtensions::GetUserToken(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x5fbe5  ldc.i4.0
0x5fbe6  newarr   [mscorlib]System.Object
0x5fbeb  call     string [mscorlib]System.String::Format(string, object[])
0x5fbf0  dup
0x5fbf1  ldc.i4.s 0x3A
0x5fbf3  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x5fbf8  ldc.i4.1
0x5fbf9  add
0x5fbfa  callvirt instance string [mscorlib]System.String::Substring(int32)
0x5fbff  stloc.1
0x5fc00  ldloc.1
0x5fc01  ldc.i4.0
0x5fc02  ldloc.1
0x5fc03  ldc.i4.s 0x40
0x5fc05  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x5fc0a  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x5fc0f  stloc.1
0x5fc10  ldstr    a0_1// "{0}"
0x5fc15  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x5fc1a  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x5fc1f  call     string [Microsoft.Crm.Core]IdentityExtensions::GetUserName(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x5fc24  call     string [mscorlib]System.String::Format(string, object)
0x5fc29  stloc.2
0x5fc2a  leave.s  loc_5FC59
0x5fc2c  stloc.s  5
0x5fc2e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5fc33  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x5fc38  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x5fc3d  ldstr    aO365WaffleLoad// "O365 waffle load failure - PUID/UPN not"...
0x5fc42  ldc.i4.1
0x5fc43  newarr   [mscorlib]System.Object
0x5fc48  dup
0x5fc49  ldc.i4.0
0x5fc4a  ldloc.s  5
0x5fc4c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5fc51  stelem.ref
0x5fc52  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5fc57  rethrow
0x5fc59  nop
0x5fc5a  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIUtility::get_EnvironmentType()
0x5fc5f  stloc.s  6
0x5fc61  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x5fc66  ldstr    aO365shellendpo// "O365ShellEndPoint"
0x5fc6b  ldc.i4.1
0x5fc6c  callvirt T0x2B00000B
0x5fc71  stloc.s  7
0x5fc73  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5fc78  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x5fc7d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x5fc82  stloc.s  8
0x5fc84  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x5fc89  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5fc8e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x5fc93  ldloc.s  8
0x5fc95  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x5fc9a  ldstr    aOfficeshellser// "officeShellServiceTimeout"
0x5fc9f  ldc.i4.5
0x5fca0  box      [mscorlib]System.Int32
0x5fca5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x5fcaa  unbox.any [mscorlib]System.Int32
0x5fcaf  stloc.s  9
0x5fcb1  ldloc.s  7
0x5fcb3  brfalse.s loc_5FCC3
0x5fcb5  ldloc.s  7
0x5fcb7  ldstr    asc_F537C// ""
0x5fcbc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5fcc1  brfalse.s loc_5FCE5
0x5fcc3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Controls.OfficeWaffleInfo::_shellServices
0x5fcc8  ldloc.s  6
0x5fcca  ldloca.s 7
0x5fccc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x5fcd1  brtrue.s loc_5FCE5
0x5fcd3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Controls.OfficeWaffleInfo::_shellServices
0x5fcd8  ldstr    aProd// "prod"
0x5fcdd  ldloca.s 7
0x5fcdf  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x5fce4  pop
0x5fce5  ldstr    aWshttpbindingI// "WSHttpBinding_IShellService"
0x5fcea  newobj   instance void [System.ServiceModel]System.ServiceModel.WSHttpBinding::.ctor(string)
0x5fcef  dup
0x5fcf0  ldc.i4.0
0x5fcf1  ldc.i4.0
0x5fcf2  ldloc.s  9
0x5fcf4  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x5fcf9  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_OpenTimeout(valuetype [mscorlib]System.TimeSpan)
0x5fcfe  dup
0x5fcff  ldc.i4.0
0x5fd00  ldc.i4.0
0x5fd01  ldloc.s  9
0x5fd03  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x5fd08  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_ReceiveTimeout(valuetype [mscorlib]System.TimeSpan)
0x5fd0d  dup
0x5fd0e  ldc.i4.0
0x5fd0f  ldc.i4.0
0x5fd10  ldloc.s  9
0x5fd12  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x5fd17  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_SendTimeout(valuetype [mscorlib]System.TimeSpan)
0x5fd1c  dup
0x5fd1d  ldc.i4.0
0x5fd1e  ldc.i4.0
0x5fd1f  ldloc.s  9
0x5fd21  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x5fd26  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_CloseTimeout(valuetype [mscorlib]System.TimeSpan)
0x5fd2b  ldloc.s  7
0x5fd2d  newobj   instance void [System.ServiceModel]System.ServiceModel.EndpointAddress::.ctor(string)
0x5fd32  stloc.s  0xA
0x5fd34  ldloc.s  0xA
0x5fd36  newobj   instance void ShellServiceClient::.ctor(class [System.ServiceModel]System.ServiceModel.Channels.Binding binding, class [System.ServiceModel]System.ServiceModel.EndpointAddress remoteAddress)
0x5fd3b  stloc.3
0x5fd3c  ldarg.0
0x5fd3d  ldfld    class Microsoft.Crm.Application.Controls.D365CertManager Microsoft.Crm.Application.Controls.OfficeWaffleInfo::_waffleCertManager
0x5fd42  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.Crm.Application.Controls.D365CertManager::GetD365ShellServiceCert()
0x5fd47  stloc.s  0xB
0x5fd49  ldloc.s  0xB
0x5fd4b  brtrue.s loc_5FD86
0x5fd4d  ldc.i4.5
0x5fd4e  ldc.i4.2
0x5fd4f  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Store::.ctor(valuetype [System]System.Security.Cryptography.X509Certificates.StoreName, valuetype [System]System.Security.Cryptography.X509Certificates.StoreLocation)
0x5fd54  dup
0x5fd55  ldc.i4.4
0x5fd56  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509Store::Open(valuetype [System]System.Security.Cryptography.X509Certificates.OpenFlags)
0x5fd5b  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection [System]System.Security.Cryptography.X509Certificates.X509Store::get_Certificates()
0x5fd60  ldc.i4.1
0x5fd61  ldstr    aDynamics365Por// "dynamics365-portal-header"
0x5fd66  ldc.i4.1
0x5fd67  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection::Find(valuetype [System]System.Security.Cryptography.X509Certificates.X509FindType, object, bool)
0x5fd6c  stloc.s  0xC
0x5fd6e  ldloc.s  0xC
0x5fd70  brfalse.s loc_5FD86
0x5fd72  ldloc.s  0xC
0x5fd74  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5fd79  ldc.i4.0
0x5fd7a  ble.s    loc_5FD86
0x5fd7c  ldloc.s  0xC
0x5fd7e  ldc.i4.0
0x5fd7f  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection::get_Item(int32)
0x5fd84  stloc.s  0xB
0x5fd86  ldloc.s  0xB
0x5fd88  brfalse.s loc_5FD9E
0x5fd8a  ldloc.3
0x5fd8b  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials class [System.ServiceModel]System.ServiceModel.ClientBase`1<class IShellService>::get_ClientCredentials()
0x5fd90  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ClientCertificate()
0x5fd95  ldloc.s  0xB
0x5fd97  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorClientCredential::set_Certificate(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x5fd9c  br.s     loc_5FDC8
0x5fd9e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5fda3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x5fda8  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x5fdad  ldstr    aO365WaffleLoad_0// "O365 waffle load failure - Unable to fi"...
0x5fdb2  ldc.i4.0
0x5fdb3  newarr   [mscorlib]System.Object
0x5fdb8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5fdbd  ldstr    aWaffleCertific// "Waffle certificate not configured"
0x5fdc2  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x5fdc7  throw
0x5fdc8  leave.s  loc_5FDF7
0x5fdca  stloc.s  0xD
0x5fdcc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5fdd1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x5fdd6  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x5fddb  ldstr    aO365WaffleLoad_1// "O365 waffle load failure - Unable to cr"...
0x5fde0  ldc.i4.1
0x5fde1  newarr   [mscorlib]System.Object
0x5fde6  dup
0x5fde7  ldc.i4.0
0x5fde8  ldloc.s  0xD
0x5fdea  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5fdef  stelem.ref
0x5fdf0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5fdf5  rethrow
0x5fdf7  nop
0x5fdf8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5fdfd  stloc.s  0x10
0x5fdff  ldloca.s 0x10
0x5fe01  constrained. [mscorlib]System.Guid
0x5fe07  callvirt instance string [mscorlib]System.Object::ToString()
0x5fe0c  stloc.s  0xE
0x5fe0e  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentContext()
0x5fe13  brfalse.s loc_5FE3B
0x5fe15  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentContext()
0x5fe1a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_ActivityId()
0x5fe1f  pop
0x5fe20  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentContext()
0x5fe25  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_ActivityId()
0x5fe2a  stloc.s  0x10
0x5fe2c  ldloca.s 0x10
0x5fe2e  constrained. [mscorlib]System.Guid
0x5fe34  callvirt instance string [mscorlib]System.Object::ToString()
0x5fe39  stloc.s  0xE
0x5fe3b  newobj   instance void Microsoft.Online.BOX.Shell.ShellInfoRequest::.ctor()
0x5fe40  dup
0x5fe41  ldc.i4.s 0x24
0x5fe43  callvirt instance void Microsoft.Online.BOX.Shell.NavBarInfoRequest::set_WorkloadId(valuetype Microsoft.Online.BOX.Shell.WorkloadAuthenticationId value)
0x5fe48  dup
0x5fe49  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5fe4e  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserCulture()
0x5fe53  callvirt instance string [mscorlib]System.Object::ToString()
0x5fe58  callvirt instance void Microsoft.Online.BOX.Shell.NavBarInfoRequest::set_CultureName(string value)
0x5fe5d  dup
0x5fe5e  ldloc.1
0x5fe5f  callvirt instance void Microsoft.Online.BOX.Shell.NavBarInfoRequest::set_UserPuid(string value)
0x5fe64  dup
0x5fe65  ldloc.2
0x5fe66  callvirt instance void Microsoft.Online.BOX.Shell.NavBarInfoRequest::set_UserPrincipalName(string value)
0x5fe6b  dup
0x5fe6c  ldc.i4.3
0x5fe6d  callvirt instance void Microsoft.Online.BOX.Shell.NavBarInfoRequest::set_CurrentMainLinkID(valuetype Microsoft.Online.BOX.UI.Shell.NavBarMainLinkID value)
0x5fe72  dup
0x5fe73  ldc.i4.0
0x5fe74  callvirt instance void Microsoft.Online.BOX.Shell.ShellInfoRequest::set_ExcludeMSAjax(bool value)
0x5fe79  dup
0x5fe7a  ldloc.s  0xE
0x5fe7c  callvirt instance void Microsoft.Online.BOX.Shell.NavBarInfoRequest::set_TrackingGuid(string value)
0x5fe81  dup
0x5fe82  ldloca.s 0x11
0x5fe84  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Online.BOX.UI.Shell.ShellBaseFlight>
0x5fe8a  ldloc.s  0x11
0x5fe8c  callvirt instance void Microsoft.Online.BOX.Shell.ShellInfoRequest::set_ShellBaseFlight(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Online.BOX.UI.Shell.ShellBaseFlight> value)
0x5fe91  stloc.s  0xF
0x5fe93  ldloc.3
0x5fe94  ldloc.s  0xF
0x5fe96  callvirt instance class Microsoft.Online.BOX.Shell.ShellInfo ShellServiceClient::GetShellInfo(class Microsoft.Online.BOX.Shell.ShellInfoRequest shellInfoRequest)
0x5fe9b  stloc.s  4
0x5fe9d  leave.s  loc_5FED3
0x5fe9f  stloc.s  0x12
0x5fea1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5fea6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x5feab  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x5feb0  ldstr    aO365WaffleLoad_2// "O365 waffle load failure - Unable to co"...
0x5feb5  ldc.i4.1
0x5feb6  newarr   [mscorlib]System.Object
0x5febb  dup
0x5febc  ldc.i4.0
0x5febd  ldloc.s  0x12
0x5febf  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5fec4  stelem.ref
0x5fec5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5feca  rethrow
0x5fecc  ldloc.3
0x5fecd  callvirt instance void class [System.ServiceModel]System.ServiceModel.ClientBase`1<class IShellService>::Close()
0x5fed2  endfinally
0x5fed3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5fed8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x5fedd  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x5fee2  ldstr    aO365WaffleRetr// "O365 waffle retrieved"
0x5fee7  ldc.i4.0
0x5fee8  newarr   [mscorlib]System.Object
0x5feed  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5fef2  ldloc.0
0x5fef3  ldstr    aCss// "css"
0x5fef8  ldloc.s  4
0x5fefa  callvirt instance string Microsoft.Online.BOX.Shell.NavBarInfo::get_SharedCSSUrl()
0x5feff  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5ff04  ldloc.0
0x5ff05  ldstr    aJs// "js"
0x5ff0a  ldloc.s  4
0x5ff0c  callvirt instance string Microsoft.Online.BOX.Shell.NavBarInfo::get_SharedJSUrl()
0x5ff11  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5ff16  ldloc.0
0x5ff17  ldstr    aNavbardata// "navBarData"
0x5ff1c  ldloc.s  4
0x5ff1e  callvirt instance string Microsoft.Online.BOX.Shell.NavBarInfo::get_NavBarDataJson()
0x5ff23  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5ff28  ldloc.0
0x5ff29  ret
```
