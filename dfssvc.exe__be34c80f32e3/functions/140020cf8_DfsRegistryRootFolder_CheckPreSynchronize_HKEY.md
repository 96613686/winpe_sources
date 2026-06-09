# DfsRegistryRootFolder::CheckPreSynchronize(HKEY__ *)

- ea: `0x140020cf8`
- end: `0x140020e87`
- name: `?CheckPreSynchronize@DfsRegistryRootFolder@@AEAAXPEAUHKEY__@@@Z`
- size: `399`
- prototype: `void __fastcall(DfsRegistryRootFolder *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140021460`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140005f20`
- `0x140005f44`
- `0x14000abc4`
- `0x140020cf8`
- `0x14002e544`
- `0x140057f64`
- `0x14005a9f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140020d68`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140020d68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140020d96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140020d96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140020e29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140020e29`

## pseudocode

```c

```
