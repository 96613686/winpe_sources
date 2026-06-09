# NlpRemoveBadPasswordCacheEntry(_DOMAIN_INFO *,uchar *)

- ea: `0x18002fbac`
- end: `0x18002fca0`
- name: `?NlpRemoveBadPasswordCacheEntry@@YAXPEAU_DOMAIN_INFO@@PEAE@Z`
- size: `244`
- prototype: `void __fastcall(struct _DOMAIN_INFO *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003033c`

## callees

- `0x18002fbac`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002fc34`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002fc34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fbd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fbd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc83`
- `ntdll!RtlLeaveCriticalSection` at `0x18002fc74`
- `ntdll!RtlLeaveCriticalSection` at `0x18002fc74`
- `ntdll!RtlEnterCriticalSection` at `0x18002fc12`
- `ntdll!RtlEnterCriticalSection` at `0x18002fc12`

## pseudocode

```c

```
