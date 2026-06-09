# Microsoft.Crm.Tools.Admin.ClaimsConfiguration::GetClaimsInfo

- ea: `0x2d50`
- end: `0x2e50`
- name: `Microsoft.Crm.Tools.Admin.ClaimsConfiguration::GetClaimsInfo`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x12320`

## callees

- `0x2d50`
- `0x3120`
- `0x3160`
- `0x31a0`
- `0x31e0`
- `0x32a0`
- `0x3340`
- `0x3360`

## string_xrefs

- `0x2dc3`: `ClaimsSessionSecurityTokenLifetime`
- `0x2df1`: `GetClaimsInfo`
- `0x2df6`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Claims\ClaimsConfigurator.cs`
- `0x2e06`: `Error retrieving the ClaimsSessionSecurityTokenLifetime (in hours) attribute from the Deployment table. Exception = ({0})`

## pseudocode

```c

```

## disassembly

```asm
0x2d50  newobj   instance void Microsoft.Crm.Tools.Admin.ClaimsInfo::.ctor()
0x2d55  stloc.0
0x2d56  ldloc.0
0x2d57  ldarg.0
0x2d58  callvirt instance void Microsoft.Crm.Tools.Admin.ClaimsInfo::set_FederationProviderId(valuetype [mscorlib]System.Guid value)
0x2d5d  ldloc.0
0x2d5e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.ClaimsInfo::get_FederationProviderId()
0x2d63  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::.ctor(valuetype [mscorlib]System.Guid)
0x2d68  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::GetFederationProviderData()
0x2d6d  stloc.1
0x2d6e  ldloc.0
0x2d6f  ldloc.1
0x2d70  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::get_Enabled()
0x2d75  callvirt instance void Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsEnabled(bool value)
0x2d7a  ldloc.0
0x2d7b  ldloc.1
0x2d7c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::get_MetadataUrl()
0x2d81  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d86  brtrue.s loc_2D90
0x2d88  ldloc.1
0x2d89  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::get_MetadataUrl()
0x2d8e  br.s     loc_2D95
0x2d90  ldsfld   string [mscorlib]System.String::Empty
0x2d95  callvirt instance void Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsFederationMetadataUrl(string value)
0x2d9a  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::.ctor()
0x2d9f  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::GetEncryptionCertificateName()
0x2da4  stloc.2
0x2da5  ldloc.0
0x2da6  ldloc.2
0x2da7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2dac  brtrue.s loc_2DB1
0x2dae  ldloc.2
0x2daf  br.s     loc_2DB6
0x2db1  ldsfld   string [mscorlib]System.String::Empty
0x2db6  callvirt instance void Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsEncryptionCertificate(string value)
0x2dbb  ldc.i4.1
0x2dbc  newarr   [mscorlib]System.String
0x2dc1  dup
0x2dc2  ldc.i4.0
0x2dc3  ldstr    aClaimssessions// "ClaimsSessionSecurityTokenLifetime"
0x2dc8  stelem.ref
0x2dc9  stloc.3
0x2dca  ldnull
0x2dcb  stloc.s  4
0x2dcd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x2dd2  stloc.s  5
0x2dd4  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2dd9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentId()
0x2dde  stloc.s  6
0x2de0  ldloc.s  5
0x2de2  ldstr    aDeployment// "Deployment"
0x2de7  ldloc.s  6
0x2de9  box      [mscorlib]System.Guid
0x2dee  ldloc.3
0x2def  ldc.i4.s 0x42
0x2df1  ldstr    aGetclaimsinfo// "GetClaimsInfo"
0x2df6  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x2dfb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x2e00  stloc.s  4
0x2e02  leave.s  loc_2E29
0x2e04  stloc.s  7
0x2e06  ldstr    aErrorRetrievin// "Error retrieving the ClaimsSessionSecur"...
0x2e0b  ldc.i4.1
0x2e0c  newarr   [mscorlib]System.Object
0x2e11  dup
0x2e12  ldc.i4.0
0x2e13  ldloc.s  7
0x2e15  stelem.ref
0x2e16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x2e1b  leave.s  loc_2E29
0x2e1d  ldloc.s  5
0x2e1f  brfalse.s loc_2E28
0x2e21  ldloc.s  5
0x2e23  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e28  endfinally
0x2e29  ldloc.s  4
0x2e2b  brfalse.s loc_2E4E
0x2e2d  ldloc.s  4
0x2e2f  ldloc.3
0x2e30  ldc.i4.0
0x2e31  ldelem.ref
0x2e32  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2e37  brfalse.s loc_2E4E
0x2e39  ldloc.0
0x2e3a  ldloc.s  4
0x2e3c  ldloc.3
0x2e3d  ldc.i4.0
0x2e3e  ldelem.ref
0x2e3f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2e44  unbox.any [mscorlib]System.Int32
0x2e49  callvirt instance void Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsSessionSecurityTokenLifetimeInHours(int32 value)
0x2e4e  ldloc.0
0x2e4f  ret
```
