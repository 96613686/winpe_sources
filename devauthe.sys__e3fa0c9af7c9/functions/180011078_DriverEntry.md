# DriverEntry

- ea: `0x180011078`
- end: `0x18001107b`
- name: `DriverEntry`
- size: `3`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180011010`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  return 0;
}

```

## disassembly

```asm
0x180011078  xor     eax, eax
0x18001107a  retn
```
