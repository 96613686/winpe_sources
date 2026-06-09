# SspRegistry::RegistryWatcher::WaitCallback(void *,uchar)

- ea: `0x18005a8a0`
- end: `0x18005a99a`
- name: `?WaitCallback@RegistryWatcher@SspRegistry@@CAXPEAXE@Z`
- size: `250`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18005a8a0`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005a8b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005a8b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a8e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a8e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005a993`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a977`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a977`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005a915`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005a915`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18005a955`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18005a955`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18005a927`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18005a927`

## pseudocode

```c

```
