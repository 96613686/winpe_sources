# AddStringOrID(ushort const *,_UPDATEDATA *)

- ea: `0x18004a42c`
- end: `0x18004a5ca`
- name: `?AddStringOrID@@YAPEAUMY_STRING@@PEBGPEAU_UPDATEDATA@@@Z`
- size: `414`
- prototype: `struct MY_STRING *__fastcall(wchar_t *String2, struct _UPDATEDATA *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180057210`
- `0x180063630`

## callees

- `0x18004a42c`
- `0x18007a819`

## import_xrefs

- `ntdll!wcslen` at `0x18004a49a`
- `ntdll!wcslen` at `0x18004a49a`
- `ntdll!RtlFreeHeap` at `0x18004a556`
- `ntdll!RtlFreeHeap` at `0x18004a556`
- `ntdll!RtlAllocateHeap` at `0x18004a46f`
- `ntdll!RtlAllocateHeap` at `0x18004a4f4`
- `ntdll!RtlAllocateHeap` at `0x18004a535`
- `ntdll!RtlAllocateHeap` at `0x18004a46f`
- `ntdll!RtlAllocateHeap` at `0x18004a4f4`
- `ntdll!RtlAllocateHeap` at `0x18004a535`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004a44b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004a4cf`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004a513`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004a44b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004a4cf`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004a513`

## pseudocode

```c

```
