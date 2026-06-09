# Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::Validate

- ea: `0x2020`
- end: `0x20d1`
- name: `Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::Validate`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e40`

## callees

- `0x2020`

## string_xrefs

- `0x2071`: `Invalid value for ProfUserLicenseStorageAmountMB: `
- `0x20c0`: `Value has not been specified for D365UserLicenseStorageAmountMB setting.`

## pseudocode

```c

```

## disassembly

```asm
0x2020  ldarg.0
0x2021  ldfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_professionalUserLicenseStorageStep
0x2026  ldc.i4.1
0x2027  bge.s    loc_2044
0x2029  ldstr    aInvalidValueFo// "Invalid value for ProfUserLicenseStorag"...
0x202e  ldarg.0
0x202f  ldfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_professionalUserLicenseStorageStep
0x2034  box      [mscorlib]System.Int32
0x2039  call     string [mscorlib]System.String::Concat(object, object)
0x203e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2043  throw
0x2044  ldarg.0
0x2045  ldfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_professionalUserLicenseTestInstanceStep
0x204a  ldc.i4.1
0x204b  bge.s    loc_2068
0x204d  ldstr    aInvalidValueFo_0// "Invalid value for ProfUserLicenseTestIn"...
0x2052  ldarg.0
0x2053  ldfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_professionalUserLicenseTestInstanceStep
0x2058  box      [mscorlib]System.Int32
0x205d  call     string [mscorlib]System.String::Concat(object, object)
0x2062  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2067  throw
0x2068  ldarg.0
0x2069  ldfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_professionalUserLicenseStorageAmountInMb
0x206e  ldc.i4.0
0x206f  bge.s    loc_208C
0x2071  ldstr    aInvalidValueFo_1// "Invalid value for ProfUserLicenseStorag"...
0x2076  ldarg.0
0x2077  ldfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_professionalUserLicenseStorageAmountInMb
0x207c  box      [mscorlib]System.Int32
0x2081  call     string [mscorlib]System.String::Concat(object, object)
0x2086  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x208b  throw
0x208c  ldarg.0
0x208d  ldfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_d365UserLicenseStorageStep
0x2092  ldc.i4.0
0x2093  bgt.s    loc_20AE
0x2095  ldnull
0x2096  ldarg.0
0x2097  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_organizationId
0x209c  ldc.i4.s 0xA
0x209e  ldstr    aValueHasNotBee_1// "Value has not been specified for D365Us"...
0x20a3  ldc.i4.0
0x20a4  newarr   [mscorlib]System.Object
0x20a9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20ae  ldarg.0
0x20af  ldfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_d365UserLicenseStorageAmountInMb
0x20b4  ldc.i4.0
0x20b5  bgt.s    loc_20D0
0x20b7  ldnull
0x20b8  ldarg.0
0x20b9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_organizationId
0x20be  ldc.i4.s 0xA
0x20c0  ldstr    aValueHasNotBee_2// "Value has not been specified for D365Us"...
0x20c5  ldc.i4.0
0x20c6  newarr   [mscorlib]System.Object
0x20cb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20d0  ret
```
