# _DllMainCRTStartup

- ea: `0x180001c30`
- end: `0x180001c6d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c30`
- `0x180001c74`
- `0x180002334`

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
0x180001c30  mov     [rsp+arg_0], rbx
0x180001c35  mov     [rsp+arg_8], rsi
0x180001c3a  push    rdi
0x180001c3b  sub     rsp, 20h
0x180001c3f  mov     rdi, r8
0x180001c42  mov     ebx, edx
0x180001c44  mov     rsi, rcx
0x180001c47  cmp     edx, 1
0x180001c4a  jnz     short loc_180001C51
0x180001c4c  call    __security_init_cookie
0x180001c51  mov     r8, rdi
0x180001c54  mov     edx, ebx; fdwReason
0x180001c56  mov     rcx, rsi; hinstDLL
0x180001c59  mov     rbx, [rsp+28h+arg_0]
0x180001c5e  mov     rsi, [rsp+28h+arg_8]
0x180001c63  add     rsp, 20h
0x180001c67  pop     rdi
0x180001c68  jmp     __DllMainCRTStartup
```
