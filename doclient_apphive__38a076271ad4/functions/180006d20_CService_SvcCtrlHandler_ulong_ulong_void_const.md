# CService::_SvcCtrlHandler(ulong,ulong,void const *)

- ea: `0x180006d20`
- end: `0x180006e8b`
- name: `?_SvcCtrlHandler@CService@@AEAAKKKPEBX@Z`
- size: `363`
- prototype: `unsigned int(CService *__hidden this, unsigned int, unsigned int, const void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180006bf0`

## callees

- `0x18000696c`
- `0x1800069ec`
- `0x180006ae8`
- `0x180006d20`
- `0x18007e7c4`
- `0x1800a1ea4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006dd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006e18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006dd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006e18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006d6d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006d6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006d84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006d84`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006db9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006dfa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006db9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006dfa`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180006e0f`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180006e0f`

## string_xrefs

- `0x180006d9c`: `Service trigger event: entering OnPolicyChange`
- `0x180006d8a`: `CService::_SvcCtrlHandler`
- `0x180006e20`: `Service trigger event: shutting down and restarting`

## pseudocode

```c

```
