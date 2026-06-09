# GetSystemWindowsDirectoryA

- ea: `0x18004759c`
- end: `0x180047655`
- name: `GetSystemWindowsDirectoryA`
- size: `185`
- prototype: `UINT __stdcall(LPSTR lpBuffer, UINT uSize)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180047590`

## callees

- `0x18004759c`
- `0x180084010`

## import_xrefs

- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800475e8`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800475e8`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800475bf`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800475ce`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004760b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800475bf`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800475ce`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004760b`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18004761b`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18004761b`

## pseudocode

```c

```
