# _DllMainCRTStartup

- ea: `0x180002e00`
- end: `0x180002e3d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002cc4`
- `0x180002e00`
- `0x1800035f4`

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
0x180002e00  mov     [rsp+arg_0], rbx
0x180002e05  mov     [rsp+arg_8], rsi
0x180002e0a  push    rdi
0x180002e0b  sub     rsp, 20h
0x180002e0f  mov     rdi, r8
0x180002e12  mov     ebx, edx
0x180002e14  mov     rsi, rcx
0x180002e17  cmp     edx, 1
0x180002e1a  jnz     short loc_180002E21
0x180002e1c  call    __security_init_cookie
0x180002e21  mov     r8, rdi; lpvReserved
0x180002e24  mov     edx, ebx; fdwReason
0x180002e26  mov     rcx, rsi; hinstDLL
0x180002e29  mov     rbx, [rsp+28h+arg_0]
0x180002e2e  mov     rsi, [rsp+28h+arg_8]
0x180002e33  add     rsp, 20h
0x180002e37  pop     rdi
0x180002e38  jmp     dllmain_dispatch
```
