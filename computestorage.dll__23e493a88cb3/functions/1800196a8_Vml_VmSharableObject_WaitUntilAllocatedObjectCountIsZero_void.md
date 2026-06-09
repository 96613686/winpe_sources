# Vml::VmSharableObject::WaitUntilAllocatedObjectCountIsZero(void)

- ea: `0x1800196a8`
- end: `0x1800198ab`
- name: `?WaitUntilAllocatedObjectCountIsZero@VmSharableObject@Vml@@SAXXZ`
- size: `515`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016e5c`

## callees

- `0x180002690`
- `0x180015a40`
- `0x180015b20`
- `0x18001723c`
- `0x180017a80`
- `0x1800196a8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800197b2`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800197b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001980f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001980f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019760`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019760`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019716`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019716`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001974b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001977f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800197d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800197e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001974b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001977f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800197d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800197e6`

## string_xrefs

- `0x180019874`: `Detected a leaked instance - this leak should be fixed ASAP - terminating process rather than waiting forever or risking crash during module cleanup due to invalid state.\n`

## pseudocode

```c

```
