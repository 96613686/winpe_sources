# IMAGE_HEADER_INFO::ReadCHPEMetadata(ProcessInfo *,unsigned __int64,unsigned __int64,ulong,void *,ulong,_IMAGE_SECTION_HEADER *,unsigned __int64)

- ea: `0x18027d540`
- end: `0x18027d921`
- name: `?ReadCHPEMetadata@IMAGE_HEADER_INFO@@QEAAXPEAVProcessInfo@@_K1KPEAXKPEAU_IMAGE_SECTION_HEADER@@1@Z`
- size: `993`
- prototype: `void(IMAGE_HEADER_INFO *__hidden this, struct ProcessInfo *, unsigned __int64, unsigned __int64, unsigned int, void *, unsigned int, struct _IMAGE_SECTION_HEADER *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180080870`

## callees

- `0x180086560`
- `0x180099b04`
- `0x1800b94c4`
- `0x1800f0f40`
- `0x18027d540`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18027d673`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18027d69a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18027d673`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18027d69a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18027d6c3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18027d6df`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18027d6c3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18027d6df`
- `ntdll!RtlAreBitsClear` at `0x18027d89c`
- `ntdll!RtlAreBitsClear` at `0x18027d89c`
- `ntdll!RtlSetBits` at `0x18027d8fa`
- `ntdll!RtlSetBits` at `0x18027d8fa`
- `ntdll!RtlInitializeBitMap` at `0x18027d73b`
- `ntdll!RtlInitializeBitMap` at `0x18027d73b`

## pseudocode

```c

```
