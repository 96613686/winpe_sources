# _DllMainCRTStartup

- ea: `0x180006b30`
- end: `0x180006b6d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006b30`
- `0x180006b74`
- `0x180006ee4`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180006b30  mov     [rsp+arg_0], rbx
0x180006b35  mov     [rsp+arg_8], rsi
0x180006b3a  push    rdi
0x180006b3b  sub     rsp, 20h
0x180006b3f  mov     rdi, r8
0x180006b42  mov     ebx, edx
0x180006b44  mov     rsi, rcx
0x180006b47  cmp     edx, 1
0x180006b4a  jnz     short loc_180006B51
0x180006b4c  call    __security_init_cookie
0x180006b51  mov     r8, rdi
0x180006b54  mov     edx, ebx; fdwReason
0x180006b56  mov     rcx, rsi; hinstDLL
0x180006b59  mov     rbx, [rsp+28h+arg_0]
0x180006b5e  mov     rsi, [rsp+28h+arg_8]
0x180006b63  add     rsp, 20h
0x180006b67  pop     rdi
0x180006b68  jmp     __DllMainCRTStartup
```
