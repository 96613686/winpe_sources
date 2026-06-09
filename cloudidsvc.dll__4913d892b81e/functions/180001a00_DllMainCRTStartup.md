# _DllMainCRTStartup

- ea: `0x180001a00`
- end: `0x180001a3d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800018c4`
- `0x180001a00`
- `0x180001e7c`

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
0x180001a00  mov     [rsp+arg_0], rbx
0x180001a05  mov     [rsp+arg_8], rsi
0x180001a0a  push    rdi
0x180001a0b  sub     rsp, 20h
0x180001a0f  mov     rdi, r8
0x180001a12  mov     ebx, edx
0x180001a14  mov     rsi, rcx
0x180001a17  cmp     edx, 1
0x180001a1a  jnz     short loc_180001A21
0x180001a1c  call    __security_init_cookie
0x180001a21  mov     r8, rdi; lpvReserved
0x180001a24  mov     edx, ebx; fdwReason
0x180001a26  mov     rcx, rsi; hinstDLL
0x180001a29  mov     rbx, [rsp+28h+arg_0]
0x180001a2e  mov     rsi, [rsp+28h+arg_8]
0x180001a33  add     rsp, 20h
0x180001a37  pop     rdi
0x180001a38  jmp     dllmain_dispatch
```
