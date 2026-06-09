# _DllMainCRTStartup

- ea: `0x180002440`
- end: `0x18000247d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002304`
- `0x180002440`
- `0x180002d34`

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
0x180002440  mov     [rsp+arg_0], rbx
0x180002445  mov     [rsp+arg_8], rsi
0x18000244a  push    rdi
0x18000244b  sub     rsp, 20h
0x18000244f  mov     rdi, r8
0x180002452  mov     ebx, edx
0x180002454  mov     rsi, rcx
0x180002457  cmp     edx, 1
0x18000245a  jnz     short loc_180002461
0x18000245c  call    __security_init_cookie
0x180002461  mov     r8, rdi; lpvReserved
0x180002464  mov     edx, ebx; fdwReason
0x180002466  mov     rcx, rsi; hinstDLL
0x180002469  mov     rbx, [rsp+28h+arg_0]
0x18000246e  mov     rsi, [rsp+28h+arg_8]
0x180002473  add     rsp, 20h
0x180002477  pop     rdi
0x180002478  jmp     dllmain_dispatch
```
