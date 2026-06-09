# PEWriteResource<_IMAGE_NT_HEADERS>(int,int,ulong,_UPDATEDATA *,_IMAGE_NT_HEADERS *)

- ea: `0x18004d0dc`
- end: `0x18004e9d0`
- name: `??$PEWriteResource@U_IMAGE_NT_HEADERS@@@@YAJHHKPEAU_UPDATEDATA@@PEAU_IMAGE_NT_HEADERS@@@Z`
- size: `6388`
- prototype: `__int64 __fastcall(int, int, LONG lOffset)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x18005e844`

## callees

- `0x180033330`
- `0x180039624`
- `0x1800398a4`
- `0x18003db94`
- `0x1800499e4`
- `0x18004a798`
- `0x18004d0dc`
- `0x1800592c4`
- `0x18005987c`
- `0x18005a8a0`
- `0x18005dbbc`
- `0x18008275d`
- `0x1800827a5`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004e95b`
- `ntdll!RtlFreeHeap` at `0x18004e979`
- `ntdll!RtlFreeHeap` at `0x18004e997`
- `ntdll!RtlFreeHeap` at `0x18004e95b`
- `ntdll!RtlFreeHeap` at `0x18004e979`
- `ntdll!RtlFreeHeap` at `0x18004e997`
- `ntdll!RtlAllocateHeap` at `0x18004d278`
- `ntdll!RtlAllocateHeap` at `0x18004dab6`
- `ntdll!RtlAllocateHeap` at `0x18004dd1f`
- `ntdll!RtlAllocateHeap` at `0x18004d278`
- `ntdll!RtlAllocateHeap` at `0x18004dab6`
- `ntdll!RtlAllocateHeap` at `0x18004dd1f`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004d245`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004da8e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004dcf4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004d245`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004da8e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004dcf4`

## pseudocode

```c

```
