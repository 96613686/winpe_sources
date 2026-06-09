# _DllMainCRTStartup

- ea: `0x180001ea0`
- end: `0x180001edd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001d64`
- `0x180001ea0`
- `0x1800022fc`

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
0x180001ea0  mov     [rsp+arg_0], rbx
0x180001ea5  mov     [rsp+arg_8], rsi
0x180001eaa  push    rdi
0x180001eab  sub     rsp, 20h
0x180001eaf  mov     rdi, r8
0x180001eb2  mov     ebx, edx
0x180001eb4  mov     rsi, rcx
0x180001eb7  cmp     edx, 1
0x180001eba  jnz     short loc_180001EC1
0x180001ebc  call    __security_init_cookie
0x180001ec1  mov     r8, rdi; lpvReserved
0x180001ec4  mov     edx, ebx; fdwReason
0x180001ec6  mov     rcx, rsi; hinstDLL
0x180001ec9  mov     rbx, [rsp+28h+arg_0]
0x180001ece  mov     rsi, [rsp+28h+arg_8]
0x180001ed3  add     rsp, 20h
0x180001ed7  pop     rdi
0x180001ed8  jmp     dllmain_dispatch
```
