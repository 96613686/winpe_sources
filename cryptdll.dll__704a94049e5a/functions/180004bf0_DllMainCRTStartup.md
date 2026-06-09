# _DllMainCRTStartup

- ea: `0x180004bf0`
- end: `0x180004c2d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004ab4`
- `0x180004bf0`
- `0x180004c64`

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
0x180004bf0  mov     [rsp+arg_0], rbx
0x180004bf5  mov     [rsp+arg_8], rsi
0x180004bfa  push    rdi
0x180004bfb  sub     rsp, 20h
0x180004bff  mov     rdi, r8
0x180004c02  mov     ebx, edx
0x180004c04  mov     rsi, rcx
0x180004c07  cmp     edx, 1
0x180004c0a  jnz     short loc_180004C11
0x180004c0c  call    __security_init_cookie
0x180004c11  mov     r8, rdi; lpvReserved
0x180004c14  mov     edx, ebx; fdwReason
0x180004c16  mov     rcx, rsi; hinstDLL
0x180004c19  mov     rbx, [rsp+28h+arg_0]
0x180004c1e  mov     rsi, [rsp+28h+arg_8]
0x180004c23  add     rsp, 20h
0x180004c27  pop     rdi
0x180004c28  jmp     dllmain_dispatch
```
