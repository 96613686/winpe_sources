# GetSystemWindowsDirectoryA

- ea: `0x18004320c`
- end: `0x1800432a6`
- name: `GetSystemWindowsDirectoryA`
- size: `154`
- prototype: `UINT __stdcall(LPSTR lpBuffer, UINT uSize)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180043200`

## callees

- `0x18004320c`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlUnicodeToMultiByteSize` at `0x18004324c`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18004324c`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004322f`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180043238`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180043269`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004322f`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180043238`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180043269`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180043273`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180043273`

## pseudocode

```c

```
