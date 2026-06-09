# _DllMainCRTStartup

- ea: `0x1800014c0`
- end: `0x1800014fd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001384`
- `0x1800014c0`
- `0x180001d4c`

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
0x1800014c0  mov     [rsp+arg_0], rbx
0x1800014c5  mov     [rsp+arg_8], rsi
0x1800014ca  push    rdi
0x1800014cb  sub     rsp, 20h
0x1800014cf  mov     rdi, r8
0x1800014d2  mov     ebx, edx
0x1800014d4  mov     rsi, rcx
0x1800014d7  cmp     edx, 1
0x1800014da  jnz     short loc_1800014E1
0x1800014dc  call    __security_init_cookie
0x1800014e1  mov     r8, rdi; lpvReserved
0x1800014e4  mov     edx, ebx; fdwReason
0x1800014e6  mov     rcx, rsi; hinstDLL
0x1800014e9  mov     rbx, [rsp+28h+arg_0]
0x1800014ee  mov     rsi, [rsp+28h+arg_8]
0x1800014f3  add     rsp, 20h
0x1800014f7  pop     rdi
0x1800014f8  jmp     dllmain_dispatch
```
