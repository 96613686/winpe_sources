# DllCanUnloadNow

- ea: `0x180005c10`
- end: `0x180005d55`
- name: `DllCanUnloadNow`
- size: `325`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005c10`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005c2d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005c2d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005d06`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005d06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ce2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ce2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cfd`

## pseudocode

```c

```
