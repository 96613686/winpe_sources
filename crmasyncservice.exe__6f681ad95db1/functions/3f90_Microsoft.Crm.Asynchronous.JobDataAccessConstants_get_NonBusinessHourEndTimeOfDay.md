# Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_NonBusinessHourEndTimeOfDay

- ea: `0x3f90`
- end: `0x3f9d`
- name: `Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_NonBusinessHourEndTimeOfDay`
- size: `13`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3410`
- `0x3b70`

## callees

- `0x3fc0`

## pseudocode

```c

```

## disassembly

```asm
0x3f90  ldstr    aOrgnonbusiness_0// "OrgNonBusinessHourEndTimeOfDay"
0x3f95  ldc.i4.0
0x3f96  ldc.i4.m1
0x3f97  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::GetConfigValue(string settingName, int32 minValue, int32 defaultValue)
0x3f9c  ret
```
