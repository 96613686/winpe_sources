# Microsoft.Crm.Tools.Admin.ClaimsConfiguration::UpdateClaimsSessionSecurityTokenLifetimeInHours

- ea: `0x3000`
- end: `0x306e`
- name: `Microsoft.Crm.Tools.Admin.ClaimsConfiguration::UpdateClaimsSessionSecurityTokenLifetimeInHours`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x2eb0`

## callees

- `0x3000`

## string_xrefs

- `0x3008`: `ClaimsSessionSecurityTokenLifetime`
- `0x304c`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Claims\ClaimsConfigurator.cs`
- `0x3047`: `UpdateClaimsSessionSecurityTokenLifetimeInHours`

## pseudocode

```c

```

## disassembly

```asm
0x3000  ldc.i4.1
0x3001  newarr   [mscorlib]System.String
0x3006  dup
0x3007  ldc.i4.0
0x3008  ldstr    aClaimssessions// "ClaimsSessionSecurityTokenLifetime"
0x300d  stelem.ref
0x300e  stloc.0
0x300f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3014  stloc.1
0x3015  ldloc.1
0x3016  ldloc.0
0x3017  ldc.i4.0
0x3018  ldelem.ref
0x3019  ldarg.0
0x301a  box      [mscorlib]System.Int32
0x301f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3024  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x3029  stloc.2
0x302a  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x302f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentId()
0x3034  stloc.3
0x3035  ldloc.2
0x3036  ldstr    aDeployment// "Deployment"
0x303b  ldloc.3
0x303c  box      [mscorlib]System.Guid
0x3041  ldloc.1
0x3042  ldc.i4   0xD5
0x3047  ldstr    aUpdateclaimsse// "UpdateClaimsSessionSecurityTokenLifetim"...
0x304c  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x3051  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x3056  pop
0x3057  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x305c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Flush()
0x3061  leave.s  loc_306D
0x3063  ldloc.2
0x3064  brfalse.s loc_306C
0x3066  ldloc.2
0x3067  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x306c  endfinally
0x306d  ret
```
