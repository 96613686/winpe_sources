# SysInfo::SysCreateStream(ulong,ulong *,IStream * *)

- ea: `0x1800b8cfc`
- end: `0x1800b8e5c`
- name: `?SysCreateStream@SysInfo@@QEAAJKPEAKPEAPEAUIStream@@@Z`
- size: `352`
- prototype: `HRESULT __fastcall(SysInfo *this, unsigned int grfMode, unsigned int *pstmix, IStream **ppstm)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800bd090`

## callees

- `0x18003d050`
- `0x180043fdc`
- `0x1800b8cfc`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8d48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8dd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8d48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8dd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8d23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8d9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8d23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8d9d`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfile` at `0x1800b8d6f`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfile` at `0x1800b8d6f`

## pseudocode

```c

```
