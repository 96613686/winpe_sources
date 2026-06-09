# PcaStoreGetValueAlloc(void * *,unsigned __int64 *,unsigned __int64,ushort const *,_PCA_SLOT_ID)

- ea: `0x18000f2f4`
- end: `0x18000f6bb`
- name: `?PcaStoreGetValueAlloc@@YAKPEAPEAXPEA_K_KPEBGW4_PCA_SLOT_ID@@@Z`
- size: `967`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800085b8`
- `0x18000f234`
- `0x180016ed0`

## callees

- `0x18000f078`
- `0x18000f2f4`
- `0x180011178`
- `0x180012920`
- `0x180056256`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x18000f40d`
- `ntdll!RtlComputeCrc32` at `0x18000f40d`
- `ntdll!RtlFreeHeap` at `0x18000f3a3`
- `ntdll!RtlFreeHeap` at `0x18000f50a`
- `ntdll!RtlFreeHeap` at `0x18000f6af`
- `ntdll!RtlFreeHeap` at `0x18000f3a3`
- `ntdll!RtlFreeHeap` at `0x18000f50a`
- `ntdll!RtlFreeHeap` at `0x18000f6af`
- `ntdll!RtlAllocateHeap` at `0x18000f471`
- `ntdll!RtlAllocateHeap` at `0x18000f58f`
- `ntdll!RtlAllocateHeap` at `0x18000f471`
- `ntdll!RtlAllocateHeap` at `0x18000f58f`

## string_xrefs

- `0x18000f5e4`: `Stream read failed [%d]`
- `0x18000f68e`: `Failed to compute checksum`

## pseudocode

```c

```
