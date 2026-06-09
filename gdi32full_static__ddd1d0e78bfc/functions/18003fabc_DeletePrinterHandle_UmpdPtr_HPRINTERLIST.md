# DeletePrinterHandle(UmpdPtr &,_HPRINTERLIST *)

- ea: `0x18003fabc`
- end: `0x18003fb6e`
- name: `?DeletePrinterHandle@@YAXAEAVUmpdPtr@@PEAU_HPRINTERLIST@@@Z`
- size: `178`
- prototype: `void __fastcall(struct UmpdPtr *this, PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003bd20`

## callees

- `0x18003e930`
- `0x18003fabc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003fb62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fadb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fadb`
- `ntdll!RtlFreeHeap` at `0x18003fb43`
- `ntdll!RtlFreeHeap` at `0x18003fb43`

## pseudocode

```c

```
