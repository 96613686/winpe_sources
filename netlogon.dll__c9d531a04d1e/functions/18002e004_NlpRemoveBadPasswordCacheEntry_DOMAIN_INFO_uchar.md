# NlpRemoveBadPasswordCacheEntry(_DOMAIN_INFO *,uchar *)

- ea: `0x18002e004`
- end: `0x18002e0d3`
- name: `?NlpRemoveBadPasswordCacheEntry@@YAXPEAU_DOMAIN_INFO@@PEAE@Z`
- size: `207`
- prototype: `void __fastcall(struct _DOMAIN_INFO *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002e730`

## callees

- `0x18002e004`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002e080`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002e080`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e02a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e02a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0bd`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e0b4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e0b4`
- `ntdll!RtlEnterCriticalSection` at `0x18002e064`
- `ntdll!RtlEnterCriticalSection` at `0x18002e064`

## pseudocode

```c

```
