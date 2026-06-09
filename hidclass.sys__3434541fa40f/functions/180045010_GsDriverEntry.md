# GsDriverEntry

- ea: `0x180045010`
- end: `0x18004503c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800385e0`
- `0x180045044`

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
0x180045010  mov     [rsp+arg_0], rbx
0x180045015  push    rdi
0x180045016  sub     rsp, 20h
0x18004501a  mov     rbx, rdx
0x18004501d  mov     rdi, rcx
0x180045020  call    __security_init_cookie
0x180045025  mov     rdx, rbx; RegistryPath
0x180045028  mov     rcx, rdi; DriverObject
0x18004502b  call    DriverEntry
0x180045030  mov     rbx, [rsp+28h+arg_0]
0x180045035  add     rsp, 20h
0x180045039  pop     rdi
0x18004503a  retn
```
