# GsDriverEntry

- ea: `0x140037010`
- end: `0x14003703c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140037044`
- `0x140037080`

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
0x140037010  mov     [rsp+arg_0], rbx
0x140037015  push    rdi
0x140037016  sub     rsp, 20h
0x14003701a  mov     rbx, rdx
0x14003701d  mov     rdi, rcx
0x140037020  call    __security_init_cookie
0x140037025  mov     rdx, rbx; RegistryPath
0x140037028  mov     rcx, rdi; DriverObject
0x14003702b  call    DriverEntry
0x140037030  mov     rbx, [rsp+28h+arg_0]
0x140037035  add     rsp, 20h
0x140037039  pop     rdi
0x14003703a  retn
```
