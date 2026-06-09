# _DllMainCRTStartup

- ea: `0x180001e10`
- end: `0x180001e4d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001cd4`
- `0x180001e10`
- `0x180002290`

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
0x180001e10  mov     [rsp+arg_0], rbx
0x180001e15  mov     [rsp+arg_8], rsi
0x180001e1a  push    rdi
0x180001e1b  sub     rsp, 20h
0x180001e1f  mov     rdi, r8
0x180001e22  mov     ebx, edx
0x180001e24  mov     rsi, rcx
0x180001e27  cmp     edx, 1
0x180001e2a  jnz     short loc_180001E31
0x180001e2c  call    __security_init_cookie
0x180001e31  mov     r8, rdi; lpvReserved
0x180001e34  mov     edx, ebx; fdwReason
0x180001e36  mov     rcx, rsi; hinstDLL
0x180001e39  mov     rbx, [rsp+28h+arg_0]
0x180001e3e  mov     rsi, [rsp+28h+arg_8]
0x180001e43  add     rsp, 20h
0x180001e47  pop     rdi
0x180001e48  jmp     dllmain_dispatch
```
