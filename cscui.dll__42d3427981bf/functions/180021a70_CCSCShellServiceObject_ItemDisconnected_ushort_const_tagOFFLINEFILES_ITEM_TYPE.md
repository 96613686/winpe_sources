# CCSCShellServiceObject::ItemDisconnected(ushort const *,tagOFFLINEFILES_ITEM_TYPE)

- ea: `0x180021a70`
- end: `0x180021b43`
- name: `?ItemDisconnected@CCSCShellServiceObject@@UEAAJPEBGW4tagOFFLINEFILES_ITEM_TYPE@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(CCSCShellServiceObject *__hidden this, const unsigned __int16 *, enum tagOFFLINEFILES_ITEM_TYPE)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180008348`
- `0x180021a70`
- `0x180022110`
- `0x18003fc84`
- `0x18003ff70`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180021ab5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180021ab5`
- `ntdll!RtlReleaseResource` at `0x180021b0e`
- `ntdll!RtlReleaseResource` at `0x180021b0e`
- `ntdll!RtlAcquireResourceShared` at `0x180021a91`
- `ntdll!RtlAcquireResourceShared` at `0x180021a91`

## pseudocode

```c

```
