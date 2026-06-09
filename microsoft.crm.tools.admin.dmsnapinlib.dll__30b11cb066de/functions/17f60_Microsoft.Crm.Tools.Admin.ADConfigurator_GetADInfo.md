# Microsoft.Crm.Tools.Admin.ADConfigurator::GetADInfo

- ea: `0x17f60`
- end: `0x18135`
- name: `Microsoft.Crm.Tools.Admin.ADConfigurator::GetADInfo`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x19580`

## callees

- `0x17d20`
- `0x17d70`
- `0x17db0`
- `0x17df0`
- `0x17e30`
- `0x17e70`
- `0x17eb0`
- `0x17ef0`
- `0x17f30`
- `0x17f60`

## string_xrefs

- `0x17fed`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\WebServiceSettings\ADConfigurator.cs`
- `0x1801b`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\WebServiceSettings\ADConfigurator.cs`

## pseudocode

```c

```

## disassembly

```asm
0x17f60  newobj   instance void Microsoft.Crm.Tools.Admin.ADInfo::.ctor()
0x17f65  stloc.0
0x17f66  ldc.i4.5
0x17f67  newarr   [mscorlib]System.String
0x17f6c  dup
0x17f6d  ldc.i4.0
0x17f6e  ldstr    aAdrootdomainsc// "ADRootDomainScheme"
0x17f73  stelem.ref
0x17f74  dup
0x17f75  ldc.i4.1
0x17f76  ldstr    aAdsdkrootdomai// "ADSdkRootDomain"
0x17f7b  stelem.ref
0x17f7c  dup
0x17f7d  ldc.i4.2
0x17f7e  ldstr    aAdwebapplicati// "ADWebApplicationRootDomain"
0x17f83  stelem.ref
0x17f84  dup
0x17f85  ldc.i4.3
0x17f86  ldstr    aAddiscoveryroo// "ADDiscoveryRootDomain"
0x17f8b  stelem.ref
0x17f8c  dup
0x17f8d  ldc.i4.4
0x17f8e  ldstr    aAddeploymentsd// "ADDeploymentSdkRootDomain"
0x17f93  stelem.ref
0x17f94  stloc.1
0x17f95  ldc.i4.2
0x17f96  newarr   [mscorlib]System.String
0x17f9b  dup
0x17f9c  ldc.i4.0
0x17f9d  ldstr    aSslheader// "SslHeader"
0x17fa2  stelem.ref
0x17fa3  dup
0x17fa4  ldc.i4.1
0x17fa5  ldstr    aNlbenabled// "NlbEnabled"
0x17faa  stelem.ref
0x17fab  stloc.2
0x17fac  ldc.i4.1
0x17fad  newarr   [mscorlib]System.String
0x17fb2  dup
0x17fb3  ldc.i4.0
0x17fb4  ldstr    aHelpserverurl// "HelpServerUrl"
0x17fb9  stelem.ref
0x17fba  stloc.3
0x17fbb  ldnull
0x17fbc  stloc.s  4
0x17fbe  ldnull
0x17fbf  stloc.s  5
0x17fc1  ldnull
0x17fc2  stloc.s  6
0x17fc4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x17fc9  stloc.s  7
0x17fcb  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x17fd0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentId()
0x17fd5  stloc.s  8
0x17fd7  ldloc.s  7
0x17fd9  ldstr    aDeployment// "Deployment"
0x17fde  ldloc.s  8
0x17fe0  box      [mscorlib]System.Guid
0x17fe5  ldloc.1
0x17fe6  ldc.i4.s 0x29
0x17fe8  ldstr    aGetadinfo// "GetADInfo"
0x17fed  ldstr    aDDbsShDccm2110_12// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x17ff2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x17ff7  stloc.s  4
0x17ff9  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x17ffe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider::GetSiteSettingId()
0x18003  stloc.s  9
0x18005  ldloc.s  7
0x18007  ldstr    aServersettings// "ServerSettings"
0x1800c  ldloc.s  9
0x1800e  box      [mscorlib]System.Guid
0x18013  ldloc.2
0x18014  ldc.i4.s 0x2C
0x18016  ldstr    aGetadinfo// "GetADInfo"
0x1801b  ldstr    aDDbsShDccm2110_12// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x18020  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x18025  stloc.s  5
0x18027  leave.s  loc_18035
0x18029  ldloc.s  7
0x1802b  brfalse.s loc_18034
0x1802d  ldloc.s  7
0x1802f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18034  endfinally
0x18035  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::.ctor()
0x1803a  ldloc.3
0x1803b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Retrieve(string[])
0x18040  stloc.s  6
0x18042  ldloc.0
0x18043  ldloc.s  4
0x18045  ldloc.1
0x18046  ldc.i4.0
0x18047  ldelem.ref
0x18048  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1804d  dup
0x1804e  brtrue.s loc_18056
0x18050  pop
0x18051  ldsfld   string [mscorlib]System.String::Empty
0x18056  castclass [mscorlib]System.String
0x1805b  callvirt instance void Microsoft.Crm.Tools.Admin.ADInfo::set_ADRootDomainScheme(string value)
0x18060  ldloc.0
0x18061  ldloc.s  4
0x18063  ldloc.1
0x18064  ldc.i4.1
0x18065  ldelem.ref
0x18066  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1806b  dup
0x1806c  brtrue.s loc_18074
0x1806e  pop
0x1806f  ldsfld   string [mscorlib]System.String::Empty
0x18074  castclass [mscorlib]System.String
0x18079  callvirt instance void Microsoft.Crm.Tools.Admin.ADInfo::set_ADSdkRootDomain(string value)
0x1807e  ldloc.0
0x1807f  ldloc.s  4
0x18081  ldloc.1
0x18082  ldc.i4.2
0x18083  ldelem.ref
0x18084  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18089  dup
0x1808a  brtrue.s loc_18092
0x1808c  pop
0x1808d  ldsfld   string [mscorlib]System.String::Empty
0x18092  castclass [mscorlib]System.String
0x18097  callvirt instance void Microsoft.Crm.Tools.Admin.ADInfo::set_ADWebApplicationRootDomain(string value)
0x1809c  ldloc.0
0x1809d  ldloc.s  4
0x1809f  ldloc.1
0x180a0  ldc.i4.3
0x180a1  ldelem.ref
0x180a2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x180a7  dup
0x180a8  brtrue.s loc_180B0
0x180aa  pop
0x180ab  ldsfld   string [mscorlib]System.String::Empty
0x180b0  castclass [mscorlib]System.String
0x180b5  callvirt instance void Microsoft.Crm.Tools.Admin.ADInfo::set_ADDiscoveryRootDomain(string value)
0x180ba  ldloc.0
0x180bb  ldloc.s  4
0x180bd  ldloc.1
0x180be  ldc.i4.4
0x180bf  ldelem.ref
0x180c0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x180c5  dup
0x180c6  brtrue.s loc_180CE
0x180c8  pop
0x180c9  ldsfld   string [mscorlib]System.String::Empty
0x180ce  castclass [mscorlib]System.String
0x180d3  callvirt instance void Microsoft.Crm.Tools.Admin.ADInfo::set_ADDeploymentSdkRootDomain(string value)
0x180d8  ldloc.0
0x180d9  ldloc.s  5
0x180db  ldloc.2
0x180dc  ldc.i4.0
0x180dd  ldelem.ref
0x180de  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x180e3  dup
0x180e4  brtrue.s loc_180EC
0x180e6  pop
0x180e7  ldsfld   string [mscorlib]System.String::Empty
0x180ec  castclass [mscorlib]System.String
0x180f1  callvirt instance void Microsoft.Crm.Tools.Admin.ADInfo::set_ADSslHeader(string value)
0x180f6  ldloc.0
0x180f7  ldloc.s  5
0x180f9  ldloc.2
0x180fa  ldc.i4.1
0x180fb  ldelem.ref
0x180fc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18101  dup
0x18102  brtrue.s loc_1810B
0x18104  pop
0x18105  ldc.i4.0
0x18106  box      [mscorlib]System.Boolean
0x1810b  unbox.any [mscorlib]System.Boolean
0x18110  callvirt instance void Microsoft.Crm.Tools.Admin.ADInfo::set_ADNlbEnabled(bool value)
0x18115  ldloc.0
0x18116  ldloc.s  6
0x18118  ldloc.3
0x18119  ldc.i4.0
0x1811a  ldelem.ref
0x1811b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18120  dup
0x18121  brtrue.s loc_18129
0x18123  pop
0x18124  ldsfld   string [mscorlib]System.String::Empty
0x18129  castclass [mscorlib]System.String
0x1812e  callvirt instance void Microsoft.Crm.Tools.Admin.ADInfo::set_ADHelpServerUrl(string value)
0x18133  ldloc.0
0x18134  ret
```
