# _DllMainCRTStartup

- ea: `0x180002290`
- end: `0x1800022cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002154`
- `0x180002290`
- `0x1800026ec`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180002290  mov     [rsp+arg_0], rbx
0x180002295  mov     [rsp+arg_8], rsi
0x18000229a  push    rdi
0x18000229b  sub     rsp, 20h
0x18000229f  mov     rdi, r8
0x1800022a2  mov     ebx, edx
0x1800022a4  mov     rsi, rcx
0x1800022a7  cmp     edx, 1
0x1800022aa  jnz     short loc_1800022B1
0x1800022ac  call    __security_init_cookie
0x1800022b1  mov     r8, rdi; lpvReserved
0x1800022b4  mov     edx, ebx; fdwReason
0x1800022b6  mov     rcx, rsi; hinstDLL
0x1800022b9  mov     rbx, [rsp+28h+arg_0]
0x1800022be  mov     rsi, [rsp+28h+arg_8]
0x1800022c3  add     rsp, 20h
0x1800022c7  pop     rdi
0x1800022c8  jmp     dllmain_dispatch
```
