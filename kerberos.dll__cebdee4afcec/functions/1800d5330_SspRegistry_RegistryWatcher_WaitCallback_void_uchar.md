# SspRegistry::RegistryWatcher::WaitCallback(void *,uchar)

- ea: `0x1800d5330`
- end: `0x1800d542a`
- name: `?WaitCallback@RegistryWatcher@SspRegistry@@CAXPEAXE@Z`
- size: `250`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800d5330`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d5423`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d5407`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d5407`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d5349`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d5349`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d5375`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d5375`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800d53a5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800d53a5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800d53b7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800d53b7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800d53e5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800d53e5`

## pseudocode

```c

```
