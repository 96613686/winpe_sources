# GsDriverEntry

- ea: `0x1400145e0`
- end: `0x14001460c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140014300`
- `0x140014614`

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
0x1400145e0  mov     [rsp+arg_0], rbx
0x1400145e5  push    rdi
0x1400145e6  sub     rsp, 20h
0x1400145ea  mov     rbx, rdx
0x1400145ed  mov     rdi, rcx
0x1400145f0  call    __security_init_cookie
0x1400145f5  mov     rdx, rbx; RegistryPath
0x1400145f8  mov     rcx, rdi; DriverObject
0x1400145fb  call    DriverEntry
0x140014600  mov     rbx, [rsp+28h+arg_0]
0x140014605  add     rsp, 20h
0x140014609  pop     rdi
0x14001460a  retn
```
