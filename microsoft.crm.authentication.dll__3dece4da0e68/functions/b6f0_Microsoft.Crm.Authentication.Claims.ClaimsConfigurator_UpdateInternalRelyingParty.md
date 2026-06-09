# Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::UpdateInternalRelyingParty

- ea: `0xb6f0`
- end: `0xb77b`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::UpdateInternalRelyingParty`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xb6c0`
- `0xb6f0`

## string_xrefs

- `0xb72b`: `UpdateInternalRelyingParty`
- `0xb730`: `D:\a\1\s\src\Platform\Authentication\Legacy\Claims\ClaimsConfigurator.cs`

## pseudocode

```c

```

## disassembly

```asm
0xb6f0  ldc.i4.2
0xb6f1  newarr   [mscorlib]System.String
0xb6f6  dup
0xb6f7  ldc.i4.0
0xb6f8  ldstr    aAdrootdomainsc// "ADRootDomainScheme"
0xb6fd  stelem.ref
0xb6fe  dup
0xb6ff  ldc.i4.1
0xb700  ldstr    aAdwebapplicati// "ADWebApplicationRootDomain"
0xb705  stelem.ref
0xb706  stloc.0
0xb707  ldnull
0xb708  stloc.1
0xb709  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xb70e  stloc.3
0xb70f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xb714  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentId()
0xb719  stloc.s  4
0xb71b  ldloc.3
0xb71c  ldstr    aDeployment// "Deployment"
0xb721  ldloc.s  4
0xb723  box      [mscorlib]System.Guid
0xb728  ldloc.0
0xb729  ldc.i4.s 0x5D
0xb72b  ldstr    aUpdateinternal// "UpdateInternalRelyingParty"
0xb730  ldstr    aDA1SSrcPlatfor_5// "D:\\a\\1\\s\\src\\Platform\\Authenticat"...
0xb735  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string, object, string[], int32, string, string)
0xb73a  stloc.1
0xb73b  leave.s  loc_B747
0xb73d  ldloc.3
0xb73e  brfalse.s loc_B746
0xb740  ldloc.3
0xb741  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb746  endfinally
0xb747  ldloc.1
0xb748  ldloc.0
0xb749  ldc.i4.0
0xb74a  ldelem.ref
0xb74b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xb750  callvirt instance string [mscorlib]System.Object::ToString()
0xb755  ldstr    asc_191F8// "://"
0xb75a  ldloc.1
0xb75b  ldloc.0
0xb75c  ldc.i4.1
0xb75d  ldelem.ref
0xb75e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xb763  callvirt instance string [mscorlib]System.Object::ToString()
0xb768  call     string [mscorlib]System.String::Concat(string, string, string)
0xb76d  newobj   instance void [System]System.Uri::.ctor(string)
0xb772  stloc.2
0xb773  ldarg.0
0xb774  ldloc.2
0xb775  call     void Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::SetInternalRelyingPartyIdentifierUrl(valuetype [mscorlib]System.Guid federationProviderId, class [System]System.Uri uri)
0xb77a  ret
```
