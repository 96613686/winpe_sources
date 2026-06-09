# GsDriverEntry

- ea: `0x140030010`
- end: `0x14003003c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14001143c`
- `0x140030044`

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
0x140030010  mov     [rsp+arg_0], rbx
0x140030015  push    rdi
0x140030016  sub     rsp, 20h
0x14003001a  mov     rbx, rdx
0x14003001d  mov     rdi, rcx
0x140030020  call    __security_init_cookie
0x140030025  mov     rdx, rbx; RegistryPath
0x140030028  mov     rcx, rdi; DriverObject
0x14003002b  call    DriverEntry
0x140030030  mov     rbx, [rsp+28h+arg_0]
0x140030035  add     rsp, 20h
0x140030039  pop     rdi
0x14003003a  retn
```
