# PEWriteResource<_IMAGE_NT_HEADERS64>(int,int,ulong,_UPDATEDATA *,_IMAGE_NT_HEADERS64 *)

- ea: `0x180047324`
- end: `0x180048b62`
- name: `??$PEWriteResource@U_IMAGE_NT_HEADERS64@@@@YAJHHKPEAU_UPDATEDATA@@PEAU_IMAGE_NT_HEADERS64@@@Z`
- size: `6206`
- prototype: `__int64 __fastcall(int, int, LONG lOffset)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x180059128`

## callees

- `0x1800313d0`
- `0x1800373e8`
- `0x180045240`
- `0x18004566c`
- `0x180045ff4`
- `0x180047324`
- `0x1800548c8`
- `0x180054f0c`
- `0x180056048`
- `0x1800588f0`
- `0x180059f88`
- `0x18007a7dd`
- `0x18007a825`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180048b00`
- `ntdll!RtlFreeHeap` at `0x180048b18`
- `ntdll!RtlFreeHeap` at `0x180048b30`
- `ntdll!RtlFreeHeap` at `0x180048b00`
- `ntdll!RtlFreeHeap` at `0x180048b18`
- `ntdll!RtlFreeHeap` at `0x180048b30`
- `ntdll!RtlAllocateHeap` at `0x180047455`
- `ntdll!RtlAllocateHeap` at `0x180047c80`
- `ntdll!RtlAllocateHeap` at `0x180047edd`
- `ntdll!RtlAllocateHeap` at `0x180047455`
- `ntdll!RtlAllocateHeap` at `0x180047c80`
- `ntdll!RtlAllocateHeap` at `0x180047edd`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180047428`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180047c5e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180047eb8`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180047428`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180047c5e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180047eb8`

## pseudocode

```c

```
