# DeleteMappedAadAccountInfo(_GUID *,ushort const *)

- ea: `0x180040fe4`
- end: `0x180041207`
- name: `?DeleteMappedAadAccountInfo@@YAJPEAU_GUID@@PEBG@Z`
- size: `547`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *Src)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800571b0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x180040fe4`
- `0x180041210`
- `0x180042410`
- `0x18004317c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041199`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800411a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041199`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800411a2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180041121`
- `ntdll!RtlAcquireResourceExclusive` at `0x180041121`
- `ntdll!RtlReleaseResource` at `0x1800411bd`
- `ntdll!RtlReleaseResource` at `0x1800411bd`

## string_xrefs

- `0x18004102e`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18004108d`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x1800410e7`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`

## pseudocode

```c

```
