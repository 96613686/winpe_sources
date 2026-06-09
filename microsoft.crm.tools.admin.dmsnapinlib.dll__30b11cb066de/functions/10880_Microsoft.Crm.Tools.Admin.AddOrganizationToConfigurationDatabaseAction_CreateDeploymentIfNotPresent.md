# Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::CreateDeploymentIfNotPresent

- ea: `0x10880`
- end: `0x10902`
- name: `Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::CreateDeploymentIfNotPresent`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x105a0`

## callees

- `0x71d0`
- `0x8630`
- `0x8d70`
- `0x10880`

## string_xrefs

- `0x108a5`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\DatabaseConfiguration.cs`
- `0x108a0`: `CreateDeploymentIfNotPresent`
- `0x108c2`: `ConfigUtility.CreateDeployment for OrganizationId = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x10880  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x10885  stloc.0
0x10886  ldloc.0
0x10887  ldstr    aDeployment// "Deployment"
0x1088c  ldc.i4.1
0x1088d  newarr   [mscorlib]System.String
0x10892  dup
0x10893  ldc.i4.0
0x10894  ldstr    aId// "Id"
0x10899  stelem.ref
0x1089a  ldnull
0x1089b  ldc.i4   0x11E
0x108a0  ldstr    aCreatedeployme// "CreateDeploymentIfNotPresent"
0x108a5  ldstr    aDDbsShDccm2110_9// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x108aa  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x108af  stloc.1
0x108b0  ldloc.1
0x108b1  brfalse.s loc_108BB
0x108b3  ldloc.1
0x108b4  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x108b9  brtrue.s loc_108F5
0x108bb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x108c0  ldc.i4.s 0xA
0x108c2  ldstr    aConfigutilityC// "ConfigUtility.CreateDeployment for Orga"...
0x108c7  ldc.i4.1
0x108c8  newarr   [mscorlib]System.Object
0x108cd  dup
0x108ce  ldc.i4.0
0x108cf  ldarg.0
0x108d0  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationInfo()
0x108d5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x108da  box      [mscorlib]System.Guid
0x108df  stelem.ref
0x108e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x108e5  ldarg.0
0x108e6  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationInfo()
0x108eb  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqmOptIn()
0x108f0  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ConfigUtility::CreateDeployment(bool)
0x108f5  leave.s  loc_10901
0x108f7  ldloc.0
0x108f8  brfalse.s loc_10900
0x108fa  ldloc.0
0x108fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10900  endfinally
0x10901  ret
```
