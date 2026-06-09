# Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_NonBusinessHourStartTimeOfDay

- ea: `0x3f80`
- end: `0x3f8d`
- name: `Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_NonBusinessHourStartTimeOfDay`
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
0x3f80  ldstr    aOrgnonbusiness// "OrgNonBusinessHourStartTimeOfDay"
0x3f85  ldc.i4.0
0x3f86  ldc.i4.m1
0x3f87  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::GetConfigValue(string settingName, int32 minValue, int32 defaultValue)
0x3f8c  ret
```
