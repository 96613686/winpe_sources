# Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::GetTimeLimit

- ea: `0x256e0`
- end: `0x25770`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::GetTimeLimit`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x25630`

## callees

- `0x256e0`

## string_xrefs

- `0x256e5`: `UpgradeTaskTimeLimitInMinutes`
- `0x2570d`: `UpgradeTaskTimeLimitInMinutes`
- `0x256f5`: `SiteSetting UpgradeTaskTimeLimitInMinutes should be configured and should be greater than 0`
- `0x25719`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\OrganizationUpgradeExecutor.cs`
- `0x25741`: `Organization Setting UpgradeTaskTimeLimitInMinutes should be configured and should be greater than 0. Current Value: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x256e0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x256e5  ldstr    aUpgradetasktim// "UpgradeTaskTimeLimitInMinutes"
0x256ea  ldc.i4.0
0x256eb  callvirt T0x2B000013
0x256f0  stloc.0
0x256f1  ldloc.0
0x256f2  ldc.i4.0
0x256f3  bgt.s    loc_25700
0x256f5  ldstr    aSitesettingUpg// "SiteSetting UpgradeTaskTimeLimitInMinut"...
0x256fa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x256ff  throw
0x25700  ldarg.1
0x25701  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::get_OrganizationId()
0x25706  stloc.1
0x25707  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x2570c  ldloc.1
0x2570d  ldstr    aUpgradetasktim// "UpgradeTaskTimeLimitInMinutes"
0x25712  ldc.i4.s 0x53
0x25714  ldstr    aGettimelimit// "GetTimeLimit"
0x25719  ldstr    aDDbsShDccm2110_38// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2571e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x25723  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x25728  stloc.2
0x25729  ldloca.s 2
0x2572b  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x25730  brfalse.s loc_2576E
0x25732  ldloca.s 2
0x25734  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x25739  ldc.i4.0
0x2573a  bge.s    loc_25766
0x2573c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25741  ldstr    aOrganizationSe// "Organization Setting UpgradeTaskTimeLim"...
0x25746  ldc.i4.1
0x25747  newarr   [mscorlib]System.Object
0x2574c  dup
0x2574d  ldc.i4.0
0x2574e  ldloca.s 2
0x25750  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x25755  box      [mscorlib]System.Int32
0x2575a  stelem.ref
0x2575b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25760  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x25765  throw
0x25766  ldloca.s 2
0x25768  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x2576d  stloc.0
0x2576e  ldloc.0
0x2576f  ret
```
