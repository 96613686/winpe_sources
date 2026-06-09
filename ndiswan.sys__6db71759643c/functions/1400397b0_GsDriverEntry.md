# GsDriverEntry

- ea: `0x1400397b0`
- end: `0x1400397dc`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140039008`
- `0x1400397e4`

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
0x1400397b0  mov     [rsp+arg_0], rbx
0x1400397b5  push    rdi
0x1400397b6  sub     rsp, 20h
0x1400397ba  mov     rbx, rdx
0x1400397bd  mov     rdi, rcx
0x1400397c0  call    __security_init_cookie
0x1400397c5  mov     rdx, rbx; RegistryPath
0x1400397c8  mov     rcx, rdi; DriverObject
0x1400397cb  call    DriverEntry
0x1400397d0  mov     rbx, [rsp+28h+arg_0]
0x1400397d5  add     rsp, 20h
0x1400397d9  pop     rdi
0x1400397da  retn
```
