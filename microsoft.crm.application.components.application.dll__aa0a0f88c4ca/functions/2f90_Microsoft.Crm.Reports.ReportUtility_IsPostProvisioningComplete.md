# Microsoft.Crm.Reports.ReportUtility::IsPostProvisioningComplete

- ea: `0x2f90`
- end: `0x3008`
- name: `Microsoft.Crm.Reports.ReportUtility::IsPostProvisioningComplete`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2f90`

## string_xrefs

- `0x2fc7`: `PostProvisionComplete`
- `0x2fe6`: `PostProvisionComplete`
- `0x2ff3`: `PostProvisionComplete`
- `0x2fd2`: `IsPostProvisioningComplete`

## pseudocode

```c

```

## disassembly

```asm
0x2f90  ldc.i4.1
0x2f91  stloc.0
0x2f92  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x2f97  brtrue.s loc_3006
0x2f99  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x2f9e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x2fa3  ldc.i4.2
0x2fa4  bne.un.s loc_3006
0x2fa6  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x2fab  ldstr    aOrganization// "Organization"
0x2fb0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2fb5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2fba  box      [mscorlib]System.Guid
0x2fbf  ldc.i4.1
0x2fc0  newarr   [mscorlib]System.String
0x2fc5  dup
0x2fc6  ldc.i4.0
0x2fc7  ldstr    aPostprovisionc// "PostProvisionComplete"
0x2fcc  stelem.ref
0x2fcd  ldc.i4   0xC0
0x2fd2  ldstr    aIspostprovisio// "IsPostProvisioningComplete"
0x2fd7  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\1"...
0x2fdc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveById(string, object, string[], int32, string, string)
0x2fe1  stloc.1
0x2fe2  ldloc.1
0x2fe3  brfalse.s loc_3006
0x2fe5  ldloc.1
0x2fe6  ldstr    aPostprovisionc// "PostProvisionComplete"
0x2feb  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x2ff0  brfalse.s loc_3006
0x2ff2  ldloc.1
0x2ff3  ldstr    aPostprovisionc// "PostProvisionComplete"
0x2ff8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2ffd  unbox.any [mscorlib]System.Boolean
0x3002  brtrue.s loc_3006
0x3004  ldc.i4.0
0x3005  stloc.0
0x3006  ldloc.0
0x3007  ret
```
