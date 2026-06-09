# LocalAlloc

- ea: `0x180037920`
- end: `0x180037b3f`
- name: `LocalAlloc`
- size: `543`
- prototype: `HLOCAL __stdcall(UINT uFlags, SIZE_T uBytes)`
- caller_count: `64`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000669c`
- `0x180016378`
- `0x1800169c0`
- `0x180021ee0`
- `0x18002d820`
- `0x1800348e0`
- `0x180035ca0`
- `0x180035e60`
- `0x1800366c0`
- `0x180036f50`
- `0x180036ff0`
- `0x180037600`
- `0x180037c60`
- `0x180039600`
- `0x180039860`
- `0x180039ab0`
- `0x18003a030`
- `0x18003a600`
- `0x18003b420`
- `0x18003c2e0`
- `0x18003ca10`
- `0x18003d640`
- `0x18003df50`
- `0x18003e9c0`
- `0x18003f5f0`
- `0x18003f76c`
- `0x18003f9e0`
- `0x1800413d4`
- `0x180043e90`
- `0x180043fe0`
- `0x18005a1d0`
- `0x1800852b0`
- `0x1800a7950`
- `0x1800a7a00`
- `0x1800b3900`
- `0x1800b4a3c`
- `0x1800b6330`
- `0x1800b7160`
- `0x1800b74a0`
- `0x1800cc8b0`
- `0x1800e31e0`
- `0x1800e32d4`
- `0x1800e37ac`
- `0x1800e3a54`
- `0x1800e59b0`
- `0x1800eaf40`
- `0x1800eea40`
- `0x1800eeac0`
- `0x1800eec58`
- `0x1800f3f10`

## callees

- `0x180037920`
- `0x18004b9d0`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18003798e`
- `ntdll!RtlSetLastWin32Error` at `0x1800379a1`
- `ntdll!RtlSetLastWin32Error` at `0x180037a97`
- `ntdll!RtlSetLastWin32Error` at `0x180037ab4`
- `ntdll!RtlSetLastWin32Error` at `0x18003798e`
- `ntdll!RtlSetLastWin32Error` at `0x1800379a1`
- `ntdll!RtlSetLastWin32Error` at `0x180037a97`
- `ntdll!RtlSetLastWin32Error` at `0x180037ab4`
- `ntdll!RtlAllocateHandle` at `0x1800379e8`
- `ntdll!RtlAllocateHandle` at `0x1800379e8`
- `ntdll!RtlFreeHandle` at `0x180037a7e`
- `ntdll!RtlFreeHandle` at `0x180037a7e`
- `ntdll!RtlSetUserValueHeap` at `0x180037a62`
- `ntdll!RtlSetUserValueHeap` at `0x180037a62`
- `ntdll!RtlUnlockHeap` at `0x180037af3`
- `ntdll!RtlUnlockHeap` at `0x180037af3`
- `ntdll!RtlUnlockHeap` at `0x180195365`
- `ntdll!RtlLockHeap` at `0x1800379d2`
- `ntdll!RtlLockHeap` at `0x1800379d2`
- `ntdll!RtlAllocateHeap` at `0x180037963`
- `ntdll!RtlAllocateHeap` at `0x180037a35`
- `ntdll!RtlAllocateHeap` at `0x180037963`
- `ntdll!RtlAllocateHeap` at `0x180037a35`

## pseudocode

```c

```
