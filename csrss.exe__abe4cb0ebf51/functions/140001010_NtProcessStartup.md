# NtProcessStartup

- ea: `0x140001010`
- end: `0x140001027`
- name: `NtProcessStartup`
- size: `23`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001030`
- `0x1400015b0`

## pseudocode

```c
NTSTATUS __stdcall __noreturn NtProcessStartup(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  _security_init_cookie();
  NtProcessStartup_AfterSecurityCookieInitialized((__int64)DriverObject);
  JUMPOUT(0x140001026LL);
}

```

## disassembly

```asm
0x140001010  push    rbx
0x140001012  sub     rsp, 20h
0x140001016  mov     rbx, rcx
0x140001019  call    __security_init_cookie
0x14000101e  mov     rcx, rbx
0x140001021  call    NtProcessStartup_AfterSecurityCookieInitialized
```
