# Microsoft.Crm.CrmSqlAcccessTimeoutConfig::GetCommandTimeoutInSecond

- ea: `0xf900`
- end: `0xf96b`
- name: `Microsoft.Crm.CrmSqlAcccessTimeoutConfig::GetCommandTimeoutInSecond`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd1a0`

## callees

- `0xb10`
- `0xfa0`
- `0x1350`
- `0x1f80`
- `0xf900`
- `0xf970`
- `0xf980`
- `0xf9a0`
- `0x33840`

## string_xrefs

- `0xf944`: `SqlCommandTimeout`
- `0xf956`: `SqlCommandTimeout`

## pseudocode

```c

```

## disassembly

```asm
0xf900  ldc.i4.m1
0xf901  stloc.0
0xf902  ldc.i4.1
0xf903  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0xf908  bne.un.s loc_F910
0xf90a  call     int32 Microsoft.Crm.CrmSqlAcccessTimeoutConfig::GetCommandTimeoutOrInvalidValueInSecond()
0xf90f  stloc.0
0xf910  ldc.i4.m1
0xf911  ldloc.0
0xf912  bne.un.s loc_F969
0xf914  call     bool Microsoft.Crm.RegControl::IsInServerContext()
0xf919  brfalse.s loc_F963
0xf91b  ldarg.0
0xf91c  call     int32 Microsoft.Crm.CrmSqlAcccessTimeoutConfig::GetOrganizationCommandTimeoutOrInvalidValueInSecond(valuetype [mscorlib]System.Guid organizationId)
0xf921  stloc.1
0xf922  ldloc.1
0xf923  ldc.i4.m1
0xf924  beq.s    loc_F92A
0xf926  ldloc.1
0xf927  stloc.0
0xf928  br.s     loc_F969
0xf92a  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0xf92f  ldc.i4.2
0xf930  bne.un.s loc_F951
0xf932  call     class Microsoft.Crm.IOrganizationMetadataProvider Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0xf937  ldarg.0
0xf938  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid organizationId)
0xf93d  stloc.2
0xf93e  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xf943  ldloc.2
0xf944  ldstr    aSqlcommandtime// "SqlCommandTimeout"
0xf949  callvirt T0x2B000043
0xf94e  stloc.0
0xf94f  br.s     loc_F969
0xf951  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xf956  ldstr    aSqlcommandtime// "SqlCommandTimeout"
0xf95b  callvirt T0x2B00003E
0xf960  stloc.0
0xf961  br.s     loc_F969
0xf963  call     int32 Microsoft.Crm.CrmSqlAcccessTimeoutConfig::GetCommandTimeoutOrDefaultInSecond()
0xf968  stloc.0
0xf969  ldloc.0
0xf96a  ret
```
