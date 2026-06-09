# Microsoft.Crm.Tools.Admin.IfdConfiguration::RetrieveIfdInfo

- ea: `0x4cf0`
- end: `0x4e57`
- name: `Microsoft.Crm.Tools.Admin.IfdConfiguration::RetrieveIfdInfo`
- size: `359`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4cf0`
- `0x5170`
- `0x51b0`
- `0x51f0`
- `0x5230`
- `0x5270`
- `0x52b0`
- `0x52f0`

## string_xrefs

- `0x4d1e`: `IfdIntranetAccessEnabled`
- `0x4d4e`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Ifd\IfdConfigurator.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4cf0  newobj   instance void Microsoft.Crm.Tools.Admin.IfdInfo::.ctor()
0x4cf5  stloc.0
0x4cf6  ldc.i4.5
0x4cf7  newarr   [mscorlib]System.String
0x4cfc  dup
0x4cfd  ldc.i4.0
0x4cfe  ldstr    aIfdsdkrootdoma// "IfdSdkRootDomainBackup"
0x4d03  stelem.ref
0x4d04  dup
0x4d05  ldc.i4.1
0x4d06  ldstr    aIfdwebapplicat// "IfdWebApplicationRootDomainBackup"
0x4d0b  stelem.ref
0x4d0c  dup
0x4d0d  ldc.i4.2
0x4d0e  ldstr    aIfddiscoveryro// "IfdDiscoveryRootDomainBackup"
0x4d13  stelem.ref
0x4d14  dup
0x4d15  ldc.i4.3
0x4d16  ldstr    aIfdenabled// "IfdEnabled"
0x4d1b  stelem.ref
0x4d1c  dup
0x4d1d  ldc.i4.4
0x4d1e  ldstr    aIfdintranetacc// "IfdIntranetAccessEnabled"
0x4d23  stelem.ref
0x4d24  stloc.1
0x4d25  ldnull
0x4d26  stloc.2
0x4d27  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x4d2c  stloc.3
0x4d2d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x4d32  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentId()
0x4d37  stloc.s  4
0x4d39  ldloc.3
0x4d3a  ldstr    aDeployment// "Deployment"
0x4d3f  ldloc.s  4
0x4d41  box      [mscorlib]System.Guid
0x4d46  ldloc.1
0x4d47  ldc.i4.s 0x27
0x4d49  ldstr    aRetrieveifdinf// "RetrieveIfdInfo"
0x4d4e  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x4d53  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x4d58  stloc.2
0x4d59  leave.s  loc_4D65
0x4d5b  ldloc.3
0x4d5c  brfalse.s loc_4D64
0x4d5e  ldloc.3
0x4d5f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d64  endfinally
0x4d65  ldloc.2
0x4d66  ldloc.1
0x4d67  ldc.i4.0
0x4d68  ldelem.ref
0x4d69  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4d6e  brfalse  loc_4DFA
0x4d73  ldloc.0
0x4d74  ldloc.2
0x4d75  ldloc.1
0x4d76  ldc.i4.0
0x4d77  ldelem.ref
0x4d78  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4d7d  callvirt instance string [mscorlib]System.Object::ToString()
0x4d82  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdSdkRootDomain(string value)
0x4d87  ldloc.0
0x4d88  ldloc.2
0x4d89  ldloc.1
0x4d8a  ldc.i4.1
0x4d8b  ldelem.ref
0x4d8c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4d91  callvirt instance string [mscorlib]System.Object::ToString()
0x4d96  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdWebApplicationRootDomain(string value)
0x4d9b  ldloc.0
0x4d9c  ldloc.2
0x4d9d  ldloc.1
0x4d9e  ldc.i4.2
0x4d9f  ldelem.ref
0x4da0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4da5  callvirt instance string [mscorlib]System.Object::ToString()
0x4daa  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdDiscoveryRootDomain(string value)
0x4daf  ldloc.0
0x4db0  ldloc.2
0x4db1  ldloc.1
0x4db2  ldc.i4.3
0x4db3  ldelem.ref
0x4db4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4db9  unbox.any [mscorlib]System.Boolean
0x4dbe  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdEnabled(bool value)
0x4dc3  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_DefaultId()
0x4dc8  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::.ctor(valuetype [mscorlib]System.Guid)
0x4dcd  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::GetFederationProviderData()
0x4dd2  stloc.s  5
0x4dd4  ldloc.s  5
0x4dd6  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::get_ExternalRelyingPartyPassiveIdentifier()
0x4ddb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4de0  brfalse.s loc_4DEB
0x4de2  ldloc.0
0x4de3  ldnull
0x4de4  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_ExternalRelyingPartyPassiveIdentifier(string value)
0x4de9  br.s     loc_4E2D
0x4deb  ldloc.0
0x4dec  ldloc.s  5
0x4dee  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::get_ExternalRelyingPartyPassiveIdentifier()
0x4df3  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_ExternalRelyingPartyPassiveIdentifier(string value)
0x4df8  br.s     loc_4E2D
0x4dfa  ldloc.0
0x4dfb  ldstr    asc_1E310// ""
0x4e00  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdSdkRootDomain(string value)
0x4e05  ldloc.0
0x4e06  ldstr    asc_1E310// ""
0x4e0b  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdWebApplicationRootDomain(string value)
0x4e10  ldloc.0
0x4e11  ldstr    asc_1E310// ""
0x4e16  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdDiscoveryRootDomain(string value)
0x4e1b  ldloc.0
0x4e1c  ldstr    asc_1E310// ""
0x4e21  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_ExternalRelyingPartyPassiveIdentifier(string value)
0x4e26  ldloc.0
0x4e27  ldc.i4.0
0x4e28  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdEnabled(bool value)
0x4e2d  ldloc.2
0x4e2e  ldloc.1
0x4e2f  ldc.i4.4
0x4e30  ldelem.ref
0x4e31  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4e36  brtrue.s loc_4E41
0x4e38  ldloc.0
0x4e39  ldc.i4.0
0x4e3a  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdIntranetAccessEnabled(bool value)
0x4e3f  br.s     loc_4E55
0x4e41  ldloc.0
0x4e42  ldloc.2
0x4e43  ldloc.1
0x4e44  ldc.i4.4
0x4e45  ldelem.ref
0x4e46  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4e4b  unbox.any [mscorlib]System.Boolean
0x4e50  callvirt instance void Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdIntranetAccessEnabled(bool value)
0x4e55  ldloc.0
0x4e56  ret
```
