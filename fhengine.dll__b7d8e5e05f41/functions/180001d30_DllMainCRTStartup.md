# _DllMainCRTStartup

- ea: `0x180001d30`
- end: `0x180001d6d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001d30`
- `0x180001d74`
- `0x180002734`

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
0x180001d30  mov     [rsp+arg_0], rbx
0x180001d35  mov     [rsp+arg_8], rsi
0x180001d3a  push    rdi
0x180001d3b  sub     rsp, 20h
0x180001d3f  mov     rdi, r8
0x180001d42  mov     ebx, edx
0x180001d44  mov     rsi, rcx
0x180001d47  cmp     edx, 1
0x180001d4a  jnz     short loc_180001D51
0x180001d4c  call    __security_init_cookie
0x180001d51  mov     r8, rdi
0x180001d54  mov     edx, ebx; fdwReason
0x180001d56  mov     rcx, rsi; hinstDLL
0x180001d59  mov     rbx, [rsp+28h+arg_0]
0x180001d5e  mov     rsi, [rsp+28h+arg_8]
0x180001d63  add     rsp, 20h
0x180001d67  pop     rdi
0x180001d68  jmp     __DllMainCRTStartup
```
