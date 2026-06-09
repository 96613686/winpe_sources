# Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_MaxConcurrentOrgDBUpdateJobsPerAsyncServer

- ea: `0x3fa0`
- end: `0x3fb1`
- name: `Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_MaxConcurrentOrgDBUpdateJobsPerAsyncServer`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2b30`
- `0x33a0`
- `0x3410`

## callees

- `0x3fc0`

## string_xrefs

- `0x3fa0`: `MaxConcurrentOrgDBUpdateJobsPerAsyncServer`

## pseudocode

```c

```

## disassembly

```asm
0x3fa0  ldstr    aMaxconcurrento_0// "MaxConcurrentOrgDBUpdateJobsPerAsyncSer"...
0x3fa5  ldc.i4.1
0x3fa6  ldsfld   int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::_maxConcurrentOrgDBUpdateJobsPerAsyncServerDefault
0x3fab  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::GetConfigValue(string settingName, int32 minValue, int32 defaultValue)
0x3fb0  ret
```
