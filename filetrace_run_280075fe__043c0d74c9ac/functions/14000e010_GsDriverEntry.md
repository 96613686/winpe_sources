# GsDriverEntry

- ea: `0x14000e010`
- end: `0x14000e03c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000e044`
- `0x14000e078`

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
0x14000e010  mov     [rsp+arg_0], rbx
0x14000e015  push    rdi
0x14000e016  sub     rsp, 20h
0x14000e01a  mov     rbx, rdx
0x14000e01d  mov     rdi, rcx
0x14000e020  call    __security_init_cookie
0x14000e025  mov     rdx, rbx; RegistryPath
0x14000e028  mov     rcx, rdi; DriverObject
0x14000e02b  call    DriverEntry
0x14000e030  mov     rbx, [rsp+28h+arg_0]
0x14000e035  add     rsp, 20h
0x14000e039  pop     rdi
0x14000e03a  retn
```
