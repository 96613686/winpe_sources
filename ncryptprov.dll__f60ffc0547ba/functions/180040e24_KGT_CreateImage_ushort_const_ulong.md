# KGT_CreateImage(ushort const *,ulong)

- ea: `0x180040e24`
- end: `0x180040edd`
- name: `?KGT_CreateImage@@YAPEAUKEYGUARD_TELEMETRY_IMAGE_T@@PEBGK@Z`
- size: `185`
- prototype: `struct KEYGUARD_TELEMETRY_IMAGE_T *__fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b754`

## callees

- `0x18000af80`
- `0x180040794`
- `0x180040e24`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x180040e7e`
- `ntdll!RtlInitializeCriticalSection` at `0x180040e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040eac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040e3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040e3f`

## string_xrefs

- `0x180040e65`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\telemetry-image.cpp`
- `0x180040e94`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\telemetry-image.cpp`

## pseudocode

```c

```
