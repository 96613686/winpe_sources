# NlSitesAddSubnet(ushort *,ushort *,ushort *)

- ea: `0x180044cc0`
- end: `0x180044f34`
- name: `?NlSitesAddSubnet@@YAKPEAG00@Z`
- size: `628`
- prototype: `unsigned int __fastcall(unsigned __int16 *Src, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180044f3c`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x180043e94`
- `0x180044cc0`
- `0x18004a068`
- `0x18004b2c0`
- `0x180083828`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044dcc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044ef4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044ef4`
- `ntdll!RtlLeaveCriticalSection` at `0x180044f14`
- `ntdll!RtlLeaveCriticalSection` at `0x180044f14`
- `ntdll!RtlEnterCriticalSection` at `0x180044cf4`
- `ntdll!RtlEnterCriticalSection` at `0x180044cf4`

## string_xrefs

- `0x180044e47`: `onecore\ds\netapi\svcdlls\logonsrv\server\nlsite.cxx`
- `0x180044e72`: `%ld: Subnet already exists %ld\n`

## pseudocode

```c

```
