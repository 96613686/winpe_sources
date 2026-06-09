# IAccMeth::ReadRowForUpdate(PageRef &,ulong,uint,Err &,uint,uint,LckTyp *)

- ea: `0x1006bb51`
- end: `0x1006bbd2`
- name: `?ReadRowForUpdate@IAccMeth@@QAEXAAVPageRef@@KIAAVErr@@IIPAW4LckTyp@@@Z`
- size: `129`
- prototype: `void __thiscall(IAccMeth *__hidden this, struct PageRef *, unsigned int, unsigned int, struct Err *, char, unsigned int, enum LckTyp *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1006e465`
- `0x1006f25e`

## callees

- `0x100575a6`
- `0x1006bb51`
- `0x10074bb1`
- `0x10076c16`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1006bbc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1006bbc5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1006bb69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1006bb69`

## pseudocode

```c

```
