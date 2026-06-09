# Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::GetInternalFederationMetadataUrl

- ea: `0xb8f0`
- end: `0xb993`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::GetInternalFederationMetadataUrl`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xb8f0`

## string_xrefs

- `0xb931`: `D:\a\1\s\src\Platform\Authentication\Legacy\Claims\ClaimsConfigurator.cs`

## pseudocode

```c

```

## disassembly

```asm
0xb8f0  ldc.i4.2
0xb8f1  newarr   [mscorlib]System.String
0xb8f6  dup
0xb8f7  ldc.i4.0
0xb8f8  ldstr    aAdrootdomainsc// "ADRootDomainScheme"
0xb8fd  stelem.ref
0xb8fe  dup
0xb8ff  ldc.i4.1
0xb900  ldstr    aAdwebapplicati// "ADWebApplicationRootDomain"
0xb905  stelem.ref
0xb906  stloc.0
0xb907  ldnull
0xb908  stloc.1
0xb909  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xb90e  stloc.2
0xb90f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xb914  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentId()
0xb919  stloc.3
0xb91a  ldloc.2
0xb91b  ldstr    aDeployment// "Deployment"
0xb920  ldloc.3
0xb921  box      [mscorlib]System.Guid
0xb926  ldloc.0
0xb927  ldc.i4   0xCD
0xb92c  ldstr    aGetinternalfed// "GetInternalFederationMetadataUrl"
0xb931  ldstr    aDA1SSrcPlatfor_5// "D:\\a\\1\\s\\src\\Platform\\Authenticat"...
0xb936  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string, object, string[], int32, string, string)
0xb93b  stloc.1
0xb93c  leave.s  loc_B948
0xb93e  ldloc.2
0xb93f  brfalse.s loc_B947
0xb941  ldloc.2
0xb942  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb947  endfinally
0xb948  ldc.i4.5
0xb949  newarr   [mscorlib]System.String
0xb94e  dup
0xb94f  ldc.i4.0
0xb950  ldloc.1
0xb951  ldloc.0
0xb952  ldc.i4.0
0xb953  ldelem.ref
0xb954  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xb959  callvirt instance string [mscorlib]System.Object::ToString()
0xb95e  stelem.ref
0xb95f  dup
0xb960  ldc.i4.1
0xb961  ldstr    asc_191F8// "://"
0xb966  stelem.ref
0xb967  dup
0xb968  ldc.i4.2
0xb969  ldloc.1
0xb96a  ldloc.0
0xb96b  ldc.i4.1
0xb96c  ldelem.ref
0xb96d  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xb972  callvirt instance string [mscorlib]System.Object::ToString()
0xb977  stelem.ref
0xb978  dup
0xb979  ldc.i4.3
0xb97a  ldstr    asc_1C878// "/"
0xb97f  stelem.ref
0xb980  dup
0xb981  ldc.i4.4
0xb982  ldsfld   string Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::crmFederationMetadataPath
0xb987  stelem.ref
0xb988  call     string [mscorlib]System.String::Concat(string[])
0xb98d  newobj   instance void [System]System.Uri::.ctor(string)
0xb992  ret
```
