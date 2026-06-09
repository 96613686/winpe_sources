# HcsModifyProcess

- ea: `0x180016e50`
- end: `0x18001716b`
- name: `HcsModifyProcess`
- size: `795`
- prototype: `HRESULT __stdcall(HCS_PROCESS process, HCS_OPERATION operation, PCWSTR settings)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x18000b948`
- `0x180013de8`
- `0x1800144a4`
- `0x180014f14`
- `0x180015150`
- `0x18001587c`
- `0x180016e50`
- `0x18002af88`
- `0x18002c41c`
- `0x18002cd14`
- `0x180049604`
- `0x180049b6c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017066`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017066`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001702e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001702e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18001705d`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18001705d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001701a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001701a`

## string_xrefs

- `0x180017133`: `onecore\vm\compute\dll\core\src\process.cpp`
- `0x180017148`: `onecore\vm\compute\dll\lib\core\clientprocess.cpp`
- `0x18001715a`: `onecore\vm\compute\shared\rundownreference\rundownreference.cpp`

## pseudocode

```c

```
