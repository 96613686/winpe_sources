# PEWriteResource<_IMAGE_NT_HEADERS>(int,int,ulong,_UPDATEDATA *,_IMAGE_NT_HEADERS *)

- ea: `0x180048b68`
- end: `0x18004a425`
- name: `??$PEWriteResource@U_IMAGE_NT_HEADERS@@@@YAJHHKPEAU_UPDATEDATA@@PEAU_IMAGE_NT_HEADERS@@@Z`
- size: `6333`
- prototype: `__int64 __fastcall(int, int, LONG lOffset)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x180059128`

## callees

- `0x1800313d0`
- `0x180037188`
- `0x1800373e8`
- `0x18003aa60`
- `0x180045240`
- `0x180045ff4`
- `0x180048b68`
- `0x1800548c8`
- `0x180054f0c`
- `0x180056048`
- `0x180059f88`
- `0x18007a7dd`
- `0x18007a825`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004a3c3`
- `ntdll!RtlFreeHeap` at `0x18004a3db`
- `ntdll!RtlFreeHeap` at `0x18004a3f3`
- `ntdll!RtlFreeHeap` at `0x18004a3c3`
- `ntdll!RtlFreeHeap` at `0x18004a3db`
- `ntdll!RtlFreeHeap` at `0x18004a3f3`
- `ntdll!RtlAllocateHeap` at `0x180048cfe`
- `ntdll!RtlAllocateHeap` at `0x180049530`
- `ntdll!RtlAllocateHeap` at `0x18004978d`
- `ntdll!RtlAllocateHeap` at `0x180048cfe`
- `ntdll!RtlAllocateHeap` at `0x180049530`
- `ntdll!RtlAllocateHeap` at `0x18004978d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180048cd1`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004950e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180049768`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180048cd1`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004950e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180049768`

## pseudocode

```c

```
