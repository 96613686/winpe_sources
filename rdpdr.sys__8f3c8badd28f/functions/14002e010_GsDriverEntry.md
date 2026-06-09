# GsDriverEntry

- ea: `0x14002e010`
- end: `0x14002e03c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14002e044`
- `0x14002e078`

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
0x14002e010  mov     [rsp+arg_0], rbx
0x14002e015  push    rdi
0x14002e016  sub     rsp, 20h
0x14002e01a  mov     rbx, rdx
0x14002e01d  mov     rdi, rcx
0x14002e020  call    __security_init_cookie
0x14002e025  mov     rdx, rbx; RegistryPath
0x14002e028  mov     rcx, rdi; DriverObject
0x14002e02b  call    DriverEntry
0x14002e030  mov     rbx, [rsp+28h+arg_0]
0x14002e035  add     rsp, 20h
0x14002e039  pop     rdi
0x14002e03a  retn
```
