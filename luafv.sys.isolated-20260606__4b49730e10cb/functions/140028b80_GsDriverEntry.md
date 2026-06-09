# GsDriverEntry

- ea: `0x140028b80`
- end: `0x140028bac`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140028bb4`
- `0x1400291a8`

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
0x140028b80  mov     [rsp+arg_0], rbx
0x140028b85  push    rdi
0x140028b86  sub     rsp, 20h
0x140028b8a  mov     rbx, rdx
0x140028b8d  mov     rdi, rcx
0x140028b90  call    __security_init_cookie
0x140028b95  mov     rdx, rbx; RegistryPath
0x140028b98  mov     rcx, rdi; DriverObject
0x140028b9b  call    DriverEntry
0x140028ba0  mov     rbx, [rsp+28h+arg_0]
0x140028ba5  add     rsp, 20h
0x140028ba9  pop     rdi
0x140028baa  retn
```
