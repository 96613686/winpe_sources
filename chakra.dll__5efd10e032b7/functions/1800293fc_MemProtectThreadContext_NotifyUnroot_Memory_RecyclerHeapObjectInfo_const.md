# MemProtectThreadContext::NotifyUnroot(Memory::RecyclerHeapObjectInfo const &)

- ea: `0x1800293fc`
- end: `0x180029645`
- name: `?NotifyUnroot@MemProtectThreadContext@@QEAAXAEBVRecyclerHeapObjectInfo@Memory@@@Z`
- size: `585`
- prototype: `void __fastcall(MemProtectThreadContext *__hidden this, const struct Memory::RecyclerHeapObjectInfo *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180494040`
- `0x18049440c`

## callees

- `0x1800293fc`
- `0x18002964c`
- `0x18002a098`
- `0x1801f197c`
- `0x18048e568`
- `0x1805a9e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029536`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029536`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800295db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800295db`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800294e9`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800294e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002962a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002962a`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800295af`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800295af`

## pseudocode

```c

```
