# _DllMainCRTStartup

- ea: `0x18000f9c0`
- end: `0x18000f9fd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000f884`
- `0x18000f9c0`
- `0x18000fe1c`

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
0x18000f9c0  mov     [rsp+arg_0], rbx
0x18000f9c5  mov     [rsp+arg_8], rsi
0x18000f9ca  push    rdi
0x18000f9cb  sub     rsp, 20h
0x18000f9cf  mov     rdi, r8
0x18000f9d2  mov     ebx, edx
0x18000f9d4  mov     rsi, rcx
0x18000f9d7  cmp     edx, 1
0x18000f9da  jnz     short loc_18000F9E1
0x18000f9dc  call    __security_init_cookie
0x18000f9e1  mov     r8, rdi; lpvReserved
0x18000f9e4  mov     edx, ebx; fdwReason
0x18000f9e6  mov     rcx, rsi; hinstDLL
0x18000f9e9  mov     rbx, [rsp+28h+arg_0]
0x18000f9ee  mov     rsi, [rsp+28h+arg_8]
0x18000f9f3  add     rsp, 20h
0x18000f9f7  pop     rdi
0x18000f9f8  jmp     dllmain_dispatch
```
