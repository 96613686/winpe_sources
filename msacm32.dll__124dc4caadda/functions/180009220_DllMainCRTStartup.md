# _DllMainCRTStartup

- ea: `0x180009220`
- end: `0x18000925d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800090e4`
- `0x180009220`
- `0x1800092b0`

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
0x180009220  mov     [rsp+arg_0], rbx
0x180009225  mov     [rsp+arg_8], rsi
0x18000922a  push    rdi
0x18000922b  sub     rsp, 20h
0x18000922f  mov     rdi, r8
0x180009232  mov     ebx, edx
0x180009234  mov     rsi, rcx
0x180009237  cmp     edx, 1
0x18000923a  jnz     short loc_180009241
0x18000923c  call    __security_init_cookie
0x180009241  mov     r8, rdi; lpvReserved
0x180009244  mov     edx, ebx; fdwReason
0x180009246  mov     rcx, rsi; hinstDLL
0x180009249  mov     rbx, [rsp+28h+arg_0]
0x18000924e  mov     rsi, [rsp+28h+arg_8]
0x180009253  add     rsp, 20h
0x180009257  pop     rdi
0x180009258  jmp     dllmain_dispatch
```
