# _DllMainCRTStartup

- ea: `0x180001f40`
- end: `0x180001f7d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001e04`
- `0x180001f40`
- `0x1800024e0`

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
0x180001f40  mov     [rsp+arg_0], rbx
0x180001f45  mov     [rsp+arg_8], rsi
0x180001f4a  push    rdi
0x180001f4b  sub     rsp, 20h
0x180001f4f  mov     rdi, r8
0x180001f52  mov     ebx, edx
0x180001f54  mov     rsi, rcx
0x180001f57  cmp     edx, 1
0x180001f5a  jnz     short loc_180001F61
0x180001f5c  call    __security_init_cookie
0x180001f61  mov     r8, rdi; lpvReserved
0x180001f64  mov     edx, ebx; fdwReason
0x180001f66  mov     rcx, rsi; hinstDLL
0x180001f69  mov     rbx, [rsp+28h+arg_0]
0x180001f6e  mov     rsi, [rsp+28h+arg_8]
0x180001f73  add     rsp, 20h
0x180001f77  pop     rdi
0x180001f78  jmp     dllmain_dispatch
```
