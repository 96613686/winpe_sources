# _DllMainCRTStartup

- ea: `0x1800020b0`
- end: `0x1800020ed`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001f74`
- `0x1800020b0`
- `0x18000250c`

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
0x1800020b0  mov     [rsp+arg_0], rbx
0x1800020b5  mov     [rsp+arg_8], rsi
0x1800020ba  push    rdi
0x1800020bb  sub     rsp, 20h
0x1800020bf  mov     rdi, r8
0x1800020c2  mov     ebx, edx
0x1800020c4  mov     rsi, rcx
0x1800020c7  cmp     edx, 1
0x1800020ca  jnz     short loc_1800020D1
0x1800020cc  call    __security_init_cookie
0x1800020d1  mov     r8, rdi; lpvReserved
0x1800020d4  mov     edx, ebx; fdwReason
0x1800020d6  mov     rcx, rsi; hinstDLL
0x1800020d9  mov     rbx, [rsp+28h+arg_0]
0x1800020de  mov     rsi, [rsp+28h+arg_8]
0x1800020e3  add     rsp, 20h
0x1800020e7  pop     rdi
0x1800020e8  jmp     dllmain_dispatch
```
