# _DllMainCRTStartup

- ea: `0x180001a10`
- end: `0x180001a4d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800018d4`
- `0x180001a10`
- `0x180001b64`

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
0x180001a10  mov     [rsp+arg_0], rbx
0x180001a15  mov     [rsp+arg_8], rsi
0x180001a1a  push    rdi
0x180001a1b  sub     rsp, 20h
0x180001a1f  mov     rdi, r8
0x180001a22  mov     ebx, edx
0x180001a24  mov     rsi, rcx
0x180001a27  cmp     edx, 1
0x180001a2a  jnz     short loc_180001A31
0x180001a2c  call    __security_init_cookie
0x180001a31  mov     r8, rdi; lpvReserved
0x180001a34  mov     edx, ebx; fdwReason
0x180001a36  mov     rcx, rsi; hinstDLL
0x180001a39  mov     rbx, [rsp+28h+arg_0]
0x180001a3e  mov     rsi, [rsp+28h+arg_8]
0x180001a43  add     rsp, 20h
0x180001a47  pop     rdi
0x180001a48  jmp     dllmain_dispatch
```
