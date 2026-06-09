# UfhpUtilityStoreDeleteAboveQuota(HKEY__ *,_UFH_DATA_TYPE)

- ea: `0x18003ba5c`
- end: `0x18003bbb9`
- name: `?UfhpUtilityStoreDeleteAboveQuota@@YAKPEAUHKEY__@@W4_UFH_DATA_TYPE@@@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180035458`

## callees

- `0x18003ba5c`
- `0x18007a9cf`
- `0x1800f13f8`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_itow_s` at `0x18003bb52`
- `msvcrt!_itow_s` at `0x18003bb52`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003bb20`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003bb7a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003bb20`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003bb7a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003bb33`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003bb90`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003bb33`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003bb90`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003bb60`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003bb60`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003baf4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003baf4`

## pseudocode

```c

```
