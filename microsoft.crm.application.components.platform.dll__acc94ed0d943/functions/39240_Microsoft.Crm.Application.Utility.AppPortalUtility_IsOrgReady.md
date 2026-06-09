# Microsoft.Crm.Application.Utility.AppPortalUtility::IsOrgReady

- ea: `0x39240`
- end: `0x392eb`
- name: `Microsoft.Crm.Application.Utility.AppPortalUtility::IsOrgReady`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x39240`
- `0x393d0`

## string_xrefs

- `0x39265`: `ConfigurationStatusCode`
- `0x39298`: `ConfigurationStatusCode`
- `0x392c3`: `ConfigurationStatusCode`
- `0x392af`: `IsOrgReady`

## pseudocode

```c

```

## disassembly

```asm
0x39240  ldarg.0
0x39241  ldstr    aOrganizationid_0// "organizationId"
0x39246  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3924b  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x39250  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x39255  ldc.i4.2
0x39256  beq.s    loc_3925A
0x39258  ldc.i4.1
0x39259  ret
0x3925a  ldarg.0
0x3925b  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Application.Utility.AppPortalUtility::RetrieveCachedOrgInfo(valuetype [mscorlib]System.Guid organizationId)
0x39260  stloc.0
0x39261  ldloc.0
0x39262  brfalse.s loc_39279
0x39264  ldloc.0
0x39265  ldstr    aConfigurations// "ConfigurationStatusCode"
0x3926a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3926f  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleConfigurationStatus
0x39274  ldc.i4.4
0x39275  bne.un.s loc_39279
0x39277  ldc.i4.1
0x39278  ret
0x39279  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3927e  stloc.1
0x3927f  ldloc.1
0x39280  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x39285  ldarg.0
0x39286  box      [mscorlib]System.Guid
0x3928b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x39290  ldc.i4.1
0x39291  newarr   [mscorlib]System.String
0x39296  dup
0x39297  ldc.i4.0
0x39298  ldstr    aConfigurations// "ConfigurationStatusCode"
0x3929d  stelem.ref
0x3929e  stloc.2
0x3929f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x392a4  stloc.3
0x392a5  ldloc.3
0x392a6  ldstr    aOrganizationli// "OrganizationLifecycle"
0x392ab  ldloc.2
0x392ac  ldloc.1
0x392ad  ldc.i4.s 0x6D
0x392af  ldstr    aIsorgready// "IsOrgReady"
0x392b4  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\2"...
0x392b9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x392be  stloc.0
0x392bf  ldloc.0
0x392c0  brfalse.s loc_392DA
0x392c2  ldloc.0
0x392c3  ldstr    aConfigurations// "ConfigurationStatusCode"
0x392c8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x392cd  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleConfigurationStatus
0x392d2  ldc.i4.4
0x392d3  bne.un.s loc_392DA
0x392d5  ldc.i4.1
0x392d6  stloc.s  4
0x392d8  leave.s  loc_392E8
0x392da  leave.s  loc_392E6
0x392dc  ldloc.3
0x392dd  brfalse.s loc_392E5
0x392df  ldloc.3
0x392e0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x392e5  endfinally
0x392e6  ldc.i4.0
0x392e7  ret
0x392e8  ldloc.s  4
0x392ea  ret
```
