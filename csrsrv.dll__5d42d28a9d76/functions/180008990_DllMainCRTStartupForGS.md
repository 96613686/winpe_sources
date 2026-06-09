# _DllMainCRTStartupForGS

- ea: `0x180008990`
- end: `0x1800089b7`
- name: `_DllMainCRTStartupForGS`
- size: `39`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008990`
- `0x180008b50`

## import_xrefs

- `ntdll!LdrDisableThreadCalloutsForDll` at `0x1800089a6`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x1800089a6`

## pseudocode

```c
NTSTATUS __stdcall DllMainCRTStartupForGS(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  if ( (_DWORD)RegistryPath == 1 )
  {
    _security_init_cookie();
    LdrDisableThreadCalloutsForDll(DriverObject);
  }
  return 1;
}

```

## disassembly

```asm
0x180008990  push    rbx
0x180008992  sub     rsp, 20h
0x180008996  mov     rbx, rcx
0x180008999  cmp     edx, 1
0x18000899c  jnz     short loc_1800089AC
0x18000899e  call    __security_init_cookie
0x1800089a3  mov     rcx, rbx; BaseAddress
0x1800089a6  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x1800089ac  mov     eax, 1
0x1800089b1  add     rsp, 20h
0x1800089b5  pop     rbx
0x1800089b6  retn
```
