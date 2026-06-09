# _DllMainCRTStartup

- ea: `0x180001b50`
- end: `0x180001b8d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001a14`
- `0x180001b50`
- `0x180002380`

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
0x180001b50  mov     [rsp+arg_0], rbx
0x180001b55  mov     [rsp+arg_8], rsi
0x180001b5a  push    rdi
0x180001b5b  sub     rsp, 20h
0x180001b5f  mov     rdi, r8
0x180001b62  mov     ebx, edx
0x180001b64  mov     rsi, rcx
0x180001b67  cmp     edx, 1
0x180001b6a  jnz     short loc_180001B71
0x180001b6c  call    __security_init_cookie
0x180001b71  mov     r8, rdi; lpvReserved
0x180001b74  mov     edx, ebx; fdwReason
0x180001b76  mov     rcx, rsi; hinstDLL
0x180001b79  mov     rbx, [rsp+28h+arg_0]
0x180001b7e  mov     rsi, [rsp+28h+arg_8]
0x180001b83  add     rsp, 20h
0x180001b87  pop     rdi
0x180001b88  jmp     dllmain_dispatch
```
