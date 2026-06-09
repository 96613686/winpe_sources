# GsDriverEntry

- ea: `0x14002a010`
- end: `0x14002a03c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14002a044`
- `0x14002a904`

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
0x14002a010  mov     [rsp+arg_0], rbx
0x14002a015  push    rdi
0x14002a016  sub     rsp, 20h
0x14002a01a  mov     rbx, rdx
0x14002a01d  mov     rdi, rcx
0x14002a020  call    __security_init_cookie
0x14002a025  mov     rdx, rbx; RegistryPath
0x14002a028  mov     rcx, rdi; DriverObject
0x14002a02b  call    DriverEntry
0x14002a030  mov     rbx, [rsp+28h+arg_0]
0x14002a035  add     rsp, 20h
0x14002a039  pop     rdi
0x14002a03a  retn
```
