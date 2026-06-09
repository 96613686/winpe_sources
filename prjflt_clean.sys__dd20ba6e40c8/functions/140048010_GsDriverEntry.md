# GsDriverEntry

- ea: `0x140048010`
- end: `0x14004803c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140048044`
- `0x1400484e0`

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
0x140048010  mov     [rsp+arg_0], rbx
0x140048015  push    rdi
0x140048016  sub     rsp, 20h
0x14004801a  mov     rbx, rdx
0x14004801d  mov     rdi, rcx
0x140048020  call    __security_init_cookie
0x140048025  mov     rdx, rbx; RegistryPath
0x140048028  mov     rcx, rdi; DriverObject
0x14004802b  call    DriverEntry
0x140048030  mov     rbx, [rsp+28h+arg_0]
0x140048035  add     rsp, 20h
0x140048039  pop     rdi
0x14004803a  retn
```
