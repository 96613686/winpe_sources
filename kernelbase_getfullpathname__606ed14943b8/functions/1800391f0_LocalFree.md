# LocalFree

- ea: `0x1800391f0`
- end: `0x18003934f`
- name: `LocalFree`
- size: `351`
- prototype: `HLOCAL __stdcall(HLOCAL hMem)`
- caller_count: `105`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004370`
- `0x180004558`
- `0x18000669c`
- `0x180007630`
- `0x1800082a0`
- `0x18000b014`
- `0x18000bd34`
- `0x18000bf00`
- `0x18000bf5c`
- `0x18000ceb0`
- `0x18000d0fc`
- `0x1800113dc`
- `0x1800160a0`
- `0x180016378`
- `0x1800169c0`
- `0x180021ee0`
- `0x18002d820`
- `0x180032af0`
- `0x180032f90`
- `0x1800335a0`
- `0x18003366c`
- `0x180033c9c`
- `0x1800348e0`
- `0x180034e70`
- `0x180034fb0`
- `0x180035ca0`
- `0x180035e60`
- `0x1800366c0`
- `0x180036ff0`
- `0x180037600`
- `0x180037c60`
- `0x180039600`
- `0x180039860`
- `0x180039ab0`
- `0x18003a030`
- `0x18003a4f0`
- `0x18003a600`
- `0x18003a8d0`
- `0x18003ad00`
- `0x18003b420`
- `0x18003c2e0`
- `0x18003ca10`
- `0x18003d640`
- `0x18003df50`
- `0x18003e9c0`
- `0x18003ed90`
- `0x18003f65c`
- `0x18003fb50`
- `0x18003fd50`
- `0x180040974`

## callees

- `0x1800391f0`
- `0x18004b9d0`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180039239`
- `ntdll!RtlSetLastWin32Error` at `0x1800392f4`
- `ntdll!RtlSetLastWin32Error` at `0x180039307`
- `ntdll!RtlSetLastWin32Error` at `0x180039239`
- `ntdll!RtlSetLastWin32Error` at `0x1800392f4`
- `ntdll!RtlSetLastWin32Error` at `0x180039307`
- `ntdll!RtlIsValidHandle` at `0x180039288`
- `ntdll!RtlIsValidHandle` at `0x180039288`
- `ntdll!RtlFreeHandle` at `0x1800392ab`
- `ntdll!RtlFreeHandle` at `0x1800392ab`
- `ntdll!RtlUnlockHeap` at `0x18003932f`
- `ntdll!RtlUnlockHeap` at `0x18003932f`
- `ntdll!RtlUnlockHeap` at `0x1801953d5`
- `ntdll!RtlLockHeap` at `0x180039270`
- `ntdll!RtlLockHeap` at `0x180039270`
- `ntdll!RtlFreeHeap` at `0x180039219`
- `ntdll!RtlFreeHeap` at `0x1800392d6`
- `ntdll!RtlFreeHeap` at `0x180039219`
- `ntdll!RtlFreeHeap` at `0x1800392d6`

## pseudocode

```c

```
