# _DllMainCRTStartup

- ea: `0x180001f10`
- end: `0x180001f4d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001dd4`
- `0x180001f10`
- `0x180002394`

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
0x180001f10  mov     [rsp+arg_0], rbx
0x180001f15  mov     [rsp+arg_8], rsi
0x180001f1a  push    rdi
0x180001f1b  sub     rsp, 20h
0x180001f1f  mov     rdi, r8
0x180001f22  mov     ebx, edx
0x180001f24  mov     rsi, rcx
0x180001f27  cmp     edx, 1
0x180001f2a  jnz     short loc_180001F31
0x180001f2c  call    __security_init_cookie
0x180001f31  mov     r8, rdi; lpvReserved
0x180001f34  mov     edx, ebx; fdwReason
0x180001f36  mov     rcx, rsi; hinstDLL
0x180001f39  mov     rbx, [rsp+28h+arg_0]
0x180001f3e  mov     rsi, [rsp+28h+arg_8]
0x180001f43  add     rsp, 20h
0x180001f47  pop     rdi
0x180001f48  jmp     dllmain_dispatch
```
