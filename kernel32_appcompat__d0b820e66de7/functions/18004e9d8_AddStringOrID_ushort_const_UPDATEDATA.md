# AddStringOrID(ushort const *,_UPDATEDATA *)

- ea: `0x18004e9d8`
- end: `0x18004eba7`
- name: `?AddStringOrID@@YAPEAUMY_STRING@@PEBGPEAU_UPDATEDATA@@@Z`
- size: `463`
- prototype: `struct MY_STRING *__fastcall(wchar_t *String2, struct _UPDATEDATA *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18005c660`
- `0x18006a1c0`

## callees

- `0x18004e9d8`
- `0x180082799`

## import_xrefs

- `ntdll!wcslen` at `0x18004ea52`
- `ntdll!wcslen` at `0x18004ea52`
- `ntdll!RtlFreeHeap` at `0x18004eb2c`
- `ntdll!RtlFreeHeap` at `0x18004eb2c`
- `ntdll!RtlAllocateHeap` at `0x18004ea21`
- `ntdll!RtlAllocateHeap` at `0x18004eab8`
- `ntdll!RtlAllocateHeap` at `0x18004eb05`
- `ntdll!RtlAllocateHeap` at `0x18004ea21`
- `ntdll!RtlAllocateHeap` at `0x18004eab8`
- `ntdll!RtlAllocateHeap` at `0x18004eb05`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004e9f7`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004ea8d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004eadd`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004e9f7`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004ea8d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004eadd`

## pseudocode

```c

```
