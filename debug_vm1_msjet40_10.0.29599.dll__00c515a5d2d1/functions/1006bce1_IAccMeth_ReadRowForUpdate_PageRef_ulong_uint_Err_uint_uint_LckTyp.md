# IAccMeth::ReadRowForUpdate(PageRef &,ulong,uint,Err &,uint,uint,LckTyp *)

- ea: `0x1006bce1`
- end: `0x1006bd62`
- name: `?ReadRowForUpdate@IAccMeth@@QAEXAAVPageRef@@KIAAVErr@@IIPAW4LckTyp@@@Z`
- size: `129`
- prototype: `void __thiscall(IAccMeth *__hidden this, struct PageRef *, unsigned int, unsigned int, struct Err *, char, unsigned int, enum LckTyp *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1006e5f5`
- `0x1006f3ee`

## callees

- `0x10057736`
- `0x1006bce1`
- `0x10074d41`
- `0x10076da6`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1006bd55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1006bd55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1006bcf9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1006bcf9`

## pseudocode

```c

```
