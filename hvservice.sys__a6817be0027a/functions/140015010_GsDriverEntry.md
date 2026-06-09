# GsDriverEntry

- ea: `0x140015010`
- end: `0x14001503c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140015044`
- `0x140015078`

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
0x140015010  mov     [rsp+arg_0], rbx
0x140015015  push    rdi
0x140015016  sub     rsp, 20h
0x14001501a  mov     rbx, rdx
0x14001501d  mov     rdi, rcx
0x140015020  call    __security_init_cookie
0x140015025  mov     rdx, rbx; RegistryPath
0x140015028  mov     rcx, rdi; DriverObject
0x14001502b  call    DriverEntry
0x140015030  mov     rbx, [rsp+28h+arg_0]
0x140015035  add     rsp, 20h
0x140015039  pop     rdi
0x14001503a  retn
```
