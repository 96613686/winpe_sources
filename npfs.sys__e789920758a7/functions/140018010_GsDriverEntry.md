# GsDriverEntry

- ea: `0x140018010`
- end: `0x14001803c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140018044`
- `0x140018080`

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
0x140018010  mov     [rsp+arg_0], rbx
0x140018015  push    rdi
0x140018016  sub     rsp, 20h
0x14001801a  mov     rbx, rdx
0x14001801d  mov     rdi, rcx
0x140018020  call    __security_init_cookie
0x140018025  mov     rdx, rbx; RegistryPath
0x140018028  mov     rcx, rdi; DriverObject
0x14001802b  call    DriverEntry
0x140018030  mov     rbx, [rsp+28h+arg_0]
0x140018035  add     rsp, 20h
0x140018039  pop     rdi
0x14001803a  retn
```
