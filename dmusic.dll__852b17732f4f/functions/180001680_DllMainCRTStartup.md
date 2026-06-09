# _DllMainCRTStartup

- ea: `0x180001680`
- end: `0x1800016bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001544`
- `0x180001680`
- `0x180001c40`

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
0x180001680  mov     [rsp+arg_0], rbx
0x180001685  mov     [rsp+arg_8], rsi
0x18000168a  push    rdi
0x18000168b  sub     rsp, 20h
0x18000168f  mov     rdi, r8
0x180001692  mov     ebx, edx
0x180001694  mov     rsi, rcx
0x180001697  cmp     edx, 1
0x18000169a  jnz     short loc_1800016A1
0x18000169c  call    __security_init_cookie
0x1800016a1  mov     r8, rdi; lpvReserved
0x1800016a4  mov     edx, ebx; fdwReason
0x1800016a6  mov     rcx, rsi; hinstDLL
0x1800016a9  mov     rbx, [rsp+28h+arg_0]
0x1800016ae  mov     rsi, [rsp+28h+arg_8]
0x1800016b3  add     rsp, 20h
0x1800016b7  pop     rdi
0x1800016b8  jmp     dllmain_dispatch
```
