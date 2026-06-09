# GsDriverEntry

- ea: `0x140011100`
- end: `0x14001112c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140011134`
- `0x140011168`

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
0x140011100  mov     [rsp+arg_0], rbx
0x140011105  push    rdi
0x140011106  sub     rsp, 20h
0x14001110a  mov     rbx, rdx
0x14001110d  mov     rdi, rcx
0x140011110  call    __security_init_cookie
0x140011115  mov     rdx, rbx; RegistryPath
0x140011118  mov     rcx, rdi; DriverObject
0x14001111b  call    DriverEntry
0x140011120  mov     rbx, [rsp+28h+arg_0]
0x140011125  add     rsp, 20h
0x140011129  pop     rdi
0x14001112a  retn
```
