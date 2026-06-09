# GsDriverEntry

- ea: `0x14001b010`
- end: `0x14001b03c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14001b044`
- `0x14001b078`

## pseudocode

```c
NTSTATUS __stdcall GsDriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  _security_init_cookie();
  return DriverEntry(DriverObject, RegistryPath);
}

```

## disassembly

```asm
0x14001b010  mov     [rsp+arg_0], rbx
0x14001b015  push    rdi
0x14001b016  sub     rsp, 20h
0x14001b01a  mov     rbx, rdx
0x14001b01d  mov     rdi, rcx
0x14001b020  call    __security_init_cookie
0x14001b025  mov     rdx, rbx; RegistryPath
0x14001b028  mov     rcx, rdi; DriverObject
0x14001b02b  call    DriverEntry
0x14001b030  mov     rbx, [rsp+28h+arg_0]
0x14001b035  add     rsp, 20h
0x14001b039  pop     rdi
0x14001b03a  retn
```
