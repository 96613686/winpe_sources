# DeletePrinterHandle(UmpdPtr &,_HPRINTERLIST *)

- ea: `0x180045c64`
- end: `0x180045d05`
- name: `?DeletePrinterHandle@@YAXAEAVUmpdPtr@@PEAU_HPRINTERLIST@@@Z`
- size: `161`
- prototype: `void __fastcall(struct UmpdPtr *this, PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180042030`

## callees

- `0x180044b88`
- `0x180045c64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045cfe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c83`
- `ntdll!RtlFreeHeap` at `0x180045ce5`
- `ntdll!RtlFreeHeap` at `0x180045ce5`

## pseudocode

```c

```
