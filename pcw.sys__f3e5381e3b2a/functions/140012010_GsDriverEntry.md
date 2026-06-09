# GsDriverEntry

- ea: `0x140012010`
- end: `0x14001203c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140012044`
- `0x140012200`

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
0x140012010  mov     [rsp+arg_0], rbx
0x140012015  push    rdi
0x140012016  sub     rsp, 20h
0x14001201a  mov     rbx, rdx
0x14001201d  mov     rdi, rcx
0x140012020  call    __security_init_cookie
0x140012025  mov     rdx, rbx; RegistryPath
0x140012028  mov     rcx, rdi; DriverObject
0x14001202b  call    DriverEntry
0x140012030  mov     rbx, [rsp+28h+arg_0]
0x140012035  add     rsp, 20h
0x140012039  pop     rdi
0x14001203a  retn
```
