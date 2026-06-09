# Microsoft.Crm.Tools.Admin.IfdConfiguration::SetIfdInfo

- ea: `0x4e60`
- end: `0x5023`
- name: `Microsoft.Crm.Tools.Admin.IfdConfiguration::SetIfdInfo`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3080`
- `0x4e60`
- `0x5180`
- `0x5190`
- `0x51d0`
- `0x5210`
- `0x5250`
- `0x5290`
- `0x52d0`

## string_xrefs

- `0x4e90`: `IfdIntranetAccessEnabled`
- `0x4fc8`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Ifd\IfdConfigurator.cs`
- `0x4fe9`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Ifd\IfdConfigurator.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4e60  ldc.i4.6
0x4e61  newarr   [mscorlib]System.String
0x4e66  dup
0x4e67  ldc.i4.0
0x4e68  ldstr    aIfdrootdomains// "IfdRootDomainScheme"
0x4e6d  stelem.ref
0x4e6e  dup
0x4e6f  ldc.i4.1
0x4e70  ldstr    aIfdsdkrootdoma_0// "IfdSdkRootDomain"
0x4e75  stelem.ref
0x4e76  dup
0x4e77  ldc.i4.2
0x4e78  ldstr    aIfdwebapplicat_0// "IfdWebApplicationRootDomain"
0x4e7d  stelem.ref
0x4e7e  dup
0x4e7f  ldc.i4.3
0x4e80  ldstr    aIfddiscoveryro_0// "IfdDiscoveryRootDomain"
0x4e85  stelem.ref
0x4e86  dup
0x4e87  ldc.i4.4
0x4e88  ldstr    aIfdenabled// "IfdEnabled"
0x4e8d  stelem.ref
0x4e8e  dup
0x4e8f  ldc.i4.5
0x4e90  ldstr    aIfdintranetacc// "IfdIntranetAccessEnabled"
0x4e95  stelem.ref
0x4e96  stloc.0
0x4e97  ldc.i4.3
0x4e98  newarr   [mscorlib]System.String
0x4e9d  dup
0x4e9e  ldc.i4.0
0x4e9f  ldstr    aIfdsdkrootdoma// "IfdSdkRootDomainBackup"
0x4ea4  stelem.ref
0x4ea5  dup
0x4ea6  ldc.i4.1
0x4ea7  ldstr    aIfdwebapplicat// "IfdWebApplicationRootDomainBackup"
0x4eac  stelem.ref
0x4ead  dup
0x4eae  ldc.i4.2
0x4eaf  ldstr    aIfddiscoveryro// "IfdDiscoveryRootDomainBackup"
0x4eb4  stelem.ref
0x4eb5  stloc.1
0x4eb6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x4ebb  stloc.2
0x4ebc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x4ec1  stloc.3
0x4ec2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x4ec7  stloc.s  4
0x4ec9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x4ece  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentId()
0x4ed3  stloc.s  5
0x4ed5  ldarg.0
0x4ed6  callvirt instance bool Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdEnabled()
0x4edb  brfalse.s loc_4F2A
0x4edd  ldloc.2
0x4ede  ldloc.0
0x4edf  ldc.i4.0
0x4ee0  ldelem.ref
0x4ee1  ldarg.0
0x4ee2  callvirt instance string Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdRootDomainScheme()
0x4ee7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4eec  ldloc.2
0x4eed  ldloc.0
0x4eee  ldc.i4.1
0x4eef  ldelem.ref
0x4ef0  ldarg.0
0x4ef1  callvirt instance string Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdSdkRootDomain()
0x4ef6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4efb  ldloc.2
0x4efc  ldloc.0
0x4efd  ldc.i4.2
0x4efe  ldelem.ref
0x4eff  ldarg.0
0x4f00  callvirt instance string Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdWebApplicationRootDomain()
0x4f05  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f0a  ldloc.2
0x4f0b  ldloc.0
0x4f0c  ldc.i4.3
0x4f0d  ldelem.ref
0x4f0e  ldarg.0
0x4f0f  callvirt instance string Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdDiscoveryRootDomain()
0x4f14  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f19  ldloc.2
0x4f1a  ldloc.0
0x4f1b  ldc.i4.4
0x4f1c  ldelem.ref
0x4f1d  ldc.i4.1
0x4f1e  box      [mscorlib]System.Boolean
0x4f23  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f28  br.s     loc_4F71
0x4f2a  ldloc.2
0x4f2b  ldloc.0
0x4f2c  ldc.i4.0
0x4f2d  ldelem.ref
0x4f2e  ldsfld   string [mscorlib]System.String::Empty
0x4f33  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f38  ldloc.2
0x4f39  ldloc.0
0x4f3a  ldc.i4.1
0x4f3b  ldelem.ref
0x4f3c  ldsfld   string [mscorlib]System.String::Empty
0x4f41  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f46  ldloc.2
0x4f47  ldloc.0
0x4f48  ldc.i4.2
0x4f49  ldelem.ref
0x4f4a  ldsfld   string [mscorlib]System.String::Empty
0x4f4f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f54  ldloc.2
0x4f55  ldloc.0
0x4f56  ldc.i4.3
0x4f57  ldelem.ref
0x4f58  ldsfld   string [mscorlib]System.String::Empty
0x4f5d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f62  ldloc.2
0x4f63  ldloc.0
0x4f64  ldc.i4.4
0x4f65  ldelem.ref
0x4f66  ldc.i4.0
0x4f67  box      [mscorlib]System.Boolean
0x4f6c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f71  ldloc.2
0x4f72  ldloc.0
0x4f73  ldc.i4.5
0x4f74  ldelem.ref
0x4f75  ldarg.0
0x4f76  callvirt instance bool Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdIntranetAccessEnabled()
0x4f7b  box      [mscorlib]System.Boolean
0x4f80  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f85  ldloc.3
0x4f86  ldloc.1
0x4f87  ldc.i4.0
0x4f88  ldelem.ref
0x4f89  ldarg.0
0x4f8a  callvirt instance string Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdSdkRootDomain()
0x4f8f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f94  ldloc.3
0x4f95  ldloc.1
0x4f96  ldc.i4.1
0x4f97  ldelem.ref
0x4f98  ldarg.0
0x4f99  callvirt instance string Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdWebApplicationRootDomain()
0x4f9e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4fa3  ldloc.3
0x4fa4  ldloc.1
0x4fa5  ldc.i4.2
0x4fa6  ldelem.ref
0x4fa7  ldarg.0
0x4fa8  callvirt instance string Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdDiscoveryRootDomain()
0x4fad  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4fb2  ldloc.s  4
0x4fb4  ldstr    aDeployment// "Deployment"
0x4fb9  ldloc.s  5
0x4fbb  box      [mscorlib]System.Guid
0x4fc0  ldloc.2
0x4fc1  ldc.i4.s 0x7C
0x4fc3  ldstr    aSetifdinfo// "SetIfdInfo"
0x4fc8  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x4fcd  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x4fd2  pop
0x4fd3  ldloc.s  4
0x4fd5  ldstr    aDeployment// "Deployment"
0x4fda  ldloc.s  5
0x4fdc  box      [mscorlib]System.Guid
0x4fe1  ldloc.3
0x4fe2  ldc.i4.s 0x7F
0x4fe4  ldstr    aSetifdinfo// "SetIfdInfo"
0x4fe9  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x4fee  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x4ff3  pop
0x4ff4  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x4ff9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Flush()
0x4ffe  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_DefaultId()
0x5003  ldarg.0
0x5004  callvirt instance string Microsoft.Crm.Tools.Admin.IfdInfo::get_ExternalRelyingPartyPassiveIdentifier()
0x5009  newobj   instance void [System]System.Uri::.ctor(string)
0x500e  call     void Microsoft.Crm.Tools.Admin.ClaimsConfiguration::SetExternalRelyingPartyIdentifierUrl(valuetype [mscorlib]System.Guid federationProviderId, class [System]System.Uri uri)
0x5013  leave.s  loc_5021
0x5015  ldloc.s  4
0x5017  brfalse.s loc_5020
0x5019  ldloc.s  4
0x501b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5020  endfinally
0x5021  ldc.i4.1
0x5022  ret
```
