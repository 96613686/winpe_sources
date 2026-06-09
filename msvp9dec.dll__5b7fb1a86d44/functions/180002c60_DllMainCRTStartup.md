# _DllMainCRTStartup

- ea: `0x180002c60`
- end: `0x180002c9d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002b24`
- `0x180002c60`
- `0x1800030b0`

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
0x180002c60  mov     [rsp+arg_0], rbx
0x180002c65  mov     [rsp+arg_8], rsi
0x180002c6a  push    rdi
0x180002c6b  sub     rsp, 20h
0x180002c6f  mov     rdi, r8
0x180002c72  mov     ebx, edx
0x180002c74  mov     rsi, rcx
0x180002c77  cmp     edx, 1
0x180002c7a  jnz     short loc_180002C81
0x180002c7c  call    __security_init_cookie
0x180002c81  mov     r8, rdi; lpvReserved
0x180002c84  mov     edx, ebx; fdwReason
0x180002c86  mov     rcx, rsi; hinstDLL
0x180002c89  mov     rbx, [rsp+28h+arg_0]
0x180002c8e  mov     rsi, [rsp+28h+arg_8]
0x180002c93  add     rsp, 20h
0x180002c97  pop     rdi
0x180002c98  jmp     dllmain_dispatch
```
