# GsDriverEntry

- ea: `0x140047010`
- end: `0x14004703c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14002246c`
- `0x140047044`

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
0x140047010  mov     [rsp+arg_0], rbx
0x140047015  push    rdi
0x140047016  sub     rsp, 20h
0x14004701a  mov     rbx, rdx
0x14004701d  mov     rdi, rcx
0x140047020  call    __security_init_cookie
0x140047025  mov     rdx, rbx; RegistryPath
0x140047028  mov     rcx, rdi; DriverObject
0x14004702b  call    DriverEntry
0x140047030  mov     rbx, [rsp+28h+arg_0]
0x140047035  add     rsp, 20h
0x140047039  pop     rdi
0x14004703a  retn
```
