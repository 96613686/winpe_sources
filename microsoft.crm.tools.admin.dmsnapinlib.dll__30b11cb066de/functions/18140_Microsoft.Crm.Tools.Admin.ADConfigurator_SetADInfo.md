# Microsoft.Crm.Tools.Admin.ADConfigurator::SetADInfo

- ea: `0x18140`
- end: `0x1829b`
- name: `Microsoft.Crm.Tools.Admin.ADConfigurator::SetADInfo`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3070`
- `0x17d50`
- `0x17d90`
- `0x17dd0`
- `0x17e10`
- `0x17e50`
- `0x17e90`
- `0x17ed0`
- `0x17f10`
- `0x18140`

## string_xrefs

- `0x1823c`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\WebServiceSettings\ADConfigurator.cs`
- `0x1825d`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\WebServiceSettings\ADConfigurator.cs`

## pseudocode

```c

```

## disassembly

```asm
0x18140  ldc.i4.5
0x18141  newarr   [mscorlib]System.String
0x18146  dup
0x18147  ldc.i4.0
0x18148  ldstr    aAdrootdomainsc// "ADRootDomainScheme"
0x1814d  stelem.ref
0x1814e  dup
0x1814f  ldc.i4.1
0x18150  ldstr    aAdsdkrootdomai// "ADSdkRootDomain"
0x18155  stelem.ref
0x18156  dup
0x18157  ldc.i4.2
0x18158  ldstr    aAdwebapplicati// "ADWebApplicationRootDomain"
0x1815d  stelem.ref
0x1815e  dup
0x1815f  ldc.i4.3
0x18160  ldstr    aAddiscoveryroo// "ADDiscoveryRootDomain"
0x18165  stelem.ref
0x18166  dup
0x18167  ldc.i4.4
0x18168  ldstr    aAddeploymentsd// "ADDeploymentSdkRootDomain"
0x1816d  stelem.ref
0x1816e  stloc.0
0x1816f  ldc.i4.2
0x18170  newarr   [mscorlib]System.String
0x18175  dup
0x18176  ldc.i4.0
0x18177  ldstr    aSslheader// "SslHeader"
0x1817c  stelem.ref
0x1817d  dup
0x1817e  ldc.i4.1
0x1817f  ldstr    aNlbenabled// "NlbEnabled"
0x18184  stelem.ref
0x18185  stloc.1
0x18186  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1818b  stloc.2
0x1818c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x18191  stloc.3
0x18192  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.HelpServerData::.ctor()
0x18197  stloc.s  4
0x18199  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x1819e  stloc.s  5
0x181a0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x181a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentId()
0x181aa  stloc.s  6
0x181ac  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x181b1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider::GetSiteSettingId()
0x181b6  stloc.s  7
0x181b8  ldloc.2
0x181b9  ldloc.0
0x181ba  ldc.i4.0
0x181bb  ldelem.ref
0x181bc  ldarg.0
0x181bd  callvirt instance string Microsoft.Crm.Tools.Admin.ADInfo::get_ADRootDomainScheme()
0x181c2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x181c7  ldloc.2
0x181c8  ldloc.0
0x181c9  ldc.i4.1
0x181ca  ldelem.ref
0x181cb  ldarg.0
0x181cc  callvirt instance string Microsoft.Crm.Tools.Admin.ADInfo::get_ADSdkRootDomain()
0x181d1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x181d6  ldloc.2
0x181d7  ldloc.0
0x181d8  ldc.i4.2
0x181d9  ldelem.ref
0x181da  ldarg.0
0x181db  callvirt instance string Microsoft.Crm.Tools.Admin.ADInfo::get_ADWebApplicationRootDomain()
0x181e0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x181e5  ldloc.2
0x181e6  ldloc.0
0x181e7  ldc.i4.3
0x181e8  ldelem.ref
0x181e9  ldarg.0
0x181ea  callvirt instance string Microsoft.Crm.Tools.Admin.ADInfo::get_ADDiscoveryRootDomain()
0x181ef  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x181f4  ldloc.2
0x181f5  ldloc.0
0x181f6  ldc.i4.4
0x181f7  ldelem.ref
0x181f8  ldarg.0
0x181f9  callvirt instance string Microsoft.Crm.Tools.Admin.ADInfo::get_ADDeploymentSdkRootDomain()
0x181fe  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x18203  ldloc.3
0x18204  ldloc.1
0x18205  ldc.i4.0
0x18206  ldelem.ref
0x18207  ldarg.0
0x18208  callvirt instance string Microsoft.Crm.Tools.Admin.ADInfo::get_ADSslHeader()
0x1820d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x18212  ldloc.3
0x18213  ldloc.1
0x18214  ldc.i4.1
0x18215  ldelem.ref
0x18216  ldarg.0
0x18217  callvirt instance bool Microsoft.Crm.Tools.Admin.ADInfo::get_ADNlbEnabled()
0x1821c  box      [mscorlib]System.Boolean
0x18221  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x18226  ldloc.s  5
0x18228  ldstr    aDeployment// "Deployment"
0x1822d  ldloc.s  6
0x1822f  box      [mscorlib]System.Guid
0x18234  ldloc.2
0x18235  ldc.i4.s 0x5C
0x18237  ldstr    aSetadinfo// "SetADInfo"
0x1823c  ldstr    aDDbsShDccm2110_12// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x18241  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x18246  pop
0x18247  ldloc.s  5
0x18249  ldstr    aServersettings// "ServerSettings"
0x1824e  ldloc.s  7
0x18250  box      [mscorlib]System.Guid
0x18255  ldloc.3
0x18256  ldc.i4.s 0x5D
0x18258  ldstr    aSetadinfo// "SetADInfo"
0x1825d  ldstr    aDDbsShDccm2110_12// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x18262  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x18267  pop
0x18268  leave.s  loc_18276
0x1826a  ldloc.s  5
0x1826c  brfalse.s loc_18275
0x1826e  ldloc.s  5
0x18270  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18275  endfinally
0x18276  ldloc.s  4
0x18278  ldarg.0
0x18279  callvirt instance string Microsoft.Crm.Tools.Admin.ADInfo::get_ADHelpServerUrl()
0x1827e  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.HelpServerData::set_HelpServer(string)
0x18283  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::.ctor()
0x18288  ldloc.s  4
0x1828a  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::SetHelpServerData(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.HelpServerData)
0x1828f  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_DefaultId()
0x18294  call     void Microsoft.Crm.Tools.Admin.ClaimsConfiguration::UpdateInternalRelyingParty(valuetype [mscorlib]System.Guid federationProviderId)
0x18299  ldc.i4.1
0x1829a  ret
```
