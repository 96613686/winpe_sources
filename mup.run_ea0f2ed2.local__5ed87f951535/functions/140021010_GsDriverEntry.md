# GsDriverEntry

- ea: `0x140021010`
- end: `0x14002103c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140010f18`
- `0x140021044`

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
0x140021010  mov     [rsp+arg_0], rbx
0x140021015  push    rdi
0x140021016  sub     rsp, 20h
0x14002101a  mov     rbx, rdx
0x14002101d  mov     rdi, rcx
0x140021020  call    __security_init_cookie
0x140021025  mov     rdx, rbx; RegistryPath
0x140021028  mov     rcx, rdi; DriverObject
0x14002102b  call    DriverEntry
0x140021030  mov     rbx, [rsp+28h+arg_0]
0x140021035  add     rsp, 20h
0x140021039  pop     rdi
0x14002103a  retn
```
