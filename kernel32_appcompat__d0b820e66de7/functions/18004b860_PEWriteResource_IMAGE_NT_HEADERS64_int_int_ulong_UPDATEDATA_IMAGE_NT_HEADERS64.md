# PEWriteResource<_IMAGE_NT_HEADERS64>(int,int,ulong,_UPDATEDATA *,_IMAGE_NT_HEADERS64 *)

- ea: `0x18004b860`
- end: `0x18004d0d5`
- name: `??$PEWriteResource@U_IMAGE_NT_HEADERS64@@@@YAJHHKPEAU_UPDATEDATA@@PEAU_IMAGE_NT_HEADERS64@@@Z`
- size: `6261`
- prototype: `__int64 __fastcall(int, int, LONG lOffset)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x18005e844`

## callees

- `0x180033330`
- `0x1800398a4`
- `0x1800499e4`
- `0x180049e24`
- `0x18004a798`
- `0x18004b860`
- `0x1800592c4`
- `0x18005987c`
- `0x18005a8a0`
- `0x18005dbbc`
- `0x18005df58`
- `0x18008275d`
- `0x1800827a5`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004d060`
- `ntdll!RtlFreeHeap` at `0x18004d07e`
- `ntdll!RtlFreeHeap` at `0x18004d09c`
- `ntdll!RtlFreeHeap` at `0x18004d060`
- `ntdll!RtlFreeHeap` at `0x18004d07e`
- `ntdll!RtlFreeHeap` at `0x18004d09c`
- `ntdll!RtlAllocateHeap` at `0x18004b997`
- `ntdll!RtlAllocateHeap` at `0x18004c1ce`
- `ntdll!RtlAllocateHeap` at `0x18004c437`
- `ntdll!RtlAllocateHeap` at `0x18004b997`
- `ntdll!RtlAllocateHeap` at `0x18004c1ce`
- `ntdll!RtlAllocateHeap` at `0x18004c437`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004b964`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004c1a6`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004c40c`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004b964`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004c1a6`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004c40c`

## pseudocode

```c

```
