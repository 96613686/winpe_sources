# _Kernel32LegacyLib_BaseDllInitialize

- ea: `0x180038514`
- end: `0x180038670`
- name: `_Kernel32LegacyLib_BaseDllInitialize`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800389dc`

## callees

- `0x18000ccf0`
- `0x18000d700`
- `0x180038514`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180038650`
- `ntdll!RtlSetLastWin32Error` at `0x180038650`
- `ntdll!NtQuerySystemInformation` at `0x1800385e2`
- `ntdll!NtQuerySystemInformation` at `0x1800385e2`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003852d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003857b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800385fb`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003852d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003857b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800385fb`

## pseudocode

```c

```
