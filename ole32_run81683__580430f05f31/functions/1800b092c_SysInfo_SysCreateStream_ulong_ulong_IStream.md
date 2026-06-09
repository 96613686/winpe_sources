# SysInfo::SysCreateStream(ulong,ulong *,IStream * *)

- ea: `0x1800b092c`
- end: `0x1800b0a62`
- name: `?SysCreateStream@SysInfo@@QEAAJKPEAKPEAPEAUIStream@@@Z`
- size: `310`
- prototype: `HRESULT __fastcall(SysInfo *this, unsigned int grfMode, unsigned int *pstmix, IStream **ppstm)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800b4f50`

## callees

- `0x1800389b8`
- `0x180041c20`
- `0x1800b092c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b0951`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b09b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b0951`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b09b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b0970`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b09ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b0970`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b09ea`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfile` at `0x1800b0991`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfile` at `0x1800b0991`

## pseudocode

```c

```
