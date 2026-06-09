# GsDriverEntry

- ea: `0x140045010`
- end: `0x14004503c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140045044`
- `0x140045078`

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
0x140045010  mov     [rsp+arg_0], rbx
0x140045015  push    rdi
0x140045016  sub     rsp, 20h
0x14004501a  mov     rbx, rdx
0x14004501d  mov     rdi, rcx
0x140045020  call    __security_init_cookie
0x140045025  mov     rdx, rbx; RegistryPath
0x140045028  mov     rcx, rdi; DriverObject
0x14004502b  call    DriverEntry
0x140045030  mov     rbx, [rsp+28h+arg_0]
0x140045035  add     rsp, 20h
0x140045039  pop     rdi
0x14004503a  retn
```
