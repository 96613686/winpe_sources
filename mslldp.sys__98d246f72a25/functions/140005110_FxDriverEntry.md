# FxDriverEntry

- ea: `0x140005110`
- end: `0x14000513c`
- name: `FxDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005144`
- `0x14001331c`

## pseudocode

```c
NTSTATUS __stdcall FxDriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  _security_init_cookie();
  return FxDriverEntryWorker(DriverObject, RegistryPath);
}

```

## disassembly

```asm
0x140005110  mov     [rsp+arg_0], rbx
0x140005115  push    rdi
0x140005116  sub     rsp, 20h
0x14000511a  mov     rbx, rdx
0x14000511d  mov     rdi, rcx
0x140005120  call    __security_init_cookie
0x140005125  mov     rdx, rbx; RegistryPath
0x140005128  mov     rcx, rdi; DriverObject
0x14000512b  call    FxDriverEntryWorker
0x140005130  mov     rbx, [rsp+28h+arg_0]
0x140005135  add     rsp, 20h
0x140005139  pop     rdi
0x14000513a  retn
```
