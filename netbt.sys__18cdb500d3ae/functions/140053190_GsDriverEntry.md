# GsDriverEntry

- ea: `0x140053190`
- end: `0x1400531bc`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400531c4`
- `0x140053828`

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
0x140053190  mov     [rsp+arg_0], rbx
0x140053195  push    rdi
0x140053196  sub     rsp, 20h
0x14005319a  mov     rbx, rdx
0x14005319d  mov     rdi, rcx
0x1400531a0  call    __security_init_cookie
0x1400531a5  mov     rdx, rbx; RegistryPath
0x1400531a8  mov     rcx, rdi; DriverObject
0x1400531ab  call    DriverEntry
0x1400531b0  mov     rbx, [rsp+28h+arg_0]
0x1400531b5  add     rsp, 20h
0x1400531b9  pop     rdi
0x1400531ba  retn
```
