# _DllMainCRTStartup

- ea: `0x180003160`
- end: `0x18000319d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003024`
- `0x180003160`
- `0x180003a1c`

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
0x180003160  mov     [rsp+arg_0], rbx
0x180003165  mov     [rsp+arg_8], rsi
0x18000316a  push    rdi
0x18000316b  sub     rsp, 20h
0x18000316f  mov     rdi, r8
0x180003172  mov     ebx, edx
0x180003174  mov     rsi, rcx
0x180003177  cmp     edx, 1
0x18000317a  jnz     short loc_180003181
0x18000317c  call    __security_init_cookie
0x180003181  mov     r8, rdi; lpvReserved
0x180003184  mov     edx, ebx; fdwReason
0x180003186  mov     rcx, rsi; hinstDLL
0x180003189  mov     rbx, [rsp+28h+arg_0]
0x18000318e  mov     rsi, [rsp+28h+arg_8]
0x180003193  add     rsp, 20h
0x180003197  pop     rdi
0x180003198  jmp     dllmain_dispatch
```
