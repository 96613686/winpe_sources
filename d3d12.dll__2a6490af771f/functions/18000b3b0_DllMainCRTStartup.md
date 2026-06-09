# _DllMainCRTStartup

- ea: `0x18000b3b0`
- end: `0x18000b3ed`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b274`
- `0x18000b3b0`
- `0x18000b86c`

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
0x18000b3b0  mov     [rsp+arg_0], rbx
0x18000b3b5  mov     [rsp+arg_8], rsi
0x18000b3ba  push    rdi
0x18000b3bb  sub     rsp, 20h
0x18000b3bf  mov     rdi, r8
0x18000b3c2  mov     ebx, edx
0x18000b3c4  mov     rsi, rcx
0x18000b3c7  cmp     edx, 1
0x18000b3ca  jnz     short loc_18000B3D1
0x18000b3cc  call    __security_init_cookie
0x18000b3d1  mov     r8, rdi; lpvReserved
0x18000b3d4  mov     edx, ebx; fdwReason
0x18000b3d6  mov     rcx, rsi; hinstDLL
0x18000b3d9  mov     rbx, [rsp+28h+arg_0]
0x18000b3de  mov     rsi, [rsp+28h+arg_8]
0x18000b3e3  add     rsp, 20h
0x18000b3e7  pop     rdi
0x18000b3e8  jmp     dllmain_dispatch
```
