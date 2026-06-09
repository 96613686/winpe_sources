# _DllMainCRTStartup

- ea: `0x180001ca0`
- end: `0x180001cdd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b64`
- `0x180001ca0`
- `0x180002150`

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
0x180001ca0  mov     [rsp+arg_0], rbx
0x180001ca5  mov     [rsp+arg_8], rsi
0x180001caa  push    rdi
0x180001cab  sub     rsp, 20h
0x180001caf  mov     rdi, r8
0x180001cb2  mov     ebx, edx
0x180001cb4  mov     rsi, rcx
0x180001cb7  cmp     edx, 1
0x180001cba  jnz     short loc_180001CC1
0x180001cbc  call    __security_init_cookie
0x180001cc1  mov     r8, rdi; lpvReserved
0x180001cc4  mov     edx, ebx; fdwReason
0x180001cc6  mov     rcx, rsi; hinstDLL
0x180001cc9  mov     rbx, [rsp+28h+arg_0]
0x180001cce  mov     rsi, [rsp+28h+arg_8]
0x180001cd3  add     rsp, 20h
0x180001cd7  pop     rdi
0x180001cd8  jmp     dllmain_dispatch
```
